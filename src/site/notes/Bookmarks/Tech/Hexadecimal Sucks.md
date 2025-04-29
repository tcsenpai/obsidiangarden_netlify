---
{"dg-publish":true,"permalink":"/bookmarks/tech/hexadecimal-sucks/","tags":["algorithm","coding","memory","wiki"]}
---


# [Hexadecimal Sucks - Tyler Cipriani](https://tylercipriani.com/blog/2024/05/31/hexadecimal-sucks/)

- [What’s the problem?]()
- [Memory chunking and sha256]()

> Humans do no operate on hexadecimal symbols effectively […] there are
> exceptions.
>
> – Dan Kaminsky

When [SSH
added ASCII art fingerprints](https://marc.info/?l=openbsd-cvs&m=121321826818823&w=2) (AKA, randomart), the author credited a
talk by [Dan
Kaminsky](https://en.wikipedia.org/wiki/Dan_Kaminsky).

As a refresher, randomart looks like this:

```
$ ssh-keygen -lv -f ~/.ssh/id_ed25519.pub
256 SHA256:XrvNnhQuG1ObprgdtPiqIGXUAsHT71SKh9/WAcAKoS0 thcipriani@foo.bar (ED25519)
+--[ED25519 256]--+
| .++ ...         |
| o+.... o        |
|E .oo=.o .       |
| . .+.=   .      |
|    o= .S.o.o    |
|   o  o.o+.= +   |
|  . .  .o B *    |
|   . .   + & .   |
|      ..+o*.=    |
+----[SHA256]-----+
```

Ben Cox describes the algorithm for generating random art on [his
blog](https://blog.benjojo.co.uk/post/ssh-randomart-how-does-it-work-art). Here’s a slo-mo version of the algorithm in action:

![fffce49e318d8844f793c779bca75538_MD5 1.gif](/img/user/_resources/fffce49e318d8844f793c779bca75538_MD5%201.gif)ASCII art ssh fingerprints slo-mo algorithm

But in [Dan’s
talk](https://www.youtube.com/watch?v=QT2hOyK2qv4&list=WL&t=599s), he never mentions anything about ASCII art.

Instead, his talk was about **exploiting our brain’s hardware
acceleration** to make it easier for us to recognize SSH
fingerprints.

The talk is worth watching, but I’ll attempt a summary.

## What’s the problem?

We’ll never memorize`SHA256:XrvNnhQuG1ObprgdtPiqIGXUAsHT71SKh9/WAcAKoS0`—hexadecimal
and base64 were built to encode large amounts of information rather than
be easy to remember.

But that’s ok for SSH keys because there are different kinds of
memory:

- **Rejection**: I’ve never seen that before!
- **Recognition**: I know it’s that one—not the other
  one.
- **Recollection**: rote recall, like a phone number or
  address.

For SSH you’ll use **recognition**—do you recognize this
key? Of course, SSH keys are still a problem because our working memory
is too small to recognize such long strings of letters and numbers.

Hacks abound to shore up our paltry working memory—what Dan called
“brain hardware acceleration.”

Randomart attempts to tap into our hardware acceleration for pattern
recognition—the [visiuo-spacial
sketchpad](https://en.wikipedia.org/wiki/Baddeley's_model_of_working_memory), where we store pictures.

Dan’s idea tapped into a different aspect of hardware acceleration,
one often cited by memory competition champions: [chunking](<https://en.wikipedia.org/wiki/Chunking_(psychology)>).

## Memory chunking and sha256

The web service [what3words](https://what3words.com/) maps
every three cubic meters (3m²) on Earth to three words.

The White House’s Oval Office is [///curve.empty.buzz](https://what3words.com/curve.empty.buzz).

Three words encode the same information as latitude and
longitude—`38.89`, `-77.03`—chunking the
information to be small enough to fit in our working memory.

The mapping of locations to words uses a list of 40 thousand common
English words, so each word encodes 15.29 bits of information—45.9 bits
of information, identifying 64 trillion unique places.

Meanwhile sha256 is 256 bits of information: \~116 quindecillion
unique combinations.

```
                                                                64000000000000 # 64 trillion (what3words)
115792089237316195423570985008687907853269984665640564039457584007913129639936 # 116 (ish) quindecillion (sha256)
```

For SHA256, we need more than three words or a dictionary larger than
40,000 words.

Dan’s insight was we can identify SSH fingerprints using pairs of
human names—couples.

The math works like this:

- 131,072 first names: 17 bits per name (×2)
- 524,288 last names: 19 bits per name
- 2,048 cities: 11 bits per city
- 17+17+19+11 = 64 bits

With 64 bits per couple, you could uniquely identify 116
quindecillion items with four couples.

Turning this:

```
$ ssh foo.bar
The authenticity of host 'foo.bar' can't be established.
ED25519 key fingerprint is SHA256:XrvNnhQuG1ObprgdtPiqIGXUAsHT71SKh9/WAcAKoS0.
Are you sure you want to continue connecting
(yes/no/[fingerprint])?
```

Into this:

```
$ ssh foo.bar
The authenticity of host 'foo.bar' can't be established.
SHA256:XrvNnhQuG1ObprgdtPiqIGXUAsHT71SKh9/WAcAKoS0
Key Data:
    Svasse and Tainen Jesudasson from Fort Wayne, Indiana, United States
    Illma and Sibeth Primack from Itārsi, Madhya Pradesh, India
    Maarja and Nisim Balyeat from Mukilteo, Washington, United States
    Hsu-Heng and Rasim Haozi from Manali, Tamil Nadu, India
Are you sure you want to continue connecting
(yes/no/[fingerprint])?
```

With enough exposure, building recognition for these names and places
should be possible—at least more possible than memorizing host keys.
