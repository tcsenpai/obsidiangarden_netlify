---
{"dg-publish":true,"permalink":"/bookmarks/knowledge/nsa-builds-secret-backdoors-in-the-new-encryption-standards/","tags":["corps","history","privacy","societies","surveillance","war"]}
---


Does the NSA build secret backdoors in the new encryption standards? No. In the past? Yes. Oh my very yes. Such yes even God has never seen.

Let’s set the Wayback Machine to the late 1990s. Crypto was very much on the minds of the NSA, and the FBI, and the CIA, and basically everyone else with any interest in surveillance. The NSA in particular was especially concerned about foreign adversaries using American-made IT devices with strong cryptography, and remember, to the NSA, every nation is potentially a “foreign adversary”—yes, of course, China and Russia, but also France, Spain, Portugal, Brazil…everyone.

I won’t go too deep into the maths, because it’s outside of the scope of this answer and anyway I have only a cursory understanding of it, but a big part of secure crypto is randomly generated asymmetric keys, and a big part of that is deterministic pseudorandom number generators—algorithms that are deterministic but when seeded produce a sequence of numbers as output that cannot be distinguished from randomness.

This is hard. You want PRNGs to generate number sequences that have no biases, that get as close to a random spread of output as possible, but still be deterministic—they produce the same output from the same seed. So anyway. A lot of crypto works by something called Diffie–Hellman key exchange. Again, how it works is outside the scope of this answer, but the high level overview is it’s a formal system for two people who want to communicate securely to generate two random key pairs, one public and one private, and exchange the public keys. Each encrypts a message to the other using the other’s public key. Once this is done, it can only be decrypted using the other’s private key.

If there are weaknesses in how the random public/private key pairs are generated, you can create an attack that allows you to deduce the other party’s private key.

In 1997, a couple of cryptographers presented a paper that explained a way to compromise a random number generator so that it could be used to generate secure keys, but if you knew the characteristics of the random number generator, you could design an exploit that would allow you, if you had information about how the random number generator worked, to deduce a private key from the public key. This is called a “kleptographic attack,” and it’s very subtle.

So fast-forward to the early 2000s. ANSI, the American National Standards Institute, is hard at work trying to develop a set of standards for cryptographic key generation, because the problem with crypto is even if you’re an expert mathematician, implementation suuuuuuuucks. Tiny, unbelievably subtle errors in implementation details of secure cryptography are enough to undermine the whole cryptosystem. With no standards, people were rolling their own cryptography, and the first rule of cryptography is if you roll your own, you can be 100% certain you screwed it up.

The ANSI standard would require secure deterministic pseudorandom number generators.

Enter the NSA.

The NSA introduced a PRNG called Dual_EC_DRBGinto the standards process. Dual_EC_DRBG was awesome, an easy to implement PRNG that produced excellent output. It was adopted into the ANSI standard in 2003, and (here’s the important bit) you could only get FIPS 140-2 certification—a certification that your device used crypto that wasn’t junk—if you included Dual_EC_DRBG. Without FIPS 140-2 certification, nobody would buy your kit. Can you tell what part of this story comes next?

In 2006, mathematicians and cryptographers examining the ANSI standard and probing how Dual_EC_DRBG works started raising alarms that Dual_EC_DRBG was mmmmmmmmaybe not quite as cryptographically secure as people thought.

In 2007, security researchers produced a paper called Space-Efficient Kleptography Without Random Oracles that basically detailed how a PRNG that works exactly like Dual_EC_DRBG can be used to provide a backdoor into secure crypto that uses Diffie–Hellman key exchange.

A few months later, another pair of researchers show a real-world proof-of-concept attack on Dual_EC_DRBG that demonstrated how an attacker who understands how elliptical curve PRNGs work and knows the implementation details of Dual_EC_DRBG can recover the internal state of the PRNG from its output and thus compromise a private key from its corresponding public key. In November 2007, Bruce Schneier published an essay asking if the NSA deliberately compromised Dual_EC_DRBG to create a backdoor into ANSI-compliant, FIPS 140-2 certified cryptographic devices and software, because of course he did. He is Bruce Schneier, after all.

Let’s fast forward again to 2013 and Edward Snowden. Snowden publishes stolen information about an NSA project called BULLRUN, whose purpose was… …wait for it… …wait for it… …to allow the NSA access to cryptographic communications through a wide range of means, up to and including compromising existing cryptographic standards and industry certifications.

At this point, the cat is well and truly out of the bag. NIST releases a statement advising people to cease using Dual_EC_DRBG immediately. RSA continues using Dual_EC_DRBG in some of its software…aaaaaaand it’s later revealed that they accepted $10,000,000 from the NSA to keep using Dual_EC_DRBG, because of course they did.

There was, as you can imagine, quite a kerfluffle over this, with RSA saying “but NIST told us it was secure!” and NIST saying “but we thought it was secure!” and cryptographer John Kelsey, who, um, worked for NIST, saying “I told you losers back in 2007 that there was something wrong with Dual_EC_DRBG but you didn’t listen to me, so shut your pie-holes about ‘you thought it was secure,’ you NSA stoolies.” (Note: the actual language he used was a bit different.)

Anyway, support for Dual_EC_DRBG was dropped, Dual_EC_DRBG was withdrawn as a cryptographically secure PRNG, and as of 2015ish or thereabouts, it became something of a sad mad historical footnote.

Okay, that’s the history.

The question asks, does the NSA build secret backdoors into the new encryption standards, and the answer is, not anymore.

After the Dual_EC_DRBG fiasco, nobody, and I mean nobody, trusts those fuckers anymore. If the NSA even hints that they like a particular algo, it’s an instant poison pill. The faintest whiff of NSA anything around any crypto standard is a death sentence.

More importantly, the crypto community is now aware that internal attacks like this can happen, and that government three-letter agencies can and will attempt to infiltrate ANSI and standards such as FIPS 140-2 (which was, of course, changed to drop inclusion of Dual_EC_DRBG).

At this point, there’s so little trust for the official standards process that even though FIPS 140-2 and now FIPS 140–3 certification is required for government contracts—and let me tell you, it was egg on NIST’s face to make a standard that the United States Government was mandated to meet that had a crypto back door in it—there are people and organizations that refuse FIPS 140 certification and even go so far that they won’t implement any cryptosystem endorsed by NIST.

That’s how badly Dual_EC_DRBG has damaged trust.

So the answer today is no. NSA is radioactive in the crypto community, which loathes and despises the NSA so much the whole community has put up a 50-mile exclusion zone around anything the NSA even sneezes at, complete with 50-foot perimeter walls topped with razor wire and surrounded by a minefield. The NSA can’t get close any more. They are universally despised with a hatred that burns with the fury of a thousand suns.

Do they want to? Yes, absolutely. Do they try? You bet. Do they still do shady things, like supply chain attacks where they try to infiltrate hardware manufacturers to put compromised hardware into crypto devices? You bet—which is more than a little ironic when you consider the NSA also has released guidelines on…securing your supply chain to prevent infiltrators from putting compromised components in your hardware, ah HA ha ha ha ha ha ha oh my God.

Anyway.

Yes, they want to, and yes, some people who were active in the crypto scene in the past still believe they do.

However, with the fact that there are a lot of very smart cryptanalysts going over every new proposal with a comb looking for exactly this kind of shenanigan, that ship has sailed. The NSA blew its load and it’s done. It’s very, very unlikely it will ever succeed at this particular type of standards attack to engineer a back door again.

Everyone knows, thousands of eyes end up on every new proposed standard, and nobody trusts them or NIST or ANSI at all.
