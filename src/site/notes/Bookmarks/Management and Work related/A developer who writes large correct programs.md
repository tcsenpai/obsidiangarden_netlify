---
{"dg-publish":true,"permalink":"/bookmarks/management-and-work-related/a-developer-who-writes-large-correct-programs/","tags":["bias","coding","lifehack","productivity","work"]}
---


See also [[Bookmarks/Management and Work related/Work smarter, work slower\|Work smarter, work slower]], [[Bookmarks/Management and Work related/Use A Work Journal To Recover Focus Faster And Clarify Your Thoughts\|Use A Work Journal To Recover Focus Faster And Clarify Your Thoughts]] and [[Bookmarks/Management and Work related/Clever code is probably the worst code you could write\|Clever code is probably the worst code you could write]]

## Post

I had a conversation yesterday with someone who said he needed to hire a computer scientist. I replied that actually he needed to hire someone who could program, and that not all computer scientists could program. He disagreed, but I stood by my statement. I’ve known too many people with computer science degrees, even advanced degrees, who were ineffective software developers. Of course I’ve also known people with computer science degrees, especially advanced degrees, that were terrific software developers. The most I’ll say is that programming ability is positively correlated with computer science achievement.

The conversation turned to what it means to say someone can program. My proposed definition was **someone who could write large programs that have a high probability of being correct**. Joel Spolsky wrote a good book last year called [Smart and Gets Things Done](https://amzn.to/2U7Kh5w) about recruiting great programmers. I agree with looking for someone who is “smart and gets things done,” but “writes large correct programs” may be easier to explain. The two ideas overlap a great deal.

People who are not professional programmers often don’t realize how the difficulty of writing software increases with size. Many people who wrote 100-line programs in college imagine that they could write 1,000-line programs if they worked at it 10 times longer. Or even worse, they imagine they could write 10,000-line programs if they worked 100 times longer. **It doesn’t work that way**. Most people who can write a 100-line program could never finish a 10,000-line program no matter how long they worked on it. They would simply drown in complexity.  One of the marks of a professional programmer is knowing how to organize software so that the complexity remains manageable as the size increases.  Even among professionals there are large differences in ability. The programmers who can effectively manage 100,000-line projects are in a different league than those who can manage 10,000-line projects.

(When I talk about a program that is so many lines long, I mean a program that [needs to be about that long](https://www.johndcook.com/blog/2008/08/26/different-kinds-of-software-complexity/). It’s no achievement to write 1,000 [lines of code](https://www.johndcook.com/blog/2008/06/03/experienced-programmers-and-lines-of-code/) for a problem that would be reasonable to solve in 10.)

**Writing large buggy programs is hard**. To say a program is buggy is to imply that it is at least of sufficient quality to approximate what it’s supposed to do much of the time. For example, you wouldn’t say that Notepad is a buggy web browser. A program has got to display web pages at least occasionally to be called a buggy browser.

**Writing large correct programs is much harder**. It’s even impossible, depending on what you mean by “large” and “correct.” No large program is completely bug-free, but some large programs have a very small probability of failure. The best programmers can think of a dozen ways to solve any problem, and they choose the way they believe has the best chance of being implemented correctly. Or they choose the way that is most likely to make an error obvious if it does occur. They know that software needs to be tested and they design their software to make it easier to test.

If you ask an amateur whether their program is correct, they are likely to be offended. They’ll tell you that of course it’s correct because they were careful when they wrote it. If you ask a professional the same question, they may tell you that their program probably has bugs, but then go on to tell you how they’ve tested it and what logging facilities are in place to help debug errors when they show up later.
