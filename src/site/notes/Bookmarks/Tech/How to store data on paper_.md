---
{"dg-publish":true,"permalink":"/bookmarks/tech/how-to-store-data-on-paper/","tags":["interesting","wow","internet","art","algorithm"]}
---

How to print my voice? How to put music on paper? How to print an executable program? All this boils down to storing digital data on paper. This is also called [paper data storage](https://en.wikipedia.org/wiki/Paper_data_storage). Arrived in this domain from poetry, I’ve been investigating the area for some time. Here is what I found.

## What to print on paper?

[![_resources/Untitled 1/9e2303582f8661b77607d9a599270772_MD5.png](/img/user/_resources/Untitled%201/9e2303582f8661b77607d9a599270772_MD5.png)](https://user-images.githubusercontent.com/803666/102592241-19e7cf00-410b-11eb-9c3b-97185c910aa8.png)  
Printing an executable program (encoded in base64)

[![_resources/Untitled 1/d42a4e39bd563f29d4bd18041b901dd0_MD5.png](/img/user/_resources/Untitled%201/d42a4e39bd563f29d4bd18041b901dd0_MD5.png)](https://user-images.githubusercontent.com/803666/82190179-2b03ff80-98e0-11ea-90ec-61c471535a49.png)  
Printing a secret message (encrypted with [GPG-AES256](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard), encoded as stacked qrcode).

[![_resources/Untitled 1/fb11b5c83a23a6bd839179e237cd000c_MD5.png](/img/user/_resources/Untitled%201/fb11b5c83a23a6bd839179e237cd000c_MD5.png)](https://user-images.githubusercontent.com/803666/79379449-78dac000-7f4e-11ea-8747-b66a13ee1527.png)  
Printing a 21 seconds [soundscape of a rugby match](https://encyclopediedelaparole.org/fr/documents/joue-tous-les-ballons) (in 64kpbs MP3 encoded with Optar)

[![_resources/Untitled 1/a6944973231def10cc5eb277bcfe6557_MD5.png](/img/user/_resources/Untitled%201/a6944973231def10cc5eb277bcfe6557_MD5.png)](https://user-images.githubusercontent.com/803666/79601528-773d0380-80d8-11ea-88f9-0bc8536ad6b5.png)  
Printing a 7-page scientific paper on a single page (a PDF file encoded with colorsafe)

How to transform digital data to a printable format? You need a format that transforms a sequence of bytes into an image with a specific encoding. Then, you need two pieces of software, one encoder (data->image) and one decoder (image->decoder). We now review different kinds of encodings.

## Character-based encodings

TL;DR; OCR digital data is a very hard problem, one can get 2.5 kilobytes per A4 page that is decodable afterwards, see [“How to get perfect OCR for digital data?”](https://www.monperrus.net/martin/perfect-ocr-digital-data).

With character-based encoding, the idea is to use a [binary-to-text encoding](https://en.wikipedia.org/wiki/Binary-to-text_encoding) and then to use optical character recognition (OCR). The biggest advantage of character-based encodings is that they can be decoded by humans (as opposed to dot-based encodings), which means that you don’t need a camera or a scanner to recover the data. This is the most robust assumption for extreme conditions.

The information capacity primarily depends on the size of the alphabet and the font size (plus some variations due to the font being used). Yet, those numbers are theoretical in the sense that they assume perfect OCR.

**[base16/hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal)**: I can get 3.5 kilobytes per A4 page (font size 12pt, font Inconsolata) and OCR it with gocr at 400DPI. With smaller fonts, we have for example 4.6 kilobytes per A4 page (font size 9pt, font Inconsolata), but I cannot OCR it well (confusion between “7” and “1”), see [“How to get perfect OCR for digital data?”](https://www.monperrus.net/martin/perfect-ocr-digital-data).

[![_resources/Untitled 1/109eb057c36ec2566cdd2e3f1a67514d_MD5.png](/img/user/_resources/Untitled%201/109eb057c36ec2566cdd2e3f1a67514d_MD5.png)](https://user-images.githubusercontent.com/803666/97078209-f6584a80-15d9-11eb-85ea-adea8d950e78.png)  
Printing an encrypted GPG file encoded in base16

**[base32](https://en.wikipedia.org/wiki/Base32)**: I can get 5.8 kilobytes per A4 page (font size 9pt, font Inconsolata), but it is impossible for me to OCR it later without errors, see [“How to get perfect OCR for digital data?”](https://www.monperrus.net/martin/perfect-ocr-digital-data).

**[base64](https://en.wikipedia.org/wiki/Base64)**: 9.3 kilobytes per A4 page at font size 8t, even 17 kilobytes per A4 page at font size 6pt (confirming [this post](https://bitcoin.stackexchange.com/a/13494), but this is theoretical, no OCR can handle it).

[![_resources/Untitled 1/9e2303582f8661b77607d9a599270772_MD5.png](/img/user/_resources/Untitled%201/9e2303582f8661b77607d9a599270772_MD5.png)](https://user-images.githubusercontent.com/803666/102592241-19e7cf00-410b-11eb-9c3b-97185c910aa8.png)  
Printing an executable program encoded in base64

**[bocr32](https://www.monperrus.net/martin/perfect-ocr-digital-data)**: I have myself invented a character set of 32 characters, called bocr32, optimized for OCR, see [“How to get perfect OCR for digital data?”](https://www.monperrus.net/martin/perfect-ocr-digital-data).

[![_resources/Untitled 1/efdfe785906d9bde69566da5b402ffb3_MD5.png](/img/user/_resources/Untitled%201/efdfe785906d9bde69566da5b402ffb3_MD5.png)](https://user-images.githubusercontent.com/803666/102592774-de99d000-410b-11eb-8c07-6aa1fa566e48.png)  
Example of bocr32 encoded data

**[bip39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)**, I can get 1kb per A4 page (font size 12pt, font Inconsolata), and decode it, see [“How to get perfect OCR for digital data?”](https://www.monperrus.net/martin/perfect-ocr-digital-data).

[![_resources/Untitled 1/4d0d823de4f8fae752005a2b358530c4_MD5.png](/img/user/_resources/Untitled%201/4d0d823de4f8fae752005a2b358530c4_MD5.png)](https://user-images.githubusercontent.com/803666/97078330-28b67780-15db-11eb-9d0f-14f92645dc2f.png)  
Printing binary data encoded in bip39

## Black-and-white Dot Encodings

TL;DR; Up to 70k-100K per A4 page. Stacked QRCodes work well with off-the-shelf software. Optar is OK if one decreases the default density (XCROSSES/YCROSSES).

In a dot-based based encoding, the information capacity is a function of how small the dots are. In other words, it depends on your printer and your scanner (or camera if you take a picture of it). More technically, it means that the information capacity heavily depends on the conjunction of dots per inch (DPI) resolution at printing time and at scanning time.

**With a 600 DPI scanning resolution** (all those experiments are done on a Konica Minolta c550)

**QRCode** [(wikipedia)](https://en.wikipedia.org/wiki/QR_code): The maximum size of QR-Code is 2953 bytes, but you can stack several QRCodes on a single page (up to 24 Symbol-40 in my experiments). I decode them using [zbar-tools](https://packages.debian.org/zbar-tools). With 24 QRcode and UUencoding, I can put 47k of binary data. With direct UTF8 text, I can put 70k of text.

[![_resources/Untitled 1/b4cc93eb3104fd1398af991ee09c7f40_MD5.png](/img/user/_resources/Untitled%201/b4cc93eb3104fd1398af991ee09c7f40_MD5.png)](https://user-images.githubusercontent.com/803666/79479934-007f0800-7ffd-11ea-9d0e-7a9e22c78e1a.png)

24 QrCodes on a page, with text, totaling 9549 words over 71 kilobytes, successfully decoded

**Optar** [origin](http://ronja.twibright.com/optar/) [(unofficial Github repository)](https://github.com/colindean/optar/) works well, with which I can get 100kilobytes per A4 page, with the following tweaks: 1) XCROSSES=45 and YCROSSES=65 2) using TIF scanner output instead of JPG 3) by decreasing the scanning DPI resolution (from 600 to 400 counter-intuitive) I managed to encode 90 kilobytes of MP3 in Optar(52x74) decoded with 0.68% irreparable bits, resulting in a few audible glitches.

I could also get some reasonable results with stacked [DataMatrix](https://en.wikipedia.org/wiki/Data_Matrix) Same idea as QRCode, we have a maximum of 3116 bytes per matrix and one can pack several datamatrices on a page. However, the default decoder software on Linux ([dmtxread](https://packages.debian.org/dmtx-utils)) is not as effective as zbarimg (I succeeded to only pack 9 datamatrix per A4 page).

Other formats (failed or untested):

[paperback](http://ollydbg.de/Paperbak/) ([Windows version](http://ollydbg.de/Paperbak/)) ([linux version](https://git.teknik.io/scuti/paperback-cli)) I tested the linux version with a 600 DPI scanner and it fails ([issue](https://git.teknik.io/scuti/paperback-cli/issues/35)). Note that their 500kb-per-page claim is not reproducible.

## Color Dot Encodings

TL;DR; beautiful, but I haven’t thoroughly investigated them yet, only got some small success with jabcode.

Adding color allows on to code more information per dot (3x more with three colors). The drawback is that colorized dot encodings requires color printers, which are more expensive.

[![_resources/Untitled 1/b7393c889e2b83438cfd5a2b18303091_MD5.png](/img/user/_resources/Untitled%201/b7393c889e2b83438cfd5a2b18303091_MD5.png)](https://user-images.githubusercontent.com/803666/80257504-986d9900-8670-11ea-8ebb-af9ff18e3921.png)  
Example of Jabcode

Colorized paper formats (failed or untested):

-   [jabcode](https://github.com/jabcode/jabcode) is done by a German government organization, still maintained.
-   [colorsafe](https://github.com/colorsafe/colorsafe/) is full Python, can be installed through pip, claims up to 224kB of data per page. (fails, decoding fails after full-cycle)
-   [MrYakobo/tk](https://github.com/MrYakobo/tk) is for fun
-   [elm-hccb](https://github.com/canadaduane/elm-hccb) for [High Capacity Color Barcode (HCCB)](https://en.wikipedia.org/wiki/High_Capacity_Color_Barcode) (does not contain a decoder)
-   [blots](https://github.com/lf94/blots/) (not tested, does not contain a decoder)

## Drawing encoding

Artcodes allows users to draw encoded information, see [https://www.artcodes.co.uk/artcodes/](https://www.artcodes.co.uk/artcodes/).

## Discussion

### Theoretical information density maxima

The theoretical maxima is when you assume perfect scanning, alignment, etc. It depends on the scanning density and the color scale. At 300 DPI and black white, a page is 2480x3508 pixels, so it contains 8.7M bits which is 1100kB (1.1MB).

### Long term storage

Once you have some kind of encoded data, we store on paper. There exists different paper quality, incl. papers specifically designed for archival (and certified as such, for instance by a [Swedish government agency](https://www.ri.se/en/what-we-do/services/paper-testing-of-archival-and-permanent-paper)). Archival paper with archival ink is meant to [last for centuries](https://en.wikipedia.org/wiki/Print_permanence).

Now, it is also possible to put the encoded data on other media than paper, such as [stone](https://www.sys-teco.com/photo-engraving/qr-codes-grave-stone/), [lego bricks](https://hvitis.dev/jab-code-and-everything-you-need-to-know-about-color-bar-code) (claimed to last at least 1300 years), and [solid nickel](https://blocksandfiles.com/2021/10/25/totenpass-stores-data-on-credit-card-sized-gold-plated-nickel-slab/). Bitcoiners have gone quite far in falsifying the [durability claims of digital crypo keys on metal plates](https://blog.lopp.net/metal-bitcoin-seed-storage-stress-test/).

Also based on optical storage, one can use microfiches, as once done by [Foto-Mem](https://en.wikipedia.org/wiki/Foto-Mem).

### Redundancy and error correction

In a full cycle printing-transport-scanning there is a real risk that some dots in the image become corrupted. If the file format and use case allow for corruption (eg music in MP3), that’s fine. If the exact bit-per-bit content is required, this risk can be mitigated by [error correction](https://en.wikipedia.org/wiki/Error_correction_code).

For instance, QRCodes use [Reed-Solomon encoding](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction). In QRcode, there are four levels of error correction, low, medium, quartile and high, where the latter allows for up to 30% of the information to be lost.

It is always possible to use off-the-shelf error correction before encoding such as [rsbep](https://manpages.ubuntu.com/manpages/precise/man1/rsbep.1.html) or [PAR2](https://en.wikipedia.org/wiki/PAR2).

### Hand writing digital data

Not all encodings are appropriate for handwriting digital data. The character based encodings are OK if one has good OCR for one’s writing. Otherwise, the linear encodings (1D barcode) based on height (and not based on width) can be drawn easily. Examples of such height based encodings are the [US Postal format](https://en.wikipedia.org/wiki/Intelligent_Mail_barcode) and [Spotify codes](https://techcrunch.com/2017/05/05/spotify-codes/).

[![_resources/Untitled 1/ed8fae4bb8a18c15826bca41d21fe5c0_MD5.jpg](/img/user/_resources/Untitled%201/ed8fae4bb8a18c15826bca41d21fe5c0_MD5.jpg)](https://www.monperrus.net/martin/spotify-code-manual.jpeg)  
Hand-written Spotify barcode (credits Léonie Monperrus)

### Transportation of paper-stored data

You can take the sheets with you, send them by post, or even [attach them to homing pigeons](https://en.wikipedia.org/wiki/IP_over_Avian_Carriers)

## See also

-   Papers
    -   In [Robust and Fast Decoding of High-Capacity Color QR Codes for Mobile Applications (2017)](https://arxiv.org/pdf/1704.06447.pdf) Yang et al. claim to put 7.7kB on 38×38 mm2, which means ~300kb per A4 page. For experimenting, their [tool is on Github](https://github.com/cuhk-mobitec/HiQ-Robust-and-Fast-Decoding-of-High-Capacity-Color-QR-Codes).
    -   In [Paper encryption technology (2009)](https://www.fujitsu.com/global/documents/about/resources/publications/fstj/archives/vol46-1/paper20.pdf), Anan and colleagues do the same thing as GPG plus paper encoding, as presented above.
-   [The SKOR codex](http://societeanonyme.la/) contains 306 pages of printed images and printed sound based on a [homegrown encoding](https://archive.bleu255.com/bleu255.com-log/2012/07/03/electronic-publishing-one-bit-at-a-time/index.html).
-   [Wikinaut’s notes](https://hydra.wikinaut.de/bhntwiki/index.php/BHNT67/Paperback) is a gold mine with tons of links, in particular related to paper-storage of GPG and bitcoin cryptographic keys.
-   Wikipedia:
    -   [Paper data storage](https://en.wikipedia.org/wiki/Paper_data_storage)
    -   [2D bar code](https://en.wikipedia.org/wiki/Barcode)