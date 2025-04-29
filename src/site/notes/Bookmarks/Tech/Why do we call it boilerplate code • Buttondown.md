---
{"dg-publish":true,"permalink":"/bookmarks/tech/why-do-we-call-it-boilerplate-code-buttondown/","tags":["coding","dev","history","interesting","internet","writing"]}
---


November 14, 2022

## Etymology is fun!

Now that Twitter is on a downward spiral I'm rewriting my favorite tweetstorms in a more permanent medium, so here's the first: why do we have the term "boilerplate code"? It comes from the peculiar interplay of two industrial revolution technologies: steam engines and hot metal typesetting.

So let's start with the steam engine. Steam engines run on steam, produced by a water boiler. The hotter you can get the steam, the more efficiently you can extract energy from it. Now according to the ideal gas law, if you increase the temperature of a gas while holding the volume constant, you'll also increase the pressure. If the boiler can't handle the pressure, it explodes. This is a bad thing.

![13c97634b50f7f8330748077bd444a95_MD5.gif](/img/user/_resources/Why%20do%20we%20call%20it%20boilerplate%20code%20%E2%80%A2%20Buttondown/13c97634b50f7f8330748077bd444a95_MD5.gif)An exploding water boiler

A _lot_ goes into boiler engineering, but the relevant thing here is that boilers need to be uniformly cylindrical. If the boiler has sharp angles, or if the boiler wall is thinner in one place, then Bad Thing is more likely. Fortunately, there was a well-established method of producing large, flat sheets of metal with uniform thickness: [rolling](<https://en.wikipedia.org/wiki/Rolling_(metalworking)>). Boilermakers started buying vast quantities of cast iron from rolling mills, so large rolled sheets came to be called "boiler plate".

(We know this was a contemporary term because the [1862 Union navy contract](https://www.google.com/books/edition/Message_from_the_President_of_the_United/KQlFAQAAMAAJ?hl=en&gbpv=1&dq=boilerplate&pg=PA837) includes ~600 "sheets boiler iron".)

Now for the Linotype. Up until the late 19th century, all printing presses were typeset manually. To print a letter, the printer would select a corresponding metal slug and manually place it in the press. Once you had a full set you could print a lot of very high quality papers, which ameliorated the cost of all that manual labor. But for text that changes rapidly— like daily news— the manual overhead is too high.

The linotype machine (1884) solved this problem by introducing "hot metal typesetting". It's a sort of mechanical typewriter that could automatically slot letter _molds_ into a matrix, instead of metal _slugs_. When you finished typesetting you then poured molten lead over the mold to create a single giant letterpress. Once you were done printing with the letterpress you could melt it back down into base material and reuse it for another mold.

The tradeoff is you can layout a typeset by typing it instead of by manually moving slugs around, but you get a lower quality typeset. Bad if you're trying to do a 200,000 book print run, great if you just want to send off a couple thousand newsletters. Here's what one of those typesets looked like:

![d0ef8a476378d71bc79e29d3c77ab1a6_MD5.jpg](/img/user/_resources/Why%20do%20we%20call%20it%20boilerplate%20code%20%E2%80%A2%20Buttondown/d0ef8a476378d71bc79e29d3c77ab1a6_MD5.jpg)A stack of linotype slugs, from https://collection.sciencemuseumgroup.org.uk/objects/co38444/nine-linotype-slugs-text-beginning-what-is-a-livery-company

From a top down view, it looks like a sheet of boiler plate. From the side it's a lot thicker; I'll discuss that later.

But where does it get the meaning of being "uncreative" copy-paste code? That's due to one more advantage of hot metal typesetting: you can make multiple typesets from the same mold. So you could write an article and send it to a bunch of small newspapers, who'd all cut up the slugs and fit the stories around their other articles.

And now we have newspaper syndication! Syndication is a little older than that, but it only really took off after hot metal typesetting. Syndicated columns were designed to be as bland and inoffensive as possible, so as to be palatable to the largest possible audience. So "boilerplate" became slang for vapid syndicated articles.

(Not all linotype slugs were "boilerplate": even if you're just making slugs for your own printing, hot metal typesetting is _much_ faster than manual lettering, so most newsrooms had a linotype. I suspect that syndicates would only mail the front couple inches of the slug to save on materials and postage. So syndicate slugs would be much thinner than local slugs, and would look more like boilerplate.)

Anyway, the earliest reference to "boilerplate" as slang (I could find) is this [1894 story in _Our Paper_](https://www.google.com/books/edition/Our_Paper/5oFRAAAAYAAJ?hl=en&gbpv=1&pg=PA670&printsec=frontcover), a Massachussetts prison newsletter. The author says that because of boilerplate, "brains have been at a discount" and "the editorial needs have chiefly been a strong right arm and an axe", so pretty negative opinion overall. Then again, the author is listed as "-Advertiser", so it might have been a boilerplate story, too! This is all within ten years of the linotype, which shows just how widespread both the tool and the slang was in printing culture.

It shortly after hops from journalism to law: a "boilerplate clause" is a general clause that's just thrown into a lot of contracts out of habit.<sup id="fnref:asis"><a href="https://buttondown.com/hillelwayne/archive/why-do-we-call-it-boilerplate-code?ref=dailydev#fn:asis">1</a></sup> I found one reference to this in 1902, but it's definitely widespread by 1940. In law it becomes an actual term as opposed to just slang. The first reference to boilerplate _code_ is from a [1981 report on COBOL compilers](https://dl.acm.org/doi/10.1145/1500412.1500463), which follows the law definition.

> First, there is what can be called boilerplate source code. This code is present in each of the validation routines and is generally the same in each routine.

They don't explicitly define _why_ it's called "boilerplate", which I can only assume is because the term was common knowledge enough in other fields and they didn't see a need to give an etymology.

And that's the history of the term! RIP Twitter

---

### Update for the Internets

This was sent as part of an email newsletter; you can subscribe [here](https://buttondown.email/hillelwayne/). Common topics are [software history](https://buttondown.email/hillelwayne/archive/why-uml-really-died/), [formal methods](https://buttondown.email/hillelwayne/archive/10-misconceptions-about-formal-methods/), the [theory of software engineering](https://buttondown.email/hillelwayne/archive/reject-simplicity-embrace-complexity/), and [silly research dives](https://buttondown.email/hillelwayne/archive/whats-the-most-expensive-software-per-byte/). Updates are usually 1x a week. I also have a [website](https://www.hillelwayne.com/) where I put my polished writing (the newsletter is more for off-the-cuff stuff).

_If you're reading this on the web, you can subscribe [here](https://buttondown.com/hillelwayne). Updates are once a week. My main website is [here](https://www.hillelwayne.com/)._

_My new book,_ Logic for Programmers*, is now in early access! Get it [here](https://leanpub.com/logic/).*
