---
{"dg-publish":true,"permalink":"/bookmarks/management-and-work-related/clever-code-is-probably-the-worst-code-you-could-write/","tags":["bestpractices","coding","interesting","technique"]}
---


[read.engineerscodex.com](https://read.engineerscodex.com/p/clever-code-is-probably-the-worst)

See also [[Bookmarks/Management and Work related/Work smarter, work slower\|Work smarter, work slower]] and in a sense [[Bookmarks/Booknotes/Summaries & Bits/Digital Minimalism - Choosing a Focused Life in a Noisy World\|Digital Minimalism - Choosing a Focused Life in a Noisy World]]

Engineer’s Codex

5–7 minutes

---

_Engineer’s Codex is a free publication about real-world software engineering. I write about real-world [technical case studies](https://engineercodex.substack.com/p/how-instagram-scaled-to-14-million), [outages](https://engineercodex.substack.com/p/how-one-line-of-code-caused-a-60), and [interesting stories](https://engineercodex.substack.com/p/how-to-burnout-a-software-engineer) from the industry._

When I was an undergrad, Leetcode broke my brain. I would see top solutions of esoteric one-liners and wrongly think “how do I ever get this good?”

This is commonly called “code golfing”. It’s a fun hobby, but very far from “good code.”

Everybody (including those on Leetcode) knows this isn’t good code. In the industry, it’s the worst code one could write.

Okay, I admit - this is a _pretty bad example of clever code_, _because it is so obviously bad. Here’s an example of a code snippet I came across in some old code that I found annoying:_

[

![IMG-20241106232535796.jpg](/img/user/_resources/IMG-20241106232535796.jpg)

](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4650fd1-cf7e-4d7b-94c9-cd121aff8864_1502x406.png)

However, on the other end of the spectrum, I realized eventually that the **clearest code was actually the hardest to write.**

It made sense retrospectively. Reviewing the code of a senior staff software engineer was much easier to follow and review compared to the code of an entry-level L3 engineer.

To be a top software engineer, you need to know a lot. But how do you know what you don't know? **[SWE Quiz](https://swequiz.com/?utm_source=codex) is a compilation of 450+ software engineering and system design questions covering databases, authentication, caching, etc.**

**They’ve been created by engineers from Google, Meta, Apple, and more.**

It’s helped many of my peers (including myself) pass the “software trivia questions” during interviews and feel more confident at work.

_For a brief period of time, SWE Quiz is available for lifetime access._

[Get Lifetime Access to SWE Quiz](https://swequiz.com/)

> _"Debugging code is twice as hard as writing the code in the first place. Therefore, if you write code as cleverly as possible, you are, by definition not smart enough to debug it."_
>
> _-_ Brian W. Kernighan

The “power” of clear code, for better or for worse, was made fully clear to me after a certain incident at work.

I once wrote a module in C++, a language that is a bit harder to read compared to other languages simply due to its verbosity.

I started with just two files (.h/.cpp) and all the implementation code went into just these two files.

The result was this giant, disgusting piece of spaghetti on the inside, but a perfectly working program on the outside.

This would _never_ get past code review.

I split the implementation into 8-10 diffs. Each diff was a neat, containerized piece of code, with convenient placeholders for dependencies that would arrive in a later diff. It had code neatly split out into helper functions and helper files when necessary.

Each diff had reasonable unit test coverage - the basics and some obvious edge cases were covered, but I didn’t go wastefully overboard with it.

Each diff also took me quite a few iterations of “code cleaning,” refactoring, and more. **It took a lot more effort than I expected to achieve “clear code,” especially for such a large program.**

The result? _A beautiful landing of the module, with easy to read, clear code._

While I was proud of it, there was suddenly a **problem** when I talked to my manager about it.

> “While I understand how complex this was, when it comes to performance reviews, this code looks trivial. It looks too easy, too simple.
>
> I would recommend writing an implementation doc of this module just so we can demonstrate that this was actually quite complex.”

I was shocked - this wasn’t some startup. This was one of the biggest companies in the world, _known for their engineering culture_.

I now understood why Big Tech seemingly had so many docs — half of the docs I wrote didn’t _need_ to be written, except they did… because I wanted to get raises and be promoted.

While promotion culture in Big Tech is a story for another article (subscribe to see it in your inbox soon 🙂), the main point here is that **great code is very clear and readable.**

There’s a [popular saying](https://github.com/dwmkerr/hacker-laws) that **debugging code is twice as hard as writing it**. It’s the reason why when ChatGPT outputs some hogwash, it’s easier just to re-prompt it or write it from scratch yourself instead of trying to figure out the errors in its buggy code.

> Clever code is harder to read and looks esoteric.
>
> Clear code is harder to write and looks easy.

- The only way I got better at writing clear, readable code was just **writing a lot of code while strictly following a clear style guide.**
  - Also, having more experienced devs review my code with a magnifying glass.
    - It was agony to get tons of comments and “nits” about seemingly pointless style in the beginning, but it paid off in the end.
- Coding style is **more important** than I expected in the beginning. My start to software engineering started from being on the product-minded end of the spectrum and moved towards the “technical-minded” side of the spectrum. 
  - I had started coding solely to start a business, so I initially only cared about code as a tool, resulting in crappy, unmaintainable code.
  - It’s only through more experience with writing code and working within teams that the importance of clear, readable code became more obvious.
  - It’s not just me. This is an obvious revelation to anybody who has been writing code in the industry for more than a year.
- **[John Carmack once wrote a long email about coding style in 2007, which is an interesting read.](http://number-none.com/blow/john_carmack_on_inlined_code.html)**
- [Google probably has the most public style guide](https://engineercodex.substack.com/p/how-google-writes-clean-maintainable). Vercel also recently released their [style guide](https://github.com/vercel/style-guide?utm_source=tldrwebdev), and pretty much every company uses some sort of linter and prettifier.
