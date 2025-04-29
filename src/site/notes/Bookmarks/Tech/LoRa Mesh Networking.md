---
{"dg-publish":true,"permalink":"/bookmarks/tech/lo-ra-mesh-networking/","tags":["diy","interesting","internet","privacy"]}
---


‍

# [LoRa Mesh Networking with Simple Arduino-Based Modules | Project Lab](https://nootropicdesign.com/projectlab/2018/10/20/lora-mesh-networking/)

Project source code at GitHub: [lora-mesh](https://github.com/nootropicdesign/lora-mesh)

In this project, I will show you how I built a mesh network of 4 Arduino-Based LoRa modules and devised a way to visualize the network’s behavior in realtime. Using a realtime visualization we can see how the network forms and how it heals itself when network nodes become unreachable.

[<img alt="" src="https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/meshNetwork.png" height="480" width="640" />](https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/meshNetwork.png)

By now you’ve probably heard of LoRa (“long range”) radio technology. It is intended for reliable communication of small amounts of data over long distances (several kilometers). It’s also geared toward low power applications. LoRa modules are relatively cheap (about $8 for a bare module), but the easiest way to use LoRa is to buy development boards that also have a microcontroller on them, like the [Moteino](https://lowpowerlab.com/guide/moteino/lora-support/).

LoRa radios can be used for point-to-point communication, and can also be used in a LoRaWAN network which involves communication with a centralized base station. This article, however, discusses a different approach: mesh networking of LoRa nodes. Mesh networking is a network topology where nodes communicate with one another either directly (if they are in range) or indirectly via intermediate nodes. For example, if node 1 wants to send a message to node 2, but is too far away from node 2, the message will automatically be routed via an intermediate node that is in range, say Node 3.

[<img alt="" src="https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/routeExample.png" height="186" width="640" />](https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/routeExample.png)

In fact, the path may involve several intermediate nodes. The discovery of the route from 1 to 2 is handled by a mesh networking layer — your application code doesn’t need to know anything about the routing. With mesh networking, LoRa nodes can be spread out across a further distance but can still communicate with one another as long as there is some connectivity between nodes in the mesh. Every node can talk to every other node, even though the network is only partially connected. Sound familiar? This is pretty much the architecture of the Internet. The robustness lies with the ability to route around damage and find new routes.

### Mesh Networking in Arduino Code

How do we accomplish mesh networking with simple LoRa radios? If you have used LoRa radios before, you probably used the [RadioHead](http://www.airspayce.com/mikem/arduino/RadioHead/) library. We will use it in this project, too, because it includes an implementation of mesh networking. For details on how the mesh works, see the [RadioHead documentation about it](http://www.airspayce.com/mikem/arduino/RadioHead/classRHMesh.html). I wrote an Arduino sketch to run on each of 4 Moteino boards so that each node will form a part of the network. Each node has an identity (e.g. “2”) which is stored in the device EEPROM.

First a note about the difficulty of testing mesh networks. It’s hard to place the nodes in such a way that only some nodes can communicate directly. To do so, I’d have to put my nodes far apart all over my neighborhood. Lucky, the RadioHead library has several test networks defined so that you can force some nodes to not be able to communicate. When a test network is defined, the RadioHead library simply ignores messages is receives from nodes it is not supposed to be able to hear. This lets us test much more easily. I’m using test network which is defined in the library like this:

```
 RH_TEST_NETWORK==3
  // This network looks like 1-2-4
  //                         |   |
  //                         --3--

```

That is, nodes 1 and 4 cannot communicate with one another directly, and nodes 2 and 3 cannot communicate with one another directly. This will become very evident in the visualization.

Each node attempts to communicate with every other node in the network, and in the process it keeps track of a routing table that describes which nodes it can talk to directly and which nodes that messages get routed through when there is no direct connection available. It also keeps track of the signal strength that it “hears” from a node when it communicates with it directly. The result is that each node has a data structure with this info. Here is a sample routing table (expressed in JSON) for node 2:

{"2": [{"n":1,"r":-68}, {"n":255,"r":0}, {"n":1,"r":0}, {"n":0,"r":0}]}

The data has an array of 4 records, one for each node in the network. The 4 records above represent the routing info for this node (2) communicating with nodes 1, 2, 3, and 4 respectively. Each record has two properties. Propery “n” is the identity of the node that node 2 must talk to in order to communicate with the node in this position of the table. Record number 1 {"n":1,"r":-68} means that node 2 can talk to node 1 via node 1. That is, it has successfully communicated directly with node 1 and the signal strength indicated by the “r” property is -68 dBm.

Record 2 {"n":255,"r":0} has an “n” value of 255 which means “self”, so we can ignore this record. Record 3 {"n":1,"r":0} means that node 2 must communicate with node 3 via node 1 because there is no direct communication (which is why the RSSI value is 0). Record 4 {"n":0,"r":0} has a “n” property of 0 which means that node 2 has not yet discovered a way to talk to node 4. This may because it has not tried yet, or perhaps node 4 has dropped out of the network and nobody can find it.

Over time, by attempting to send messages to every other node, each node builds up this information about who it can talk to and how its messages are being routed, as well as the signal strength that it “hears” from any node it successfully communicates directly with. The information sent in messages is the node’s routing table itself. That is why we represent the routing table as a JSON string and use abbreviated property names. We want the message to be short.

### Visualizing the Mesh Network

In order to display the network in a web page, we need to get all the routing information from each node. One of the LoRa nodes in my network (node 1) is connected to the Internet by connecting the Moteino board to an IoT Experimenter board. The [IoT Experimenter](https://nootropicdesign.com/projectlab/2017/09/03/iot-experimenter-esp8266-dev-board/) is a simple ESP8266 development board I built to help with my IoT projects. It serves as a gateway to the Internet for this project. When node 1 receives a routing table from another node, it writes the JSON data over serial to the ESP8266 gateway code. The gateway writes the record to an MQTT topic. Over time, the routing table from each node is written to the topic and updated as the info changes.

Now we need a way for this information to be displayed on a web page. I wrote a Node.js server that subscribes to the MQTT topic and writes the info over a websocket to a web client using Socket.IO. The graphics are created using [p5.js](https://p5js.org/) which is an easy way to draw impressive graphics on a web page canvas.

[<img alt="" src="https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/projectArchitecture.png" width="640" />](https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/projectArchitecture.png)

A solid line between 2 nodes means there is direct communication. The color of the line matches the node that is making the observation, and the number is the signal strength that the node “hears” from the other node. So below we can see that node 1 and 2 are directly able to communicate and that node 1 is receiving from node 2 with an RSSI value of -63 dBm and node 2 receives from node 1 with an RSSI of -64 dBm. The distance between nodes is proportional to the signal strength — you can see that node 4 is further away from the other nodes.

[<img alt="" src="https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/meshNetwork2.png" height="480" width="640" />](https://nootropicdesign.com/projectlab/wp-content/uploads/2018/10/meshNetwork2.png)

Lines with dots indicate indirect communication, for example, the lines between nodes 1 and 4 mean that they are communicating indirectly. The yellow dots on the red line mean that node 1 is communicating with node 4 via node 2 (which is yellow). The blue dots on the green line mean that node 4 is communicating with node 1 via node 3. Note that the communication between nodes 2 and 3 have red dots, meaning that node 1 is serving as the intermediary for these nodes.

### Formation/Healing of a Mesh Network

Let’s see the visualization in action! This video shows the formation of a network when I connect power to the nodes. In the video I remove power from one of the nodes serving as an intermediary in the mesh and we can see how the network heals itself by finding new routes.

[![IMG-20241106232529677.jpg](/img/user/_resources/IMG-20241106232529677.jpg)](https://www.youtube.com/watch?v=9d1qyeix2pk)

### Get the Code

All the source code for this project is available on GitHub: [nootropic design lora-mesh project](https://github.com/nootropicdesign/lora-mesh).  
It includes info on how to use this code yourself if you are interested.
