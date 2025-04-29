---
{"dg-publish":true,"permalink":"/bookmarks/tech/three-laws-of-software-complexity/","tags":["bestpractices","coding","interesting","software","work"]}
---


# [Three Laws of Software Complexity (or: why software engineers are always grumpy) | mahesh’s blog](https://maheshba.bitbucket.io/blog/2024/05/08/2024-ThreeLaws.html)

- [The First Law of Software Complexity: **A well-designed system will degrade into a badly designed system over time.**]()
- [The Second Law of Software Complexity: **Complexity is a Moat (filled by Leaky Abstractions)**.]()
- [The Third Law of Software Complexity: **There is no fundamental upper limit on Software Complexity**.]()

I posit that most software engineers (particularly those working on infrastructural systems) are destined to wallow in unnecessary complexity due to three fundamental laws.

#### The First Law of Software Complexity: **A well-designed system will degrade into a badly designed system over time.**

We start with an opinionated definition: a well-designed system is one that is easy to change over time; a badly designed system is one that is difficult to change. Let’s say that a system X is well-designed. Someone comes along and changes it – by definition, quickly and easily – to a different system X’. Now X’ either continues to be well-designed; in which case it can be quickly and easily modified again to a different system X’’; or it will enter a badly designed state and hence be difficult to modify. For example, consider a well-designed database that uses RocksDB behind a clean storage engine API; and someone comes along and adds a getLevelSize call to it; now the database can no longer easily be modified to work over a non-LSM storage engine. It follows that a well-designed system is an unstable, ephemeral state; whereas a badly designed system is a stable, persistent state. Accordingly, the mix of systems in the wild continuously degrades towards poor design. The second derivative of code is always negative in the wild: the rate at which code can change goes down over time. Based on this law, most engineers will work on badly designed systems because **_most systems turn into badly designed systems over time_**.

#### The Second Law of Software Complexity: **Complexity is a Moat (filled by Leaky Abstractions)**.

Designing a good abstraction is a delicate dance between providing utility to the application while hiding detail about the implementation. When systems compete with each other for market share, delicacy goes out the window and designers often give the application everything it wants. This has the dual effect of increasing market share by attracting application developers; while simultaneously making it difficult for competing systems to substitute different implementations under the hood. Some of the most successful systems on the planet have APIs that are nearly impossible to implement in any other way (ZooKeeper’s stronger-than-linearizable consistency and TCP/IP-based ephemeral node semantics come to mind; as does Kafka’s idempotent produce semantics). Based on this law, most engineers will work on badly designed systems because **_most successful/popular systems are badly designed systems_**.

#### The Third Law of Software Complexity: **There is no fundamental upper limit on Software Complexity**.

In real-world systems that are built by large groups of people over time, complexity is limited only by human creativity. The shape of a system is determined by the abilities, philosophies, and idiosyncrasies of dozens of developers, each working within a complex set of real and perceived incentives. For example, why does this replicated database use its own gossip layer to detect failures instead of relying on Kubernetes? Maybe Alice the TL and Bob the developer agreed that gossip-based failure detection was the way to go; but once Bob wrote the code, Alice realized that it was the wrong approach in a containerized environment; but Charlie the manager had already written the promo docs for Bob and Alice didn’t want to take the political risk of blocking the PR. Or maybe the system was initially designed by Bob for a non-containerized environment where gossip actually was a good choice. Or maybe Bob’s PhD was on gossip-based protocols. Maybe Alice then split membership and leader election into different layers to avoid antagonizing Bob and Charlie, which is why your system now has two layers with interesting interactions. Each existing system is a DoS attack on you by dozens of people you may not even know; a booby-trapped palace of ticking complexity time-bombs planted years ahead of your involvement. Based on this law, engineers that work on badly designed systems will particularly suffer since **_badly designed systems have unbounded complexity_**.

What can we do about this state of affairs? In my career, I have taken a particular approach based on building new systems from scratch (before they succumb to the three laws), but this is a lot harder than it sounds – more on that in a different post.
