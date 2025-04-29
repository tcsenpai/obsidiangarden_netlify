---
{"dg-publish":true,"permalink":"/bookmarks/management-and-work-related/against-best-practices/","tags":["bestpractices","ideas","interesting","lifehack"]}
---


# [Against best practices](https://www.arp242.net/best-practices.html)

See also [[Bookmarks/Health, Mind and so on/Trade-offs\|Trade-offs]], [[Bookmarks/Management and Work related/Work smarter, work slower\|Work smarter, work slower]], [[Bookmarks/Management and Work related/Clever code is probably the worst code you could write\|Clever code is probably the worst code you could write]]

I have come to believe that by and large “best practices” are doing more harm
than good. Not necessarily because they’re bad advice as such, but because
they’re mostly pounded by either 1) various types of zealots, idiots, and
assholes who abuse these kind of “best practices” as an argument from authority,
or 2) inexperienced programmers who lack the ability to judge the applicability,

Everyone else just says “X is better because Y”. This is an actual argument that
can be engaged with, and engaging with actual arguments is what discovers the
best solution for the situation at hand.

This is not unique to programming; even the best of ideas becomes silly once you
start uncritically applying it to everything – one can find many examples in
politics. There, too, it’s mostly pounded by various types of zealots, idiots,
and assholes.

---

All of this doesn’t mean that “best practice” are bad advice. Many are worth
reading, and some should always be followed. But many are little more “this
thing someone said” and/or “just someone’s opinion”.

Take Postel’s “law” – what if I break this “law”? Will the police come and
arrest me? Will I get the Nobel prize in physics as I’ve discovered new laws of
nature? It’s not a “law” in any meaningful sense: it’s just a thing this Postel
guy said in 1980, which may or may not be applicable to whatever you’re doing.

_Postel’s quip_ was probably good advice in 1980 in the context of TCP. There
were tons of little incompatibilities between existing implementations and
Postel was working on the first effort to actually standardize it all. Back then
it was typically harder to write fully correct implementations (no internet with
tons of examples, little to no testing, less access to other implementations,
etc.)

There are other cases where it’s the reasonable and practical thing to do. But
as a general concept applied to all protocols or all software development I find
it’s mostly a bad idea. I’m hardly the first to critique it, and it’s been
controversial for decades.

In spite of that, people citing _Postel’s quip_ as if it’s somehow a “law” are
still plentiful. My law is that everyone who does so is an idiot, asshole, or
some combination of both.

There are many more examples:

- “Don’t use globals” is obviously good, but “never use globals under any
  circumstances” is just silly. I’ve seen people throw a hissy fit over
  “globals” in simple CLI tools with a few functions. Whoop-dee-doo.

- “Don’t use unstructured GOTO” has turned into “never use goto”, “don’t use
  continue because it’s like a hidden goto”, and “use single point of exit”, and
  that kind of absolute insane bollocks.

- “Don’t Repeat Yourself” (DRY) is basically good advice, but sometimes just
  copy/pasting things is just the more pragmatic thing to do, and not really a
  big deal.

- I think “12 factor app” has some okay ideas, some dubious ideas, and some
  outright bad ideas.

- While the basic ideas of “SOLID” are okay, I generally find that strong
  adherence does not lead to particularly good code. It’s typically 80% fucking
  about with _how_ to do things, and 20% actually doing the stuff you want to do
  (which makes things harder to understand and change, not easier).

- etc. etc. etc.

You can disagree with any of the above, and that’s fine. But citing “laws” or
“best practices” are just a fallacious arguments from authority.

---

One of the difficulties with argueing against “best practices” is that it often
goes something like this:

- _“X is not according to best practices”_

- _“I think X is better because Y”_

- _“But it’s not following best practice Z! Here is a book about it! Why don’t
  you follow it?! Do you want to write bad code?!”_

There is kind of a gaslighting effect here, because it’s very natural to assume
that maybe you _should_ be following the “best practice”, especially when
declared with great arrogance.

This is the same fallacious argument people use for safety:

- _“I don’t X will improve safety.”_

- _“What?! You don’t care about safety?!”_
- or: _“Better safe than sorry!”_

Which is why safety regulation only grows and never shrinks, even when the
regulation just makes no sense eat all: arguing against it is hard, because the
look of things is against you. I call this the _Safety Fallacy_.
