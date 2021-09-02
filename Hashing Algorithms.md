In this section, we'll cover some of the more popular hashing functions, both
currently and historically. MD5 is a popular and widely used hash function
designed in the early 1990s as a cryptographic hashing function. It operates on
a 512 bit blocks and generates 128 bit hash digests. While MD5 was published in
1992, a design flaw was discovered in 1996, and cryptographers recommended using
the SHA-1 hash, a more secure alternative. But, this flaw was not deemed
critical, so the hash function continued to see widespread use and adoption. In
2004, it was discovered that MD5 is susceptible to hash collisions, allowing for
a bad actor to craft a malicious file that can generate the same MD5 digest as
another different legitimate file. Bad actors are the worst, aren't they?
Shortly after this flaw was discovered, security researchers were able to
generate two different files that have matching MD5 hash digests. In 2008,
security researchers took this a step further and demonstrated the ability to
create a fake SSL certificate, that validated due to an empty five hash
collision. Due to these very serious vulnerabilities in the hash function, it
was recommended to stop using MD5 for cryptographic applications by 2010. In
2012, this hash collision was used for nefarious purposes in the flame malware,
which used the forge Microsoft digital certificate to sign their malware, which
resulted in the malware appearing to be from legitimate software that came from
Microsoft. You can learn more about the flame malware in the next reading. When
design flaws were discovered in MD5, it was recommended to use SHA-1 as a
replacement. SHA-1 is part of the secure hash algorithm suite of functions,
designed by the NSA and published in 1995. It operates a 512 bit blocks and
generates 160 bit hash digest. SHA-1 is another widely used cryptographic
hashing functions, used in popular protocols like TLS/SSL, PGP SSH, and IPsec.
SHA-1 is also used in version control systems like Git, which uses hashes to
identify revisions and ensure data integrity by detecting corruption or
tampering. SHA-1 and SHA-2 were required for use in some US government cases for
protection of sensitive information. Although, the US National Institute of
Standards and Technology, recommended stopping the use of SHA-1 and relying on
SHA-2 in 2010. Many other organizations have also recommended replacing SHA-1
with SHA-2 or SHA-3. And major browser vendors have announced intentions to drop
support for SSL certificates that use SHA-1 in 2017. SHA-1 also has its share of
weaknesses and vulnerabilities, with security researchers trying to demonstrate
realistic hash collisions. During the 2000s, a bunch of theoretical attacks were
formulated and some partial collisions were demonstrated, but full collisions
using these methods requires significant computing power. One such attack was
estimated to require $2.77 million in cloud computing CPU resources, Wowza. In
2015, a different attack method was developed that didn't demonstrate a full
collision but this was the first time that one of these attacks was demonstrated
which had major implications for the future security of SHA-1. What was only
theoretically possible before, was now becoming possible with more efficient
attack methods and increases in computing performance, especially in the space
of GPU accelerated computations in cloud resources. A full collision with this
attack method was estimated to be feasible using CPU and GPU cloud computing for
approximately $75 to $120,000 , much cheaper than previous attacks. You can read
more about these attacks and collisions in the next reading. In early 2017, the
first full collision of SHA-1 was published. Using significant CPU and GPU
resources, two unique PDF files were created that result in the same SHA-1 hash.
The estimated processing power required to do this was described as equivalent
of 6,500 years of a single CPU, and 110 years of a single GPU computing
non-stop. That's a lot of years. There's also the concept of a MIC, or message
integrity check. This shouldn't be confused with a MAC or message authentication
check, since how they work and what they protect against is different. A MIC is
essentially a hash digest of the message in question. You can think of it as a
check sum for the message, ensuring that the contents of the message weren't
modified in transit. But this is distinctly different from a MAC that we talked
about earlier. It doesn't use secret keys, which means the message isn't
authenticated. There's nothing stopping an attacker from altering the message,
recomputing the checksum, and modifying the MIC attached to the message. You can
think of MICs as protecting against accidental corruption or loss, but not
protecting against tampering or malicious actions.