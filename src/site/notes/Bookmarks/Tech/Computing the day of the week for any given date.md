---
{"dg-publish":true,"permalink":"/bookmarks/tech/computing-the-day-of-the-week-for-any-given-date/","tags":["coding","halloffame","history","interesting","technique","tools"]}
---


[futilitycloset.com](https://www.futilitycloset.com/2024/05/24/day-tripper/)

# Day Tripper - Futility Closet

Greg Ross

3–4 minutes

---

A letter from Lewis Carroll to [_Nature_](https://www.nature.com/articles/035517a0), March 31, 1887:

> Having hit upon the following method of mentally computing the day of the week for any given date, I send it you in the hope that it may interest some of your readers. I am not a rapid computer myself, and as I find my average time for doing any such question is about 20 seconds, I have little doubt that a rapid computer would not need 15.
>
> Take the given date in 4 portions, viz. the number of centuries, the number of years over, the month, the day of the month.
>
> Compute the following 4 items, adding each, when found, to the total of the previous items. When an item or total exceeds 7, divide by 7, and keep the remainder only.
>
> _The Century-Item._ — For Old Style (which ended September 2, 1752) subtract from 18. For New Style (which began September 14) divide by 4, take overplus from 3, multiply remainder by 2. [The Century-Item is the first two digits of the year, so for 1811 take 18.]
>
> _The Year-Item._ — Add together the number of dozens, the overplus, and the number of 4’s in the overplus.
>
> _The Month-Item._ — If it begins or ends with a vowel, subtract the number, denoting its place in the year, from 10. This, plus its number of days, gives the item for the following month. The item for January is ‘0’; for February or March (the 3rd month), ‘3’; for December (the 12th month), ’12.’ [So, for clarity, the required final numbers after division by 7 are January, 0; February, 3; March, 3; April, 6; May, 1; June, 4; July, 6; August 2; September, 5; October, 0; November, 3; and December, 5.]
>
> _The Day-Item_ is the day of the month.
>
> The total, thus reached, must be corrected, by deducting ‘1’ (first adding 7, if the total be ‘0’), if the date be January or February in a Leap Year: remembering that every year, divisible by 4, is a Leap Year, excepting only the century-years, in New Style, when the number of centuries is _not_ so divisible (_e.g._ 1800).
>
> The final result gives the day of the week, ‘0’ meaning Sunday, ‘1’ Monday, and so on.
>
> Examples
>
> 1783, _September_ 18
>
> 17, divided by 4, leaves ‘1’ over; 1 from 3 gives ‘2’; twice 2 is ‘4.’
>
> 83 is 6 dozen and 11, giving 17; plus 2 gives 19, _i.e._ (dividing by 7) ‘5.’ Total 9, _i.e._ ‘2.’
>
> The item for August is ‘8 from 10,’ _i.e._ ‘2’; so, for September, it is ‘2 plus 3,’ _i.e._ ‘5.’ Total 7, _i.e._ ‘0,’ which goes out.
>
> 18 gives ‘4.’ Answer, _‘Thursday.’_
>
> 1676, _February_ 23
>
> 16 from 18 gives ‘2.’
>
> 76 is 6 dozen and 4, giving 10; plus 1 gives 11, _i.e._ ‘4.’ Total ‘6.’
>
> The item for February is ‘3.’ Total 9, _i.e._ ‘2.’
>
> 23 gives ‘2.’ Total ‘4.’
>
> Correction for Leap Year gives ‘3.’ Answer, _‘Wednesday.’_

(Via Edward Wakeling, [_Rediscovered Lewis Carroll Puzzles_](https://archive.org/details/rediscoveredlewi00carr/page/10/mode/2up), 1995.)
