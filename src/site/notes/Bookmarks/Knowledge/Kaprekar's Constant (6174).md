---
{"dg-publish":true,"permalink":"/bookmarks/knowledge/kaprekar-s-constant-6174/","tags":["algorithm","explanation","interesting","learning","maths"]}
---


# [6174 - Wikipedia](https://en.wikipedia.org/wiki/6174)

**6174** (**six thousand, one hundred [and] seventy-four**) is the [natural number](https://en.wikipedia.org/wiki/Natural_number) following 6173 and preceding 6175.

## Kaprekar's constant

[[edit](https://en.wikipedia.org/w/index.php?title=6174&action=edit&section=1)]

6174 is known as Kaprekar's constant<sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-1"><span>[</span>1<span>]</span></a></sup><sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-Kaprekar1955-2"><span>[</span>2<span>]</span></a></sup><sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-Kaprekar1980-3"><span>[</span>3<span>]</span></a></sup> after the [Indian](https://en.wikipedia.org/wiki/India)[mathematician](https://en.wikipedia.org/wiki/Mathematician)[D. R. Kaprekar](https://en.wikipedia.org/wiki/D._R._Kaprekar). This number is renowned for the following rule:

1. Take any four-digit number, using at least two different digits (leading zeros are allowed).
2. Arrange the digits in descending and then in ascending order to get two four-digit numbers, adding leading zeros if necessary.
3. Subtract the smaller number from the bigger number.
4. Go back to step 2 and repeat.

The above process, known as [Kaprekar's routine](https://en.wikipedia.org/wiki/Kaprekar%27s_routine), will always reach its [fixed point](<https://en.wikipedia.org/wiki/Fixed_point_(mathematics)>), 6174, in at most 7 iterations.<sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-4"><span>[</span>4<span>]</span></a></sup> Once 6174 is reached, the process will continue yielding 7641 – 1467 = 6174. For example, choose 1459:

- 9541 – 1459 = 8082
- 8820 – 0288 = 8532
- 8532 – 2358 = 6174
- 7641 – 1467 = **6174**

The only four-digit numbers for which Kaprekar's routine does not reach 6174 are [repdigits](https://en.wikipedia.org/wiki/Repdigit) such as 1111, which give the result [0000](<https://en.wikipedia.org/wiki/0_(number)>) after a single iteration. All other four-digit numbers eventually reach 6174 if leading zeros are used to keep the number of digits at 4. For numbers with three identical digits and a fourth digit that is one higher or lower (such as 2111), it is essential to treat 3-digit numbers with a leading zero; for example: 2111 – 1112 = 0999; 9990 – 999 = 8991; 9981 – 1899 = 8082; 8820 – 288 = 8532; 8532 – 2358 = 6174.<sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-5"><span>[</span>5<span>]</span></a></sup>

## Other "Kaprekar's constants"

[[edit](https://en.wikipedia.org/w/index.php?title=6174&action=edit&section=2)]

There can be analogous fixed points for digit lengths other than four; for instance, if we use 3-digit numbers, then most sequences (i.e., other than repdigits such as 111) will terminate in the value [495](<https://en.wikipedia.org/wiki/495_(number)>) in at most 6 iterations. Sometimes these numbers (495, 6174, and their counterparts in other digit lengths or in bases other than 10) are called "Kaprekar constants".

Kaprekar's constant is often used in [cryptography](https://en.wikipedia.org/wiki/Cryptography) for the purpose of generating random numbers. Kaprekar's routine offers a way to arrive to completely random numbers which can be used for [decryption and encryption](https://en.wikipedia.org/wiki/Encryption). This technique is also often used to generate random prime numbers.

### Convergence analysis

[[edit](https://en.wikipedia.org/w/index.php?title=6174&action=edit&section=5)]

In [numerical analysis](https://en.wikipedia.org/wiki/Numerical_analysis), Kaprekar's constant can be used to analyze the [convergence of a variety numerical methods](https://en.wikipedia.org/wiki/Rate_of_convergence). Numerical methods are used in [engineering](https://en.wikipedia.org/wiki/Engineering), various forms of [calculus](https://en.wikipedia.org/wiki/Calculus), [coding](https://en.wikipedia.org/wiki/Computer_programming), and many other mathematical and scientific fields.

The properties of Kaprekar's routine allows for the study of [recursive functions](https://en.wikipedia.org/wiki/General_recursive_function), ones which repeat previous values and generating sequences based on these values. Kaprekar's routine is a recursive arithmetic sequence, so it helps study the properties of recursive functions. <sup><a href="https://en.wikipedia.org/wiki/6174#cite_note-6"><span>[</span>6<span>]</span></a></sup>

- 6174 is a 7-[smooth number](https://en.wikipedia.org/wiki/Smooth_number), i.e. none of its prime factors are greater than 7.
- 6174 can be written as the sum of the first three powers of 18:

  - 18<sup>3</sup> + 18<sup>2</sup> + 18<sup>1</sup> = 5832 + 324 + 18 = 6174, and coincidentally, 6 + 1 + 7 + 4 = 18.

- The sum of squares of the prime factors of 6174 is a square:
  - 2<sup>2</sup> + 3<sup>2</sup> + 3<sup>2</sup> + 7<sup>2</sup> + 7<sup>2</sup> + 7<sup>2</sup> = 4 + 9 + 9 + 49 + 49 + 49 = 169 = 13<sup>2</sup>
