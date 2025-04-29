---
{"dg-publish":true,"permalink":"/bookmarks/ideas-and-theories/hacker-s-laws/","tags":["bestpractices","ethics","hacker","halloffame","interesting","opensource","theory"]}
---


[github.com](https://github.com/dwmkerr/hacker-laws)

See also [[Bookmarks/Ideas and Theories/The Crypto Anarchist Manifesto\|The Crypto Anarchist Manifesto]], [[Bookmarks/Ideas and Theories/The GNU Manifesto\|The GNU Manifesto]], [[Bookmarks/Tech/A Declaration of the Independence of Cyberspace\|A Declaration of the Independence of Cyberspace]]

# dwmkerr/hacker-laws: 💻📖 Laws, Theories, Principles and Patterns that developers will find useful.

55–69 minutes

---

## 💻📖 hacker-laws

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Laws, Theories, Principles and Patterns that developers will find useful.

[Translations](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws): [🇮🇩](https://github.com/dwmkerr/hacker-laws/blob/main/translations/id.md) [🇧🇷](https://github.com/dwmkerr/hacker-laws/blob/main/translations/pt-BR.md) [🇨🇳](https://github.com/nusr/hacker-laws-zh) [🇩🇪](https://github.com/dwmkerr/hacker-laws/blob/main/translations/de.md) [🇫🇷](https://github.com/dwmkerr/hacker-laws/blob/main/translations/fr.md) [🇬🇷](https://github.com/dwmkerr/hacker-laws/blob/main/translations/el.md) [🇮🇹](https://github.com/csparpa/hacker-laws-it) [🇱🇻](https://github.com/dwmkerr/hacker-laws/blob/main/translations/lv.md) [🇰🇷](https://github.com/codeanddonuts/hacker-laws-kr) [🇵🇱](https://github.com/dwmkerr/hacker-laws/blob/main/translations/pl.md) [🇷🇺](https://github.com/solarrust/hacker-laws) [🇪🇸](https://github.com/dwmkerr/hacker-laws/blob/main/translations/es-ES.md) [🇹🇷](https://github.com/umutphp/hacker-laws-tr) [🇯🇵](https://github.com/dwmkerr/hacker-laws/blob/main/translations/jp.md) [🇺🇦](https://github.com/dwmkerr/hacker-laws/blob/main/translations/uk.md) [🇻🇳](https://github.com/dwmkerr/hacker-laws/blob/main/translations/vi.md)

Like this project? Please considering [sponsoring me](https://github.com/sponsors/dwmkerr) and the [translators](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws). Also check out this podcast on [The Changelog - Laws for Hackers to Live By](https://changelog.com/podcast/403) to learn more about the project! You can also [download the latest PDF eBook](https://github.com/dwmkerr/hacker-laws/releases/latest/download/hacker-laws.pdf). Check the [Contributor Guide](https://github.com/dwmkerr/hacker-laws/blob/main/.github/contributing.md) if you are keen to contribute!

```table-of-contents

```

## Introduction

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

There are lots of laws which people discuss when talking about development. This repository is a reference and overview of some of the most common ones. Please share and submit PRs!

❗: This repo contains an explanation of some laws, principles and patterns, but does not _advocate_ for any of them. Whether they should be applied will always be a matter of debate, and greatly dependent on what you are working on.

## Laws

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-lawss)

And here we go!

### 90–9–1 Principle (1% Rule)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[1% Rule on Wikipedia](<https://en.wikipedia.org/wiki/1%25_rule_(Internet_culture)>)

The 90-9-1 principle suggests that within an internet community such as a wiki, 90% of participants only consume content, 9% edit or modify content and 1% of participants add content.

Real-world examples:

- A 2014 study of four digital health social networks found the top 1% created 73% of posts, the next 9% accounted for an average of ~25% and the remaining 90% accounted for an average of 2% ([Reference](https://www.jmir.org/2014/2/e33/))

See Also:

- [Pareto principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Amdahl's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Amdahl's Law on Wikipedia](https://en.wikipedia.org/wiki/Amdahl%27s_law)

> Amdahl's Law is a formula which shows the _potential speedup_ of a computational task which can be achieved by increasing the resources of a system. Normally used in parallel computing, it can predict the actual benefit of increasing the number of processors, which is limited by the parallelisability of the program.

Best illustrated with an example. If a program is made up of two parts, part A, which must be executed by a single processor, and part B, which can be parallelised, then we see that adding multiple processors to the system executing the program can only have a limited benefit. It can potentially greatly improve the speed of part B - but the speed of part A will remain unchanged.

The diagram below shows some examples of potential improvements in speed:

[![IMG-20241106232535833.png](/img/user/_resources/IMG-20241106232535833.png)](https://github.com/dwmkerr/hacker-laws/blob/main/images/amdahls_law.png)

_(Image Reference: By Daniels219 at English Wikipedia, Creative Commons Attribution-Share Alike 3.0 Unported, [https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg](https://en.wikipedia.org/wiki/File:AmdahlsLaw.svg))_

As can be seen, even a program which is 50% parallelisable will benefit very little beyond 10 processing units, whereas a program which is 95% parallelisable can still achieve significant speed improvements with over a thousand processing units.

As [Moore's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) slows, and the acceleration of individual processor speed slows, parallelisation is key to improving performance. Graphics programming is an excellent example - with modern Shader based computing, individual pixels or fragments can be rendered in parallel - this is why modern graphics cards often have many thousands of processing cores (GPUs or Shader Units).

See also:

- [Brooks' Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Moore's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Broken Windows Theory

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Broken Windows Theory on Wikipedia](https://en.wikipedia.org/wiki/Broken_windows_theory)

The Broken Windows Theory suggests that visible signs of crime (or lack of care of an environment) lead to further and more serious crimes (or further deterioration of the environment).

This theory has been applied to software development, suggesting that poor quality code (or [Technical Debt](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)) can lead to a perception that efforts to improve quality may be ignored or undervalued, thus leading to further poor quality code. This effect cascades leading to a great decrease in quality over time.

See also:

- [Technical Debt](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Examples:

- [The Pragmatic Programming: Software Entropy](https://flylib.com/books/en/1.315.1.15/1/)
- [Coding Horror: The Broken Window Theory](https://blog.codinghorror.com/the-broken-window-theory/)
- [OpenSource: Joy of Programming - The Broken Window Theory](https://opensourceforu.com/2011/05/joy-of-programming-broken-window-theory/)

### Brooks' Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Brooks' Law on Wikipedia](https://en.wikipedia.org/wiki/Brooks%27s_law)

> Adding human resources to a late software development project makes it later.

This law suggests that in many cases, attempting to accelerate the delivery of a project which is already late, by adding more people, will make the delivery even later. Brooks is clear that this is an over-simplification, however, the general reasoning is that given the ramp-up time of new resources and the communication overheads, in the immediate short-term velocity decreases. Also, many tasks may not be divisible, i.e. easily distributed between more resources, meaning the potential velocity increase is also lower.

The common phrase in delivery "Nine women can't make a baby in one month" relates to Brooks' Law, in particular, the fact that some kinds of work are not divisible or parallelisable.

This is a central theme of the book '[The Mythical Man Month](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)'.

See also:

- [Death March](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Reading List: The Mythical Man Month](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### CAP Theorem (Brewer's Theorem)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

The CAP Theorem (defined by Eric Brewer) states that for a distributed data store only two out of the following three guarantees (at most) can be made:

- Consistency: when reading data, every request receives the _most recent_ data or an error is returned
- Availability: when reading data, every request receives _a non error response_, without the guarantee that it is the _most recent_ data
- Partition Tolerance: when an arbitrary number of network requests between nodes fail, the system continues to operate as expected

The core of the reasoning is as follows. It is impossible to guarantee that a network partition will not occur (see [The Fallacies of Distributed Computing](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)). Therefore in the case of a partition we can either cancel the operation (increasing consistency and decreasing availability) or proceed (increasing availability but decreasing consistency).

The name comes from the first letters of the guarantees (Consistency, Availability, Partition Tolerance). Note that it is very important to be aware that this does _not_ relate to [_ACID_](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws), which has a different definition of consistency. More recently, [PACELC](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) theorem has been developed which adds constraints for latency and consistency when the network is _not_ partitioned (i.e. when the system is operating as expected).

Most modern database platforms acknowledge this theorem implicitly by offering the user of the database the option to choose between whether they want a highly available operation (which might include a 'dirty read') or a highly consistent operation (for example a 'quorum acknowledged write').

Real world examples:

- [Inside Google Cloud Spanner and the CAP Theorem](https://cloud.google.com/blog/products/gcp/inside-cloud-spanner-and-the-cap-theorem) - Goes into the details of how Cloud Spanner works, which appears at first to seem like a platform which has _all_ of the guarantees of CAP, but under the hood is essentially a CP system.

See also:

- [ACID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [The Fallacies of Distributed Computing](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [PACELC](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Clarke's three laws

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Clarke's three laws on Wikipedia](https://en.wikipedia.org/wiki/Clarke's_three_laws)

Arthur C. Clarke, an british science fiction writer, formulated three adages that are known as Clarke's three laws. The third law is the best known and most widely cited.

These so-called laws are:

- When a distinguished but elderly scientist states that something is possible, they are almost certainly right. When they state that something is impossible, they are very probably wrong.
- The only way of discovering the limits of the possible is to venture a little way past them into the impossible.
- Any sufficiently advanced technology is indistinguishable from magic.

### Conway's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Conway's Law on Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_law)

This law suggests that the technical boundaries of a system will reflect the structure of the organisation. It is commonly referred to when looking at organisation improvements, Conway's Law suggests that if an organisation is structured into many small, disconnected units, the software it produces will be. If an organisation is built more around 'verticals' which are oriented around features or services, the software systems will also reflect this.

See also:

- [The Spotify Model](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Cunningham's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Cunningham's Law on Wikipedia](https://en.wikipedia.org/wiki/Ward_Cunningham's_Law)

> The best way to get the right answer on the Internet is not to ask a question, it's to post the wrong answer.

According to Steven McGeady, Ward Cunningham advised him in the early 1980s: "The best way to get the right answer on the Internet is not to ask a question, it's to post the wrong answer." McGeady dubbed this Cunningham's law, though Cunningham denies ownership calling it a "misquote." Although originally referring to interactions on Usenet, the law has been used to describe how other online communities work (e.g., Wikipedia, Reddit, Twitter, Facebook).

See also:

- [XKCD 386: "Duty Calls"](https://xkcd.com/386/)

### Dunbar's Number

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Dunbar's Number on Wikipedia](https://en.wikipedia.org/wiki/Dunbar%27s_number)

"Dunbar's number is a suggested cognitive limit to the number of people with whom one can maintain stable social relationships— relationships in which an individual knows who each person is and how each person relates to every other person." There is some disagreement to the exact number. "... [Dunbar] proposed that humans can comfortably maintain only 150 stable relationships." He put the number into a more social context, "the number of people you would not feel embarrassed about joining uninvited for a drink if you happened to bump into them in a bar." Estimates for the number generally lay between 100 and 250.

Like stable relationships between individuals, a developer's relationship with a codebase takes effort to maintain. When faced with large complicated projects, or ownership of many projects, we lean on convention, policy, and modeled procedure to scale. Dunbar's number is not only important to keep in mind as an office grows, but also when setting the scope for team efforts or deciding when a system should invest in tooling to assist in modeling and automating logistical overhead. Putting the number into an engineering context, it is the number of projects (or normalized complexity of a single project) for which you would feel confident in joining an on-call rotation to support.

See also:

- [Conway's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Dunning-Kruger Effect

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Dunning-Kruger Effect on Wikipedia](https://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect)

> If you're incompetent, you can't know you're incompetent... The skills you need to produce a right answer are exactly the skills you need to recognize what a right answer is.
>
> ([David Dunning](https://en.wikipedia.org/wiki/David_Dunning))

The Dunning–Kruger effect is a theoretical cognitive bias which was described by David Dunning and Justin Kruger in a 1999 psychological study and paper. The study suggests that people with a low level of ability at a task are likely to overestimate their ability of the task. The proposed reason for this bias is that a sufficient _awareness_ of the complexity of a problem or domain is required for a person to be able to make an informed opinion of their capability to work in that domain.

The Dunning-Kruger effect has sometimes been used to describe a related, but not necessarily implied effect which could be described as "The less a person understands a domain, the more they are likely to believe they can easily solve problems in that domain, as they are more likely to see the domain as _simple_". This more general effect is highly relevant in technology. It would suggest that people who are less familiar with a domain, such as non-technical team members or less experienced team members, are more likely to _underestimate_ the effort required to solve a problem in this space.

As a person's understanding and experience in a domain grows, they may well encounter another effect, which is that they tend to _overestimate_ the ability of _others_ or _underestimate_ their own ability, as they are have become so experienced in the domain. In all cases these effects are _cognitive biases_. As with any bias, an understanding that it may be present will often be sufficient to help avoid the challenges — as when there is awareness of a bias, more inputs and opinions can be included to attempt to eliminate these biases. A closely related bias is that of [Illusory superiority](https://en.wikipedia.org/wiki/Illusory_superiority).

Real-world examples:

- [Apple vs. FBI: Why This Anti-Terror Hawk Switched Sides](https://fortune.com/2016/03/10/apple-fbi-lindsay-graham/) - In 2016 Senator Lindsey Graham changed his stance on Apple creating a 'backdoor' in their encryption of devices. Initially Graham had been critical of Apple challenging a request to create a 'backdoor', which he saw as necessary to investigate potential terrorist plots. However, by Graham's own admission, as he learned more about the technical complexity of the domain, he realised that he had assumed it to be far more simple than he had realised, and that such a backdoor could have serious negative consequences. This could potentially be considered an example of the Dunning-Kruger effect - a cyber-security expert would likely understand immediately how such a backdoor could be exploited, as they have deep understanding of the domain, a layperson might assume that phone security is more similar to _physical security_ where the practice of having a 'master key' for law enforcement is possible, but this analogy does not apply sufficiently well to describe modern encryption in cyber-security.

### Fitts' Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Fitts' Law on Wikipedia](https://en.wikipedia.org/wiki/Fitts%27s_law)

Fitts' law predicts that the time required to move to a target area is a function of the distance to the target divided by the width of the target.

[<?xml version="1.0" encoding="UTF-8" standalone="no"?><svg   width="640"   height="480"   version="1.1"   id="svg195"   sodipodi:docname="Fitts_Law.svg"   inkscape:version="1.1 (c68e22c387, 2021-05-23)"   xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"   xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"   xmlns="http://www.w3.org/2000/svg"   xmlns:svg="http://www.w3.org/2000/svg">  <defs     id="defs199" />  <sodipodi:namedview     id="namedview197"     pagecolor="#ffffff"     bordercolor="#666666"     borderopacity="1.0"     inkscape:pageshadow="2"     inkscape:pageopacity="0.0"     inkscape:pagecheckerboard="0"     showgrid="false"     inkscape:zoom="1.2197592"     inkscape:cx="253.73861"     inkscape:cy="240.21135"     inkscape:window-width="1920"     inkscape:window-height="1043"     inkscape:window-x="0"     inkscape:window-y="0"     inkscape:window-maximized="1"     inkscape:current-layer="layer2" />  <g     inkscape:groupmode="layer"     id="layer2"     inkscape:label="Layer 2"     style="display:inline">    <rect       style="fill:#ffffff;stroke-width:0"       id="rect557"       width="100%"       height="100%"       x="0"       y="0" />  </g>  <!-- Created with SVG-edit - http://svg-edit.googlecode.com/ -->  <g     id="g193">    <title       id="title161">Layer 1</title>    <g       id="svg_14"       transform="rotate(38.2092, 97, 276.029)">      <line         stroke-linecap="round"         id="svg_10"         y2="276"         x2="92"         y1="301"         x1="92.000002"         stroke-width="4"         stroke="#000000"         fill="none" />      <line         stroke-linecap="round"         id="svg_7"         y2="281"         x2="112"         y1="276"         x1="102"         stroke-width="4"         stroke="#000000"         fill="none" />      <line         id="svg_8"         stroke-linecap="round"         y2="276"         x2="102"         y1="301.058297"         x1="102"         stroke-width="4"         stroke="#000000"         fill="none" />      <line         id="svg_11"         stroke-linecap="round"         y2="276"         x2="92"         y1="281"         x1="82"         stroke-width="4"         stroke="#000000"         fill="none" />      <line         id="svg_12"         y2="251"         x2="97"         y1="281"         x1="82"         stroke-linecap="round"         stroke-linejoin="null"         stroke-dasharray="null"         stroke-width="4"         stroke="#000000"         fill="none" />      <line         id="svg_13"         y2="251"         x2="97"         y1="281"         x1="112"         stroke-linecap="round"         stroke-linejoin="null"         stroke-dasharray="null"         stroke-width="4"         stroke="#000000"         fill="none" />    </g>    <g       id="svg_16">      <line         fill="none"         stroke="#7f7f7f"         stroke-width="2"         stroke-linejoin="round"         stroke-linecap="round"         x1="570"         y1="135"         x2="420"         y2="135"         id="svg_1"         stroke-dasharray="5,5" />      <line         fill="none"         stroke="#7f7f7f"         stroke-width="2"         stroke-linejoin="round"         stroke-linecap="round"         x1="495"         y1="210"         x2="495"         y2="60"         id="svg_4"         stroke-dasharray="5,5" />      <rect         fill="none"         stroke="#000000"         stroke-width="5"         stroke-linejoin="round"         stroke-linecap="round"         x="445"         y="85"         width="100"         height="100"         id="svg_2" />      <text         fill="#000000"         stroke="#000000"         stroke-width="0"         stroke-dasharray="null"         stroke-linejoin="round"         stroke-linecap="round"         x="495.91669"         y="118.66669"         id="svg_3"         font-size="24"         font-family="Sans-serif"         text-anchor="middle"         xml:space="preserve"         font-weight="bold">Target</text>    </g>    <text       font-weight="bold"       xml:space="preserve"       text-anchor="middle"       font-family="Sans-serif"       font-size="24"       id="svg_5"       y="35"       x="494"       stroke-linecap="round"       stroke-linejoin="null"       stroke-dasharray="5,5"       stroke-width="0"       stroke="#7f7f7f"       fill="#000000">W</text>    <g       id="svg_21">      <line         fill="none"         stroke="#000000"         stroke-width="3"         stroke-linejoin="null"         stroke-linecap="round"         x1="445"         y1="45"         x2="545"         y2="45"         id="svg_9" />      <line         id="svg_17"         y2="55"         x2="455"         y1="45"         x1="445"         stroke-linecap="round"         stroke-linejoin="null"         stroke-width="3"         stroke="#000000"         fill="none" />      <line         id="svg_18"         y2="35"         x2="455"         y1="45"         x1="445"         stroke-linecap="round"         stroke-linejoin="null"         stroke-width="3"         stroke="#000000"         fill="none" />      <line         id="svg_19"         y2="55"         x2="535"         y1="45"         x1="545"         stroke-linecap="round"         stroke-linejoin="null"         stroke-width="3"         stroke="#000000"         fill="none" />      <line         id="svg_20"         y2="35"         x2="535"         y1="45"         x1="545"         stroke-linecap="round"         stroke-linejoin="null"         stroke-width="3"         stroke="#000000"         fill="none" />    </g>    <g       id="svg_37"       transform="rotate(-17.3352, 328.667, 273.333)">      <line         fill="none"         stroke="#7f7f7f"         stroke-width="2"         stroke-dasharray="5,5"         stroke-linejoin="null"         stroke-linecap="round"         x1="128.666668"         y1="191.333333"         x2="528.666668"         y2="191.333333"         id="svg_6" />      <text         id="svg_15"         font-weight="bold"         xml:space="preserve"         text-anchor="middle"         font-family="Sans-serif"         font-size="24"         y="349.333338"         x="327.000016"         stroke-linecap="round"         stroke-linejoin="null"         stroke-dasharray="5,5"         stroke-width="0"         stroke="#7f7f7f"         fill="#000000">D</text>      <g         id="svg_34">        <line           fill="none"           stroke="#000000"           stroke-width="3"           stroke-linejoin="null"           stroke-linecap="round"           x1="128.666668"           y1="316.000005"           x2="528.666668"           y2="316.000005"           id="svg_29" />        <line           y2="326.000005"           x2="138.666668"           y1="316.000005"           x1="128.666668"           stroke-linecap="round"           stroke-linejoin="null"           stroke-width="3"           stroke="#000000"           fill="none"           id="svg_30" />        <line           y2="306.000005"           x2="138.666668"           y1="316.000005"           x1="128.666668"           stroke-linecap="round"           stroke-linejoin="null"           stroke-width="3"           stroke="#000000"           fill="none"           id="svg_31" />        <line           y2="326.000005"           x2="518.666668"           y1="316.000005"           x1="528.666668"           stroke-linecap="round"           stroke-linejoin="null"           stroke-width="3"           stroke="#000000"           fill="none"           id="svg_32" />        <line           y2="306.000005"           x2="518.666668"           y1="316.000005"           x1="528.666668"           stroke-linecap="round"           stroke-linejoin="null"           stroke-width="3"           stroke="#000000"           fill="none"           id="svg_33" />      </g>      <line         fill="none"         stroke="#7f7f7f"         stroke-width="2"         stroke-dasharray="5,5"         stroke-linejoin="null"         stroke-linecap="round"         x1="128.666668"         y1="191.333333"         x2="128.666668"         y2="341.333333"         id="svg_35" />      <line         fill="none"         stroke="#7f7f7f"         stroke-width="2"         stroke-dasharray="5,5"         stroke-linejoin="null"         stroke-linecap="round"         x1="528.666668"         y1="191.333333"         x2="528.666668"         y2="341.333333"         id="svg_36" />    </g>  </g>  <g     inkscape:groupmode="layer"     id="layer1"     inkscape:label="Layer 1" /></svg>](https://github.com/dwmkerr/hacker-laws/blob/main/images/Fitts_Law.svg)

_(Image Reference: By Foobar628 at English Wikipedia, Creative Commons Attribution-Share Alike 3.0 Unported, [https://en.wikipedia.org/wiki/Fitts%27s_law:Fitts_Law.svg](https://en.wikipedia.org/wiki/Fitts%27s_law:Fitts_Law.svg))_

The consequences of this law dictate that when designing UX or UI, interactive elements should be as large as possible and the distance between the users attention area and interactive element should be as small as possible. This has consequences on design, such as grouping tasks that are commonly used with one another close.

It also formalises the concept of 'magic corners', the corners of the screen to which a user can 'sweep' their mouse to easily hit - which is where key UI elements can be placed. The Windows Start button is in a magic corner, making it easy to select, and as an interesting contrast, the MacOS 'close window' button is _not_ in a magic corner, making it hard to hit by mistake.

See also:

- [The information capacity of the human motor system in controlling the amplitude of movement.](https://www.semanticscholar.org/paper/The-information-capacity-of-the-human-motor-system-Fitts/634c9fde5f1c411e4487658ac738dcf18d98ea8d)

### Gall's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Gall's Law on Wikipedia](<https://en.wikipedia.org/wiki/John_Gall_(author)'s_law>)

> A complex system that works is invariably found to have evolved from a simple system that worked. A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over with a working simple system.
>
> ([John Gall](<https://en.wikipedia.org/wiki/John_Gall_(author)>))

Gall's Law implies that attempts to _design_ highly complex systems are likely to fail. Highly complex systems are rarely built in one go, but evolve instead from more simple systems.

The classic example is the world-wide-web. In its current state, it is a highly complex system. However, it was defined initially as a simple way to share content between academic institutions. It was very successful in meeting these goals and evolved to become more complex over time.

See also:

- [KISS (Keep It Simple, Stupid)](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Goodhart's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Goodhart's Law on Wikipedia](https://en.wikipedia.org/wiki/Goodhart's_law)

> Any observed statistical regularity will tend to collapse once pressure is placed upon it for control purposes.
>
> _Charles Goodhart_

Also commonly referenced as:

> When a measure becomes a target, it ceases to be a good measure.
>
> _Marilyn Strathern_

The law states that the measure-driven optimizations could lead to devaluation of the measurement outcome itself. Overly selective set of measures ([KPIs](https://en.wikipedia.org/wiki/Performance_indicator)) blindly applied to a process results in distorted effect. People tend to optimize locally by "gaming" the system in order to satisfy particular metrics instead of paying attention to holistic outcome of their actions.

Real-world examples:

- Assert-free tests satisfy the code coverage expectation, despite the fact that the metric intent was to create well-tested software.
- Developer performance score indicated by the number of lines committed leads to unjustifiably bloated codebase.

See also:

- [Goodhart’s Law: How Measuring The Wrong Things Drive Immoral Behaviour](https://coffeeandjunk.com/goodharts-campbells-law/)
- [Dilbert on bug-free software](https://dilbert.com/strip/1995-11-13)

### Hanlon's Razor

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Hanlon's Razor on Wikipedia](https://en.wikipedia.org/wiki/Hanlon%27s_razor)

> Never attribute to malice that which is adequately explained by stupidity.
>
> Robert J. Hanlon

This principle suggests that actions resulting in a negative outcome were not a result of ill will. Instead the negative outcome is more likely attributed to those actions and/or the impact being not fully understood.

### Hick's Law (Hick-Hyman Law)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Hick's law on Wikipedia](https://en.wikipedia.org/wiki/Hick%27s_law)

> Decision time grows logarithmically with the number of options you can choose from.
>
> William Edmund Hick and Ray Hyman

In the equation below, `T` is the time to make a decision, `n` is the number of options, and `b` is a constant which is determined by analysis of the data.

[<svg xmlns:xlink="http://www.w3.org/1999/xlink" width="18.644ex" height="2.843ex" style="vertical-align: -0.838ex;" viewBox="0 -863.1 8027.4 1223.9" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" aria-labelledby="MathJax-SVG-1-Title"><title id="MathJax-SVG-1-Title">{\displaystyle T=b\cdot \log _{2}(n+1)}</title><rect style="fill:#ffffff" id="rect557" width="100%"  height="100%" x="0" y="-863.1" /><defs aria-hidden="true"><path stroke-width="1" id="E1-MJMATHI-54" d="M40 437Q21 437 21 445Q21 450 37 501T71 602L88 651Q93 669 101 677H569H659Q691 677 697 676T704 667Q704 661 687 553T668 444Q668 437 649 437Q640 437 637 437T631 442L629 445Q629 451 635 490T641 551Q641 586 628 604T573 629Q568 630 515 631Q469 631 457 630T439 622Q438 621 368 343T298 60Q298 48 386 46Q418 46 427 45T436 36Q436 31 433 22Q429 4 424 1L422 0Q419 0 415 0Q410 0 363 1T228 2Q99 2 64 0H49Q43 6 43 9T45 27Q49 40 55 46H83H94Q174 46 189 55Q190 56 191 56Q196 59 201 76T241 233Q258 301 269 344Q339 619 339 625Q339 630 310 630H279Q212 630 191 624Q146 614 121 583T67 467Q60 445 57 441T43 437H40Z"></path><path stroke-width="1" id="E1-MJMAIN-3D" d="M56 347Q56 360 70 367H707Q722 359 722 347Q722 336 708 328L390 327H72Q56 332 56 347ZM56 153Q56 168 72 173H708Q722 163 722 153Q722 140 707 133H70Q56 140 56 153Z"></path><path stroke-width="1" id="E1-MJMATHI-62" d="M73 647Q73 657 77 670T89 683Q90 683 161 688T234 694Q246 694 246 685T212 542Q204 508 195 472T180 418L176 399Q176 396 182 402Q231 442 283 442Q345 442 383 396T422 280Q422 169 343 79T173 -11Q123 -11 82 27T40 150V159Q40 180 48 217T97 414Q147 611 147 623T109 637Q104 637 101 637H96Q86 637 83 637T76 640T73 647ZM336 325V331Q336 405 275 405Q258 405 240 397T207 376T181 352T163 330L157 322L136 236Q114 150 114 114Q114 66 138 42Q154 26 178 26Q211 26 245 58Q270 81 285 114T318 219Q336 291 336 325Z"></path><path stroke-width="1" id="E1-MJMAIN-22C5" d="M78 250Q78 274 95 292T138 310Q162 310 180 294T199 251Q199 226 182 208T139 190T96 207T78 250Z"></path><path stroke-width="1" id="E1-MJMAIN-6C" d="M42 46H56Q95 46 103 60V68Q103 77 103 91T103 124T104 167T104 217T104 272T104 329Q104 366 104 407T104 482T104 542T103 586T103 603Q100 622 89 628T44 637H26V660Q26 683 28 683L38 684Q48 685 67 686T104 688Q121 689 141 690T171 693T182 694H185V379Q185 62 186 60Q190 52 198 49Q219 46 247 46H263V0H255L232 1Q209 2 183 2T145 3T107 3T57 1L34 0H26V46H42Z"></path><path stroke-width="1" id="E1-MJMAIN-6F" d="M28 214Q28 309 93 378T250 448Q340 448 405 380T471 215Q471 120 407 55T250 -10Q153 -10 91 57T28 214ZM250 30Q372 30 372 193V225V250Q372 272 371 288T364 326T348 362T317 390T268 410Q263 411 252 411Q222 411 195 399Q152 377 139 338T126 246V226Q126 130 145 91Q177 30 250 30Z"></path><path stroke-width="1" id="E1-MJMAIN-67" d="M329 409Q373 453 429 453Q459 453 472 434T485 396Q485 382 476 371T449 360Q416 360 412 390Q410 404 415 411Q415 412 416 414V415Q388 412 363 393Q355 388 355 386Q355 385 359 381T368 369T379 351T388 325T392 292Q392 230 343 187T222 143Q172 143 123 171Q112 153 112 133Q112 98 138 81Q147 75 155 75T227 73Q311 72 335 67Q396 58 431 26Q470 -13 470 -72Q470 -139 392 -175Q332 -206 250 -206Q167 -206 107 -175Q29 -140 29 -75Q29 -39 50 -15T92 18L103 24Q67 55 67 108Q67 155 96 193Q52 237 52 292Q52 355 102 398T223 442Q274 442 318 416L329 409ZM299 343Q294 371 273 387T221 404Q192 404 171 388T145 343Q142 326 142 292Q142 248 149 227T179 192Q196 182 222 182Q244 182 260 189T283 207T294 227T299 242Q302 258 302 292T299 343ZM403 -75Q403 -50 389 -34T348 -11T299 -2T245 0H218Q151 0 138 -6Q118 -15 107 -34T95 -74Q95 -84 101 -97T122 -127T170 -155T250 -167Q319 -167 361 -139T403 -75Z"></path><path stroke-width="1" id="E1-MJMAIN-32" d="M109 429Q82 429 66 447T50 491Q50 562 103 614T235 666Q326 666 387 610T449 465Q449 422 429 383T381 315T301 241Q265 210 201 149L142 93L218 92Q375 92 385 97Q392 99 409 186V189H449V186Q448 183 436 95T421 3V0H50V19V31Q50 38 56 46T86 81Q115 113 136 137Q145 147 170 174T204 211T233 244T261 278T284 308T305 340T320 369T333 401T340 431T343 464Q343 527 309 573T212 619Q179 619 154 602T119 569T109 550Q109 549 114 549Q132 549 151 535T170 489Q170 464 154 447T109 429Z"></path><path stroke-width="1" id="E1-MJMAIN-28" d="M94 250Q94 319 104 381T127 488T164 576T202 643T244 695T277 729T302 750H315H319Q333 750 333 741Q333 738 316 720T275 667T226 581T184 443T167 250T184 58T225 -81T274 -167T316 -220T333 -241Q333 -250 318 -250H315H302L274 -226Q180 -141 137 -14T94 250Z"></path><path stroke-width="1" id="E1-MJMATHI-6E" d="M21 287Q22 293 24 303T36 341T56 388T89 425T135 442Q171 442 195 424T225 390T231 369Q231 367 232 367L243 378Q304 442 382 442Q436 442 469 415T503 336T465 179T427 52Q427 26 444 26Q450 26 453 27Q482 32 505 65T540 145Q542 153 560 153Q580 153 580 145Q580 144 576 130Q568 101 554 73T508 17T439 -10Q392 -10 371 17T350 73Q350 92 386 193T423 345Q423 404 379 404H374Q288 404 229 303L222 291L189 157Q156 26 151 16Q138 -11 108 -11Q95 -11 87 -5T76 7T74 17Q74 30 112 180T152 343Q153 348 153 366Q153 405 129 405Q91 405 66 305Q60 285 60 284Q58 278 41 278H27Q21 284 21 287Z"></path><path stroke-width="1" id="E1-MJMAIN-2B" d="M56 237T56 250T70 270H369V420L370 570Q380 583 389 583Q402 583 409 568V270H707Q722 262 722 250T707 230H409V-68Q401 -82 391 -82H389H387Q375 -82 369 -68V230H70Q56 237 56 250Z"></path><path stroke-width="1" id="E1-MJMAIN-31" d="M213 578L200 573Q186 568 160 563T102 556H83V602H102Q149 604 189 617T245 641T273 663Q275 666 285 666Q294 666 302 660V361L303 61Q310 54 315 52T339 48T401 46H427V0H416Q395 3 257 3Q121 3 100 0H88V46H114Q136 46 152 46T177 47T193 50T201 52T207 57T213 61V578Z"></path><path stroke-width="1" id="E1-MJMAIN-29" d="M60 749L64 750Q69 750 74 750H86L114 726Q208 641 251 514T294 250Q294 182 284 119T261 12T224 -76T186 -143T145 -194T113 -227T90 -246Q87 -249 86 -250H74Q66 -250 63 -250T58 -247T55 -238Q56 -237 66 -225Q221 -64 221 250T66 725Q56 737 55 738Q55 746 60 749Z"></path></defs><g stroke="currentColor" fill="currentColor" stroke-width="0" transform="matrix(1 0 0 -1 0 0)" aria-hidden="true"> <use xlink:href="#E1-MJMATHI-54" x="0" y="0"></use> <use xlink:href="#E1-MJMAIN-3D" x="982" y="0"></use> <use xlink:href="#E1-MJMATHI-62" x="2038" y="0"></use> <use xlink:href="#E1-MJMAIN-22C5" x="2690" y="0"></use><g transform="translate(3191,0)"> <use xlink:href="#E1-MJMAIN-6C"></use> <use xlink:href="#E1-MJMAIN-6F" x="278" y="0"></use> <use xlink:href="#E1-MJMAIN-67" x="779" y="0"></use> <use transform="scale(0.707)" xlink:href="#E1-MJMAIN-32" x="1809" y="-343"></use></g> <use xlink:href="#E1-MJMAIN-28" x="4924" y="0"></use> <use xlink:href="#E1-MJMATHI-6E" x="5313" y="0"></use> <use xlink:href="#E1-MJMAIN-2B" x="6136" y="0"></use> <use xlink:href="#E1-MJMAIN-31" x="7137" y="0"></use> <use xlink:href="#E1-MJMAIN-29" x="7637" y="0"></use></g></svg>](https://github.com/dwmkerr/hacker-laws/blob/main/images/hicks_law.svg)

_(Image Reference: Creative Commons Attribution-Share Alike 3.0 Unported, [https://en.wikipedia.org/wiki/Hick%27s_law](https://en.wikipedia.org/wiki/Hick%27s_law))_

This law only applies when the number of options is _ordered_, for example, alphabetically. This is implied in the base two logarithm - which implies the decision maker is essentially performing a _binary search_. If the options are not well ordered, experiments show the time taken is linear.

This is has significant impact in UI design; ensuring that users can easily search through options leads to faster decision making.

A correlation has also been shown in Hick's Law between IQ and reaction time as shown in [Speed of Information Processing: Developmental Change and Links to Intelligence](https://www.sciencedirect.com/science/article/pii/S0022440599000369).

See also:

- [Fitts's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Hofstadter's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Hofstadter's Law on Wikipedia](https://en.wikipedia.org/wiki/Hofstadter%27s_law)

> It always takes longer than you expect, even when you take into account Hofstadter's Law.
>
> (Douglas Hofstadter)

You might hear this law referred to when looking at estimates for how long something will take. It seems a truism in software development that we tend to not be very good at accurately estimating how long something will take to deliver.

This is from the book '[Gödel, Escher, Bach: An Eternal Golden Braid](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)'.

See also:

- [Reading List: Gödel, Escher, Bach: An Eternal Golden Braid](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Hutber's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Hutber's Law on Wikipedia](https://en.wikipedia.org/wiki/Hutber%27s_law)

> Improvement means deterioration.
>
> ([Patrick Hutber](https://en.wikipedia.org/wiki/Patrick_Hutber))

This law suggests that improvements to a system will lead to deterioration in other parts, or it will hide other deterioration, leading overall to a degradation from the current state of the system.

For example, a decrease in response latency for a particular end-point could cause increased throughput and capacity issues further along in a request flow, affecting an entirely different sub-system.

### The Hype Cycle & Amara's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Hype Cycle on Wikipedia](https://en.wikipedia.org/wiki/Hype_cycle)

> We tend to overestimate the effect of a technology in the short run and underestimate the effect in the long run.
>
> (Roy Amara)

The Hype Cycle is a visual representation of the excitement and development of technology over time, originally produced by Gartner. It is best shown with a visual:

[![IMG-20241106232536166.png](/img/user/_resources/IMG-20241106232536166.png)](https://github.com/dwmkerr/hacker-laws/blob/main/images/gartner_hype_cycle.png)

_(Image Reference: By Jeremykemp at English Wikipedia, CC BY-SA 3.0, [https://commons.wikimedia.org/w/index.php?curid=10547051](https://commons.wikimedia.org/w/index.php?curid=10547051))_

In short, this cycle suggests that there is typically a burst of excitement around new technology and its potential impact. Teams often jump into these technologies quickly, and sometimes find themselves disappointed with the results. This might be because the technology is not yet mature enough, or real-world applications are not yet fully realised. After a certain amount of time, the capabilities of the technology increase and practical opportunities to use it increase, and teams can finally become productive. Roy Amara's quote sums this up most succinctly - "We tend to overestimate the effect of a technology in the short run and underestimate in the long run".

### Hyrum's Law (The Law of Implicit Interfaces)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Hyrum's Law Online](http://www.hyrumslaw.com/)

> With a sufficient number of users of an API, it does not matter what you promise in the contract: all observable behaviours of your system will be depended on by somebody.
>
> (Hyrum Wright)

Hyrum's Law states that when you have a _large enough number of consumers_ of an API, all behaviours of the API (even those not defined as part of a public contract) will eventually come to be depended on by someone. A trivial example may be non-functional elements such as the response time of an API. A more subtle example might be consumers who are relying on applying a regex to an error message to determine the _type_ of error of an API. Even if the public contract of the API states nothing about the contents of the message, indicating users should use an associated error code, _some_ users may use the message, and changing the message essentially breaks the API for those users.

See also:

- [The Law of Leaky Abstractions](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [XKCD 1172](https://xkcd.com/1172/)

### Kernighan's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

> Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it.
>
> (Brian Kernighan)

Kernighan's Law is named for [Brian Kernighan](https://en.wikipedia.org/wiki/Brian_Kernighan) and derived from a quote from Kernighan and Plauger's book [The Elements of Programming Style](https://en.wikipedia.org/wiki/The_Elements_of_Programming_Style):

> Everyone knows that debugging is twice as hard as writing a program in the first place. So if you're as clever as you can be when you write it, how will you ever debug it?

While hyperbolic, Kernighan's Law makes the argument that simple code is to be preferred over complex code, because debugging any issues that arise in complex code may be costly or even infeasible.

See also:

- [The KISS Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [The Unix Philosophy](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Occam's Razor](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Linus's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Linus's Law on Wikipedia](https://en.wikipedia.org/wiki/Linus%27s_law)

> Given enough eyeballs, all bugs are shallow.
>
> _Eric S. Raymond_

This law simply states that the more people who can see a problem, the higher the likelihood that someone will have seen and solved the problem before, or something very similar.

Although it was originally used to describe the value of open-source models for projects it can be accepted for any kind of software project. It can also be extended to processes - more code reviews, more static analysis and multi-disciplined test processes will make the problems more visible and easy to identify.

A more formal statement can be:

> Given a large enough beta-tester and co-developer base, almost every problem will be characterized quickly and can be solved by someone who has encountered a similar problem before.

This law was named in honour of [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) in Eric S. Raymond's book "[The Cathedral and the Bazaar](https://en.wikipedia.org/wiki/The_Cathedral_and_the_Bazaar)".

### Metcalfe's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Metcalfe's Law on Wikipedia](https://en.wikipedia.org/wiki/Metcalfe's_law)

> In network theory, the value of a system grows as approximately the square of the number of users of the system.

This law is based on the number of possible pairwise connections within a system and is closely related to [Reed's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws). Odlyzko and others have argued that both Reed's Law and Metcalfe's Law overstate the value of the system by not accounting for the limits of human cognition on network effects; see [Dunbar's Number](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

See also:

- [Reed's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Dunbar's Number](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Moore's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Moore's Law on Wikipedia](https://en.wikipedia.org/wiki/Moore%27s_law)

> The number of transistors in an integrated circuit doubles approximately every two years.

Often used to illustrate the sheer speed at which semiconductor and chip technology has improved, Moore's prediction has proven to be highly accurate over from the 1970s to the late 2000s. In more recent years, the trend has changed slightly, partly due to [physical limitations on the degree to which components can be miniaturised](https://en.wikipedia.org/wiki/Quantum_tunnelling). However, advancements in parallelisation, and potentially revolutionary changes in semiconductor technology and quantum computing may mean that Moore's Law could continue to hold true for decades to come.

### Murphy's Law / Sod's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Murphy's Law on Wikipedia](https://en.wikipedia.org/wiki/Murphy%27s_law)

> Anything that can go wrong will go wrong.

Related to [Edward A. Murphy, Jr](https://en.wikipedia.org/wiki/Edward_A._Murphy_Jr.) _Murphy's Law_ states that if a thing can go wrong, it will go wrong.

This is a common adage among developers. Sometimes the unexpected happens when developing, testing or even in production. This can also be related to the (more common in British English) _Sod's Law_:

> If something can go wrong, it will, at the worst possible time.

These 'laws' are generally used in a comic sense. However, phenomena such as [_Confirmation Bias_](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) and [_Selection Bias_](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) can lead people to perhaps over-emphasise these laws (the majority of times when things work, they go unnoticed, failures however are more noticeable and draw more discussion).

See Also:

- [Confirmation Bias](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Selection Bias](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Occam's Razor

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Occam's Razor on Wikipedia](https://en.wikipedia.org/wiki/Occam's_razor)

> Entities should not be multiplied without necessity.
>
> William of Ockham

Occam's razor says that among several possible solutions, the most likely solution is the one with the least number of concepts and assumptions. This solution is the simplest and solves only the given problem, without introducing accidental complexity and possible negative consequences.

See also:

- [YAGNI](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [No Silver Bullet: Accidental Complexity and Essential Complexity](https://en.wikipedia.org/wiki/No_Silver_Bullet)

Example:

- [Lean Software Development: Eliminate Waste](https://en.wikipedia.org/wiki/Lean_software_development)

### Parkinson's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Parkinson's Law on Wikipedia](https://en.wikipedia.org/wiki/Parkinson%27s_law)

> Work expands so as to fill the time available for its completion.

In its original context, this Law was based on studies of bureaucracies. It may be pessimistically applied to software development initiatives, the theory being that teams will be inefficient until deadlines near, then rush to complete work by the deadline, thus making the actual deadline somewhat arbitrary.

If this law were combined with [Hofstadter's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws), an even more pessimistic viewpoint is reached - work will expand to fill the time available for its completion and _still take longer than expected_.

See also:

- [Hofstadter's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Premature Optimization Effect

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Premature Optimization on WikiWeb](http://wiki.c2.com/?PrematureOptimization)

> Premature optimization is the root of all evil.
>
> [(Donald Knuth)](https://twitter.com/realdonaldknuth?lang=en)

In Donald Knuth's paper [Structured Programming With Go To Statements](http://wiki.c2.com/?StructuredProgrammingWithGoToStatements), he wrote: "Programmers waste enormous amounts of time thinking about, or worrying about, the speed of noncritical parts of their programs, and these attempts at efficiency actually have a strong negative impact when debugging and maintenance are considered. We should forget about small efficiencies, say about 97% of the time: **premature optimization is the root of all evil**. Yet we should not pass up our opportunities in that critical 3%."

However, _Premature Optimization_ can be defined (in less loaded terms) as optimizing before we know that we need to.

### Putt's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Putt's Law on Wikipedia](https://en.wikipedia.org/wiki/Putt%27s_Law_and_the_Successful_Technocrat)

> Technology is dominated by two types of people, those who understand what they do not manage and those who manage what they do not understand.

Putt's Law is often followed by Putt's Corollary:

> Every technical hierarchy, in time, develops a competence inversion.

These statements suggest that due to various selection criteria and trends in how groups organise, there will be a number of skilled people at working levels of a technical organisations, and a number of people in managerial roles who are not aware of the complexities and challenges of the work they are managing. This can be due to phenomena such as [The Peter Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) or [The Dilbert Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

However, it should be stressed that Laws such as this are vast generalisations and may apply to _some_ types of organisations, and not apply to others.

See also:

- [The Peter Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [The Dilbert Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Reed's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Reed's Law on Wikipedia](https://en.wikipedia.org/wiki/Reed's_law)

> The utility of large networks, particularly social networks, scales exponentially with the size of the network.

This law is based on graph theory, where the utility scales as the number of possible sub-groups, which is faster than the number of participants or the number of possible pairwise connections. Odlyzko and others have argued that Reed's Law overstates the utility of the system by not accounting for the limits of human cognition on network effects; see [Dunbar's Number](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

See also:

- [Metcalfe's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Dunbar's Number](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Law of Conservation of Complexity (Tesler's Law)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Law of Conservation of Complexity on Wikipedia](https://en.wikipedia.org/wiki/Law_of_conservation_of_complexity)

This law states that there is a certain amount of complexity in a system which cannot be reduced.

Some complexity in a system is 'inadvertent'. It is a consequence of poor structure, mistakes, or just bad modeling of a problem to solve. Inadvertent complexity can be reduced (or eliminated). However, some complexity is 'intrinsic' as a consequence of the complexity inherent in the problem being solved. This complexity can be moved, but not eliminated.

One interesting element to this law is the suggestion that even by simplifying the entire system, the intrinsic complexity is not reduced, it is _moved to the user_, who must behave in a more complex way.

### The Law of Demeter

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Law of Demeter on Wikipedia](https://en.wikipedia.org/wiki/Law_of_Demeter)

> Don't talk to strangers.

The Law of Demeter, also known as "The Principle of Least Knowledge" is a principle for software design, particularly relevant in object orientated languages.

It states that a unit of software should talk only to its immediate collaborators. An object `A` with a reference to object `B` can call its methods, but if `B` has a reference to object `C`, `A` should not call `C`s methods. So, if `C` has a `doThing()` method, `A` should not invoke it directly; `B.getC().doThis()`.

Following this principal limits the scope of changes, making them easier and safer in future.

### The Law of Leaky Abstractions

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Law of Leaky Abstractions on Joel on Software](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/)

> All non-trivial abstractions, to some degree, are leaky.
>
> ([Joel Spolsky](https://twitter.com/spolsky))

This law states that abstractions, which are generally used in computing to simplify working with complicated systems, will in certain situations 'leak' elements of the underlying system, this making the abstraction behave in an unexpected way.

An example might be loading a file and reading its contents. The file system APIs are an _abstraction_ of the lower level kernel systems, which are themselves an abstraction over the physical processes relating to changing data on a magnetic platter (or flash memory for an SSD). In most cases, the abstraction of treating a file like a stream of binary data will work. However, for a magnetic drive, reading data sequentially will be _significantly_ faster than random access (due to increased overhead of page faults), but for an SSD drive, this overhead will not be present. Underlying details will need to be understood to deal with this case (for example, database index files are structured to reduce the overhead of random access), the abstraction 'leaks' implementation details the developer may need to be aware of.

The example above can become more complex when _more_ abstractions are introduced. The Linux operating system allows files to be accessed over a network but represented locally as 'normal' files. This abstraction will 'leak' if there are network failures. If a developer treats these files as 'normal' files, without considering the fact that they may be subject to network latency and failures, the solutions will be buggy.

The article describing the law suggests that an over-reliance on abstractions, combined with a poor understanding of the underlying processes, actually makes dealing with the problem at hand _more_ complex in some cases.

See also:

- [Hyrum's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Real-world examples:

- [Photoshop Slow Startup](https://forums.adobe.com/thread/376152) - an issue I encountered in the past. Photoshop would be slow to startup, sometimes taking minutes. It seems the issue was that on startup it reads some information about the current default printer. However, if that printer is actually a network printer, this could take an extremely long time. The _abstraction_ of a network printer being presented to the system similar to a local printer caused an issue for users in poor connectivity situations.

### The Law of the Instrument

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Law of the Instrument](https://en.wikipedia.org/wiki/Law_of_the_instrument)

> I call it the law of the instrument, and it may be formulated as follows: Give a small boy a hammer, and he will find that everything he encounters needs pounding.
>
> _Abraham Kaplan_

> If all you have is a hammer, everything looks like a nail.
>
> _Abraham Maslow_

In the context of computer programming, this law suggests that people tend to use tools that are familiar with, rather than the best possible tool. This over-reliance on a familiar tool is an anti-pattern referred to as 'the golden hammer'.

See also:

- [Avoiding the law of the instrument](https://josemdev.com/avoiding-the-law-of-the-instrument/)
- [Anti-Pattern - The Golden Hammer](https://archive.org/details/antipatternsrefa0000unse/page/111/mode/2up)

### The Law of Triviality

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Law of Triviality on Wikipedia](https://en.wikipedia.org/wiki/Law_of_triviality)

This law suggests that groups will give far more time and attention to trivial or cosmetic issues rather than serious and substantial ones.

The common fictional example used is that of a committee approving plans for nuclear power plant, who spend the majority of their time discussing the structure of the bike shed, rather than the far more important design for the power plant itself. It can be difficult to give valuable input on discussions about very large, complex topics without a high degree of subject matter expertise or preparation. However, people want to be seen to be contributing valuable input. Hence a tendency to focus too much time on small details, which can be reasoned about easily, but are not necessarily of particular importance.

The fictional example above led to the usage of the term 'Bike Shedding' as an expression for wasting time on trivial details. A related term is '[Yak Shaving](https://en.wiktionary.org/wiki/yak_shaving),' which connotes a seemingly irrelevant activity that is part of a long chain of prerequisites to the main task.

### The Unix Philosophy

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Unix Philosophy on Wikipedia](https://en.wikipedia.org/wiki/Unix_philosophy)

The Unix Philosophy is that software components should be small, and focused on doing one specific thing well. This can make it easier to build systems by composing together small, simple, well-defined units, rather than using large, complex, multi-purpose programs.

Modern practices like 'Microservice Architecture' can be thought of as an application of this law, where services are small, focused and do one specific thing, allowing complex behaviour to be composed of simple building blocks.

### The Scout Rule

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Scout Rule on O'Reilly](https://www.oreilly.com/library/view/97-things-every/9780596809515/ch08.html)

> Always leave the code better than you found it.
>
> (Robert C. Martin (Uncle Bob))

Based on the "Scout Rule", which is "always leave the campground cleaner than you found it", the Scout Rule in programming is simply "always leave the code cleaner than you found it".

This was introduced in the first chapter of the book [Clean Code](https://www.goodreads.com/book/show/3735293-clean-code) by Bob Martin. The rule suggests that developers should perform 'optimistic refactoring', which means to endeavour to improve the overall quality of the code when you work on it. If you see a mistake, attempt to fix it or clean it up. However, when making changes to code which seems incorrect, it may be worth remembering [Chesterton's Fence](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)!

See also:

- [Reading List: Clean Code](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Chesterton's Fence](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [The Broken Windows Theory](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[https://www.amazon.sg/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882](https://www.amazon.sg/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

### The Spotify Model

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Spotify Model on Spotify Labs](https://labs.spotify.com/2014/03/27/spotify-engineering-culture-part-1/)

The Spotify Model is an approach to team and organisation structure which has been popularised by 'Spotify'. In this model, teams are organised around features, rather than technologies.

The Spotify Model also popularises the concepts of Tribes, Guilds, Chapters, which are other components of their organisation structure.

Members of the organisation have described that the actual meaning of these groups changes, evolves and is an on-going experiment. The fact that the model is a _process in motion_, rather than a fixed model continues to lead to varying interpretations of the structure, which may be based on presentations given by employees at conferences. This means 'snapshots' may be 're-packaged' by third parties as a _fixed structure_, with the fact that the model is dynamic being lost.

### The Two Pizza Rule

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

> If you can't feed a team with two pizzas, it's too large.
>
> (Jeff Bezos)

This rule suggests that regardless of the size of the company, teams should be small enough to be fed by two pizzas. Attributed to Jeff Bezos and Amazon, this belief suggests that large teams are inherently inefficient. This is supported by the fact that as the team size increases linearly, the links between people increases quadratically; thus the cost of coordinating and communicating also grows quadratically. If this cost of coordination is essentially overhead, then smaller teams should be preferred.

The number of links between people can be expressed as `n(n-1)/2` where n = number of people.

[![IMG-20241106232536276.png](/img/user/_resources/IMG-20241106232536276.png)](https://github.com/dwmkerr/hacker-laws/blob/main/images/complete_graph.png)

### Wadler's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Wadler's Law on wiki.haskell.org](https://wiki.haskell.org/Wadler's_Law)

> In any language design, the total time spent discussing a feature in this list is proportional to two raised to the power of its position.
>
> 0. Semantics
> 1. Syntax
> 2. Lexical syntax
> 3. Lexical syntax of comments
>
> (In short, for every hour spent on semantics, 8 hours will be spent on the syntax of comments).

Similar to [The Law of Triviality](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws), Wadler's Law states what when designing a language, the amount of time spent on language structures is disproportionately high in comparison to the importance of those features.

See also:

- [The Law of Triviality](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Wheaton's Law

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Link](http://www.wheatonslaw.com/)

[The Official Day](https://dontbeadickday.com/)

> Don't be a dick.
>
> _Wil Wheaton_

Coined by Wil Wheaton (Star Trek: The Next Generation, The Big Bang Theory), this simple, concise, and powerful law aims for an increase in harmony and respect within a professional organization. It can be applied when speaking with coworkers, performing code reviews, countering other points of view, critiquing, and in general, most professional interactions humans have with each other.

## Principles

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Principles are generally more likely to be guidelines relating to design.

### All Models Are Wrong (George Box's Law)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[All Models Are Wrong](https://en.wikipedia.org/wiki/All_models_are_wrong)

> All models are wrong, but some are useful.
>
> _George Box_

This principle suggests that all models of systems are flawed, but that as long as they are not _too_ flawed they may be useful. This principle has its roots in statistics but applies to scientific and computing models as well.

A fundamental requirement of most software is to model a system of some kind. Regardless of whether the system being modeled is a computer network, a library, a graph of social connections or any other kind of system, the designer will have to decide an appropriate level of detail to model. Excessive detail may lead to too much complexity, too little detail may prevent the model from being functional.

See also:

- [The Law of Leaky Abstractions](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### Chesterton's Fence

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[Chesterton's Fence on Wikipedia](https://en.wikipedia.org/wiki/Wikipedia:Chesterton%27s_fence)

> Reforms should not be made until the reasoning behind the existing state of affairs is understood.

This principle is relevant in software engineering when removing technical debt. Each line of a program was originally written by someone for some reason. Chesterton's Fence suggests that one should try to understand the context and meaning of the code fully, before changing or removing it, even if at first glance it seems redundant or incorrect.

The name of this principle comes from a story by [G.K. Chesterton](https://en.wikipedia.org/wiki/G._K._Chesterton). A man comes across a fence crossing the middle of the road. He complains to the mayor that this useless fence is getting in the way, and asks to remove it. The mayor asks why the fence is there in the first place. When the man says he doesn't know, the mayor says, "If you don't know its purpose, I certainly won't let you remove it. Go and find out the use of it, and then I may let you destroy it."

### The Dead Sea Effect

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Dead Sea Effect on Bruce F. Webster](http://brucefwebster.com/2008/04/11/the-wetware-crisis-the-dead-sea-effect/)

> "... [T]he more talented and effective IT engineers are the ones most likely to leave - to evaporate ... [those who tend to] remain behind [are] the 'residue' — the least talented and effective IT engineers."
>
> _Bruce F. Webster_

The "Dead Sea Effect" suggests that in any organisation, the skills/talent/efficacy of engineers is often inversely proportional to their time in the company.

Typically, highly skilled engineers find it easy to gain employment elsewhere and are the first to do so. Engineers who have obsolete or weak skills will tend to remain with the company, as finding employment elsewhere is difficult. This is particularly pronounced if they have gained incremental pay rises over their time in the company, as it can be challenging to get equivalent remuneration elsewhere.

### The Dilbert Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Dilbert Principle on Wikipedia](https://en.wikipedia.org/wiki/Dilbert_principle)

> Companies tend to systematically promote incompetent employees to management to get them out of the workflow.
>
> _Scott Adams_

A management concept developed by Scott Adams (creator of the Dilbert comic strip), the Dilbert Principle is inspired by [The Peter Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws). Under the Dilbert Principle, employees who were never competent are promoted to management in order to limit the damage they can do. Adams first explained the principle in a 1995 Wall Street Journal article, and expanded upon it in his 1996 business book, [The Dilbert Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

See Also:

- [The Peter Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Putt's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Pareto Principle (The 80/20 Rule)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Pareto Principle on Wikipedia](https://en.wikipedia.org/wiki/Pareto_principle)

> Most things in life are not distributed evenly.

The Pareto Principle suggests that in some cases, the majority of results come from a minority of inputs:

- 80% of a certain piece of software can be written in 20% of the total allocated time (conversely, the hardest 20% of the code takes 80% of the time)
- 20% of the effort produces 80% of the result
- 20% of the work creates 80% of the revenue
- 20% of the bugs cause 80% of the crashes
- 20% of the features cause 80% of the usage

In the 1940s American-Romanian engineer Dr. Joseph Juran, who is widely credited with being the father of quality control, [began to apply the Pareto principle to quality issues](https://en.wikipedia.org/wiki/Joseph_M._Juran).

This principle is also known as: The 80/20 Rule, The Law of the Vital Few, and The Principle of Factor Sparsity.

Real-world examples:

- In 2002 Microsoft reported that by fixing the top 20% of the most-reported bugs, 80% of the related errors and crashes in windows and office would become eliminated ([Reference](https://www.crn.com/news/security/18821726/microsofts-ceo-80-20-rule-applies-to-bugs-not-just-features.htm)).

### The Shirky Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Shirky Principle explained](https://kk.org/thetechnium/the-shirky-prin/)

> Institutions will try to preserve the problem to which they are the solution.
>
> _Clay Shirky_

The Shirky Principle suggests that complex solutions - a company, an industry, or a technology - can become so focused on the problem that they are solving, that they can inadvertently perpetuate the problem itself. This may be deliberate (a company striving to find new nuances to a problem which justify continued development of a solution), or inadvertent (being unable or unwilling to accept or build a solution which solves the problem completely or obviates it).

Related to:

- Upton Sinclair's famous line, _"It is difficult to get a man to understand something, when his salary depends upon his not understanding it!"_
- Clay Christensen's _The Innovator's Dilemma_

See also:

- [Pareto Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Peter Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Peter Principle on Wikipedia](https://en.wikipedia.org/wiki/Peter_principle)

> People in a hierarchy tend to rise to their "level of incompetence".
>
> _Laurence J. Peter_

A management concept developed by Laurence J. Peter, the Peter Principle observes that people who are good at their jobs are promoted, until they reach a level where they are no longer successful (their "level of incompetence"). At this point, as they are more senior, they are less likely to be removed from the organisation (unless they perform spectacularly badly) and will continue to reside in a role which they have few intrinsic skills at, as their original skills which made them successful are not necessarily the skills required for their new jobs.

This is of particular interest to engineers - who initially start out in deeply technical roles, but often have a career path which leads to _managing_ other engineers - which requires a fundamentally different skill set.

See Also:

- [The Dilbert Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Putt's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Robustness Principle (Postel's Law)

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Robustness Principle on Wikipedia](https://en.wikipedia.org/wiki/Robustness_principle)

> Be conservative in what you do, be liberal in what you accept from others.

Often applied in server application development, this principle states that what you send to others should be as minimal and conformant as possible, but you should aim to allow non-conformant input if it can be processed.

The goal of this principle is to build systems which are robust, as they can handle poorly formed input if the intent can still be understood. However, there are potentially security implications of accepting malformed input, particularly if the processing of such input is not well tested. These implications and other issues are described by Eric Allman in [The Robustness Principle Reconsidered](https://queue.acm.org/detail.cfm?id=1999945).

Allowing non-conformant input, in time, may undermine the ability of protocols to evolve as implementors will eventually rely on this liberality to build their features.

See Also:

- [Hyrum's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### SOLID

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

This is an acronym, which refers to:

- S: [The Single Responsibility Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- O: [The Open/Closed Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- L: [The Liskov Substitution Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- I: [The Interface Segregation Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- D: [The Dependency Inversion Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

These are key principles in [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws). Design principles such as these should be able to aid developers build more maintainable systems.

### The Single Responsibility Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Single Responsibility Principle on Wikipedia](https://en.wikipedia.org/wiki/Single_responsibility_principle)

> Every module or class should have a single responsibility only.

The first of the '[SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)' principles. This principle suggests that modules or classes should do one thing and one thing only. In more practical terms, this means that a single, small change to a feature of a program should require a change in one component only. For example, changing how a password is validated for complexity should require a change in only one part of the program.

Theoretically, this should make the code more robust, and easier to change. Knowing that a component being changed has a single responsibility only means that _testing_ that change should be easier. Using the earlier example, changing the password complexity component should only be able to affect the features which relate to password complexity. It can be much more difficult to reason about the impact of a change to a component which has many responsibilities.

See also:

- [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Open/Closed Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Open/Closed Principle on Wikipedia](https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle)

> Entities should be open for extension and closed for modification.

The second of the '[SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)' principles. This principle states that entities (which could be classes, modules, functions and so on) should be able to have their behaviour _extended_, but that their _existing_ behaviour should not be able to be modified.

As a hypothetical example, imagine a module which is able to turn a Markdown document into HTML. Now imagine there is a new syntax added to the Markdown specification, which adds support for mathematical equations. The module should be _open to extension_ to implement the new mathematics syntax. However, existing syntax implementations (like paragraphs, bullets, etc) should be _closed for modification_. They already work, we don't want people to change them.

This principle has particular relevance for object-oriented programming, where we may design objects to be easily extended, but would avoid designing objects which can have their existing behaviour changed in unexpected ways.

See also:

- [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Liskov Substitution Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Liskov Substitution Principle on Wikipedia](https://en.wikipedia.org/wiki/Liskov_substitution_principle)

> It should be possible to replace a type with a subtype, without breaking the system.

The third of the '[SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)' principles. This principle states that if a component relies on a type, then it should be able to use subtypes of that type, without the system failing or having to know the details of what that subtype is.

As an example, imagine we have a method which reads an XML document from a structure which represents a file. If the method uses a base type 'file', then anything which derives from 'file' should be usable in the function. If 'file' supports seeking in reverse, and the XML parser uses that function, but the derived type 'network file' fails when reverse seeking is attempted, then the 'network file' would be violating the principle.

This principle has particular relevance for object-oriented programming, where type hierarchies must be modeled carefully to avoid confusing users of a system.

See also:

- [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Interface Segregation Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Interface Segregation Principle on Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle)

> No client should be forced to depend on methods it does not use.

The fourth of the '[SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)' principles. This principle states that consumers of a component should not depend on functions of that component which it doesn't actually use.

As an example, imagine we have a method which reads an XML document from a structure which represents a file. It only needs to read bytes, move forwards or move backwards in the file. If this method needs to be updated because an unrelated feature of the file structure changes (such as an update to the permissions model used to represent file security), then the principle has been invalidated. It would be better for the file to implement a 'seekable-stream' interface, and for the XML reader to use that.

This principle has particular relevance for object-oriented programming, where interfaces, hierarchies and abstract types are used to [minimise the coupling](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) between different components. [Duck typing](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) is a methodology which enforces this principle by eliminating explicit interfaces.

See also:

- [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Duck Typing](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Decoupling](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Dependency Inversion Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Dependency Inversion Principle on Wikipedia](https://en.wikipedia.org/wiki/Dependency_inversion_principle)

> High-level modules should not be dependent on low-level implementations.

The fifth of the '[SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)' principles. This principle states that higher-level orchestrating components should not have to know the details of their dependencies.

As an example, imagine we have a program which read metadata from a website. We would assume that the main component would have to know about a component to download the webpage content, then a component which can read the metadata. If we were to take dependency inversion into account, the main component would depend only on an abstract component which can fetch byte data, and then an abstract component which would be able to read metadata from a byte stream. The main component would not know about TCP/IP, HTTP, HTML, etc.

This principle is complex, as it can seem to 'invert' the expected dependencies of a system (hence the name). In practice, it also means that a separate orchestrating component must ensure the correct implementations of abstract types are used (e.g. in the previous example, _something_ must still provide the metadata reader component a HTTP file downloader and HTML meta tag reader). This then touches on patterns such as [Inversion of Control](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) and [Dependency Injection](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

See also:

- [Object-Oriented Programming](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [SOLID](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Inversion of Control](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)
- [Dependency Injection](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The DRY Principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The DRY Principle on Wikipedia](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

DRY is an acronym for _Don't Repeat Yourself_. This principle aims to help developers reducing the repetition of code and keep the information in a single place and was cited in 1999 by Andrew Hunt and Dave Thomas in the book [The Pragmatic Programmer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

> The opposite of DRY would be _WET_ (Write Everything Twice or We Enjoy Typing).

In practice, if you have the same piece of information in two (or more) different places, you can use DRY to merge them into a single one and reuse it wherever you want/need.

See also:

- [The Pragmatic Programmer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

### The KISS principle

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[KISS on Wikipedia](https://en.wikipedia.org/wiki/KISS_principle)

> Keep it simple, stupid

The KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore, simplicity should be a key goal in design, and unnecessary complexity should be avoided. Originating in the U.S. Navy in 1960, the phrase has been associated with aircraft engineer Kelly Johnson.

The principle is best exemplified by the story of Johnson handing a team of design engineers a handful of tools, with the challenge that the jet aircraft they were designing must be repairable by an average mechanic in the field under combat conditions with only these tools. Hence, the "stupid" refers to the relationship between the way things break and the sophistication of the tools available to repair them, not the capabilities of the engineers themselves.

See also:

- [Gall's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### YAGNI

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[YAGNI on Wikipedia](https://en.wikipedia.org/wiki/You_ain%27t_gonna_need_it)

This is an acronym for _**Y**ou **A**in't **G**onna **N**eed **I**t_.

> Always implement things when you actually need them, never when you just foresee that you need them.
>
> ([Ron Jeffries](https://twitter.com/RonJeffries)) (XP co-founder and author of the book "Extreme Programming Installed")

This _Extreme Programming_ (XP) principle suggests developers should only implement functionality that is needed for the immediate requirements, and avoid attempts to predict the future by implementing functionality that might be needed later.

Adhering to this principle should reduce the amount of unused code in the codebase, and avoid time and effort being wasted on functionality that brings no value.

See also:

- [Reading List: Extreme Programming Installed](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

### The Fallacies of Distributed Computing

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Fallacies of Distributed Computing on Wikipedia](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)

Also known as _Fallacies of Networked Computing_, the Fallacies are a list of conjectures (or beliefs) about distributed computing, which can lead to failures in software development. The assumptions are:

- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology doesn't change
- There is one administrator
- Transport cost is zero
- The network is homogeneous

The first four items were listed by [Bill Joy](https://en.wikipedia.org/wiki/Bill_Joy) and [Tom Lyon](https://twitter.com/aka_pugs) around 1991 and first classified by [James Gosling](https://en.wikipedia.org/wiki/James_Gosling) as the "Fallacies of Networked Computing". [L. Peter Deutsch](https://en.wikipedia.org/wiki/L._Peter_Deutsch) added the 5th, 6th and 7th fallacies. In the late 90's Gosling added the 8th fallacy.

The group was inspired by what was happening at the time inside [Sun Microsystems](https://en.wikipedia.org/wiki/Sun_Microsystems).

These fallacies should be considered carefully when designing code which is resilient; assuming any of these fallacies can lead to flawed logic which fails to deal with the realities and complexities of distributed systems.

See also:

- [Foraging for the Fallacies of Distributed Computing (Part 1) - Vaidehi Joshi on Medium](https://medium.com/baseds/foraging-for-the-fallacies-of-distributed-computing-part-1-1b35c3b85b53)

### The Principle of Least Astonishment

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

[The Principle of Least Astonishment on Wikipedia](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)

> People are part of the system. The design should match the user's experience, expectations, and mental models.
>
> Frans Kaashoek

This principle proposes that systems and interfaces should be designed in a way that features and functionality is easily discovered and matches users expectations. Features that 'surprise' users should be discouraged in favour of features that can be intuitively reasoned about based on existing patterns and practices.

Many examples are present in user interfaces, such as a 'pull down' gesture on a mobile appliation to refresh content. Another example would be command line tools, where many standards exist for how parameters are named, common parameters that should be available and so on.

See also:

- [Convention Over Configuration](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

## Reading List

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

If you have found these concepts interesting, you may enjoy the following books.

- [Clean Code - Robert C. Martin](https://www.goodreads.com/book/show/3735293-clean-code) - One of the most well respected books on how to write clean, maintainable code.
- [Extreme Programming Installed - Ron Jeffries, Ann Anderson, Chet Hendrikson](https://www.goodreads.com/en/book/show/67834) - Covers the core principles of Extreme Programming.
- [Gödel, Escher, Bach: An Eternal Golden Braid - Douglas R. Hofstadter.](https://www.goodreads.com/book/show/24113.G_del_Escher_Bach) - This book is difficult to classify. [Hofstadter's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) is from the book.
- [Structure and Interpretation of Computer Programs - Harold Abelson, Gerald Jay Sussman, Julie Sussman](https://www.goodreads.com/book/show/43713) - If you were a comp sci or electical engineering student at MIT or Cambridge this was your intro to programming. Widely reported as being a turning point in people's lives.
- [The Cathedral and the Bazaar - Eric S. Raymond](https://en.wikipedia.org/wiki/The_Cathedral_and_the_Bazaar) - a collection of essays on open source. This book was the source of [Linus's Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).
- [The Dilbert Principle - Scott Adams](https://www.goodreads.com/book/show/85574.The_Dilbert_Principle) - A comic look at corporate America, from the author who created the [Dilbert Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).
- [The Mythical Man Month - Frederick P. Brooks Jr.](https://www.goodreads.com/book/show/13629.The_Mythical_Man_Month) - A classic volume on software engineering. [Brooks' Law](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws) is a central theme of the book.
- [The Peter Principle - Lawrence J. Peter](https://www.goodreads.com/book/show/890728.The_Peter_Principle) - Another comic look at the challenges of larger organisations and people management, the source of [The Peter Principle](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws).

## Online Resources

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Some useful resources and reading.

- [CB Insights: 8 Laws Driving Success In Tech: Amazon's 2-Pizza Rule, The 80/20 Principle, & More](https://www.cbinsights.com/research/report/tech-laws-success-failure) - an interesting write up of some laws which have been highly influential in technology.

## PDF eBook

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

The project is available as a PDF eBook, [download the latest PDF eBook with this link](https://github.com/dwmkerr/hacker-laws/releases/latest/download/hacker-laws.pdf) or check the [release](https://github.com/dwmkerr/hacker-laws/releases) page for older versions.

A new version of the eBook is created automatically when a new version tag is pushed.

## Podcast

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Hacker Laws has been featured in [The Changelog](https://changelog.com/podcast/403), you can check out the Podcast episode with the link below:

[![IMG-20241106232536354.png](/img/user/_resources/IMG-20241106232536354.png)](https://changelog.com/podcast/403)

## Translations

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Thanks to a number of wonderful contributors, Hacker Laws is available in a number of languages. Please consider sponsoring moderators!

| Language                                                                                                   | Moderator                                                                                             | Status                                                                                     |
| ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [AR Arabic / Arabic](https://github.com/dwmkerr/hacker-laws/blob/main/translations/ar-AR.md)               | [Abdurrahman Rajab - a0m0rajab](https://github.com/a0m0rajab)                                         | .                                                                                          |
| [🇮🇩 Bahasa Indonesia / Indonesian](https://github.com/dwmkerr/hacker-laws/blob/main/translations/pt-BR.md) | [arywidiantara](https://github.com/arywidiantara)                                                     | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='119.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='119.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h28v20H91.5z'/>        <path fill='url(#b)' d='M0 0h119.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>id</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='180'>0%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/id?utm_source=badge)    |
| [🇧🇷 Brasileiro / Brazilian](https://github.com/dwmkerr/hacker-laws/blob/main/translations/pt-BR.md)        | [Eugênio Moreira](https://github.com/eugenioamn), [Leonardo Costa](https://github.com/leofc97)        | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='141.25' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='141.25' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h107.25v20H0z'/>        <path fill='#44CC11' d='M107.25 0h34v20H107.25z'/>        <path fill='url(#b)' d='M0 0h141.25v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>pt-BR</text>        <text x='1122.5' y='130' transform='scale(.1)'          textLength='240'>49%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/pt-BR?utm_source=badge) |
| [🇨🇳 中文 / Chinese](https://github.com/nusr/hacker-laws-zh)                                                | [Steve Xu](https://github.com/nusr)                                                                   | Partially complete                                                                         |
| [🇩🇪 Deutsch / German](https://github.com/dwmkerr/hacker-laws/blob/main/translations/de.md)                 | [Vikto](https://github.com/viktodergunov)                                                             | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='131.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='131.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h40v20H91.5z'/>        <path fill='url(#b)' d='M0 0h131.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>de</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='300'>100%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/de?utm_source=badge)    |
| [🇫🇷 Français / French](https://github.com/dwmkerr/hacker-laws/blob/main/translations/fr.md)                | [Kevin Bockelandt](https://github.com/KevinBockelandt)                                                | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='125.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='125.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h34v20H91.5z'/>        <path fill='url(#b)' d='M0 0h125.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>fr</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='240'>40%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/fr?utm_source=badge)    |
| [🇬🇷 ελληνικά / Greek](https://github.com/dwmkerr/hacker-laws/blob/main/translations/el.md)                 | [Panagiotis Gourgaris](https://github.com/0gap)                                                       | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='119.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='119.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h28v20H91.5z'/>        <path fill='url(#b)' d='M0 0h119.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>el</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='180'>0%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/el?utm_source=badge)    |
| [🇮🇹 Italiano / Italian](https://github.com/csparpa/hacker-laws-it)                                         | [Claudio Sparpaglione](https://github.com/csparpa)                                                    | Partially complete                                                                         |
| [🇯🇵 JP 日本語 / Japanese](https://github.com/dwmkerr/hacker-laws/blob/main/translations/jp.md)             | [Fumikazu Fujiwara](https://github.com/freddiefujiwara)                                               | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='119.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='119.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h28v20H91.5z'/>        <path fill='url(#b)' d='M0 0h119.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>ja</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='180'>0%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/ja?utm_source=badge)    |
| [🇰🇷 한국어 / Korean](https://github.com/codeanddonuts/hacker-laws-kr)                                      | [Doughnut](https://github.com/codeanddonuts)                                                          | Partially complete                                                                         |
| [🇱🇻 Latviešu Valoda / Latvian](https://github.com/dwmkerr/hacker-laws/blob/main/translations/lv.md)        | [Arturs Jansons](https://github.com/iegik)                                                            | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='119.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='119.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h28v20H91.5z'/>        <path fill='url(#b)' d='M0 0h119.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>lv</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='180'>0%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/lv?utm_source=badge)    |
| [🇵🇱 Polski / Polish](https://github.com/dwmkerr/hacker-laws/blob/main/translations/pl.md)                  | [Mariusz Kogen](https://github.com/k0gen)                                                             | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='91.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='91.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h0v20H91.5z'/>        <path fill='url(#b)' d='M0 0h91.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>pl</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='-100'>%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/pl?utm_source=badge)    |
| [🇷🇺 Русская версия / Russian](https://github.com/solarrust/hacker-laws)                                    | [Alena Batitskaya](https://github.com/solarrust)                                                      | Partially complete                                                                         |
| [🇪🇸 Castellano / Spanish](https://github.com/dwmkerr/hacker-laws/blob/main/translations/es-ES.md)          | [Manuel Rubio](https://github.com/manuel-rubio) ([Sponsor](https://github.com/sponsors/manuel-rubio)) | Partially complete                                                                         |
| [🇹🇷 Türkçe / Turkish](https://github.com/umutphp/hacker-laws-tr)                                           | [Umut Işık](https://github.com/umutphp)                                                               | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='125.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='125.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h34v20H91.5z'/>        <path fill='url(#b)' d='M0 0h125.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>tr</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='240'>82%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/tr?utm_source=badge)    |
| [🇺🇦 українська мова / Ukrainian](https://github.com/dwmkerr/hacker-laws/blob/main/translations/uk.md)      | [Nazar](https://github.com/troyane), [Helga Lastivka](https://github.com/HelgaLastivka)               | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='125.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='125.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h34v20H91.5z'/>        <path fill='url(#b)' d='M0 0h125.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>uk</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='240'>87%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/uk?utm_source=badge)    |
| [🇻🇳 Tiếng Việt / Vietnamese](https://github.com/dwmkerr/hacker-laws/blob/main/translations/vu.md)          | [Nguyên](https://github.com/truonghoangnguyen), [Trương Hoàng](https://github.com/truonghoangnguyen)  | [<svg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'      width='131.5' height='20' class='mdl-js'>      <linearGradient id='b' x2='0' y2='100%'>        <stop offset='0' stop-color='#bbb' stop-opacity='.1'/>        <stop offset='1' stop-opacity='.1'/>      </linearGradient>      <clipPath id='a'>        <rect width='131.5' height='20' rx='3' fill='#fff'/>      </clipPath>      <g clip-path='url(#a)'>        <path fill='#555' d='M0 0h91.5v20H0z'/>        <path fill='#44CC11' d='M91.5 0h40v20H91.5z'/>        <path fill='url(#b)' d='M0 0h131.5v20H0z'/>      </g>      <g fill='#fff' text-anchor='start'        font-family='DejaVu Sans,Verdana,Geneva,sans-serif' font-size='110'>        <text x='70' y='130' transform='scale(.1)'          textLength='600'>gitlocalized</text>        <text x='720' y='130'          fill='#FFCD19' transform='scale(.1)'>vi</text>        <text x='965.0' y='130' transform='scale(.1)'          textLength='300'>100%</text>      </g>    </svg>](https://gitlocalize.com/repo/2513/vi?utm_source=badge)    |

If you would like to update a translation, follow the [Translators Contributor Guide](https://github.com/dwmkerr/hacker-laws/blob/main/.github/contributing.md).

## Related Projects

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

- [Tip of the Day](https://tips.darekkay.com/html/hacker-laws-en.html) - Receive a daily hacker law/principle.
- [Hacker Laws CLI](https://github.com/umutphp/hacker-laws-cli) - List, view and see random laws from the terminal!
- [Hacker Laws Action](https://github.com/marketplace/actions/hacker-laws-action) - Adds a random Hacker Law to a pull request as a small gift for the contributor, thanks [Umut Işık](https://github.com/umutphp)

## Contributing

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Please do contribute! [Raise an issue](https://github.com/dwmkerr/hacker-laws/issues/new) if you'd like to suggest an addition or change, or [Open a pull request](https://github.com/dwmkerr/hacker-laws/compare) to propose your own changes.

Please be sure to read the [Contributing Guidelines](https://github.com/dwmkerr/hacker-laws/blob/main/.github/contributing.md) for requirements on text, style and so on. Please be aware of the [Code of Conduct](https://github.com/dwmkerr/hacker-laws/blob/main/.github/CODE_OF_CONDUCT.md) when engaging in discussions on the project.

## TODO

[](about:reader?url=https%3A%2F%2Fgithub.com%2Fdwmkerr%2Fhacker-laws)

Hi! If you land here, you've clicked on a link to a topic I've not written up yet, sorry about this - this is work in progress!

Feel free to [Raise an Issue](https://github.com/dwmkerr/hacker-laws/issues) requesting more details, or [Open a Pull Request](https://github.com/dwmkerr/hacker-laws/pulls) to submit your proposed definition of the topic.
