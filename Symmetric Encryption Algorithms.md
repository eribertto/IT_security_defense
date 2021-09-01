In the last section, we covered the basics of what exactly
symmetric encryption algorithms are and gave a basic example of the Caesar cipher,
a type of substitution cipher. We couldn't possibly protect anything of
value using the cipher though, right? There must be more complex and
secure symmetric algorithms, right? Of course, there are. One of the earliest encryption
standards is DES, which stands for Data Encryption Standard. DES was designed in the 1970s by IBM, with some input from
the US National Security Agency. DES was adopted as an official FIPS, Federal Information Processing Standard
for the US. This means that DES was adopted as
a federal standard for encrypting and securing government data. DES is a symmetric block cipher
that uses 64-bit key sizes and operates on blocks 64-bits in size. Though the key size is
technically 64-bits in length, 8-bits are used only for parity checking,
a simple form of error checking. This means that real world key length for
DES is only 56-bits. A quick note about encryption key sizes
since we haven't covered that yet. In symmetric encryption algorithms, the same key is used to encrypt as to
decrypt, everything else being the same. The key is the unique piece that protects
your data and the symmetric key must be kept secret to ensure the confidentiality
of the data being protected. The key size, defined in bits,
is the total number of bits or data that comprises the encryption key. So you can think of the key
size as the upper limit for the total possible keys for
a given encryption algorithm. Key length is super important in
cryptography since it essentially defines the maximum potential
strength of the system. Imagine an ideal symmetric encryption
algorithm where there are no flaws or weaknesses in the algorithm itself. In this scenario, the only possible way
for an adversary to break your encryption would be to attack the key
instead of the algorithm. One attack method is to just guess the key
and see if the message decodes correctly. This is referred to as
a brute-force attack. Longer key lengths protect
against this type of attack. Let's take the DES key as an example. 64-bits long minus the 8 parity bits
gives us a key length of 56-bits. This means that there are a maximum
of 2 to the 56th power, or 72 quadrillion possible keys. That seems like a ton of keys,
and back in the 1970s, it was. But as technology advanced and
computers got faster and more efficient, 64-bit keys quickly
proved to be too small. What were once only theoretical attacks
on a key size became reality in 1998 when the EFF,
Electronic Frontier Foundation, decrypted a DES-encrypted
message in only 56 hours. Because of the inherent weakness
of the small key size of DES, replacement algorithms were designed and
proposed. A number of new ones appeared
in the 1980s and 1990s. Many kept the 64-bit block size, but
used a larger key size, allowing for easier replacement of DES. In 1997, the NIST, National Institute
of Standards and Technology, wanted to replace DES with
a new algorithm, and in 2001, adopted AES, Advanced Encryption Standard,
after an international competition. AES is also the first and
only public cipher that's approved for use with top secret information by the
United States National Security Agency. AES is also a symmetric block cipher
similar to DES in which it replaced. But AES uses 128-bit blocks,
twice the size of DES blocks, and supports key lengths of 128-bit,
192-bit, or 256-bit. Because of the large key size, brute-force
attacks on AES are only theoretical right now, because the computing power
required (or time required using modern technology) exceeds
anything feasible today. I want to call out that these algorithms
are the overall designs of the ciphers themselves. These designs then must be
implemented in either software or hardware before the encryption functions
can be applied and put to use. An important thing to keep in mind when
considering various encryption algorithms is speed and ease of implementation. Ideally, an algorithm shouldn't
be overly difficult to implement because complicated implementation
can lead to errors and potential loss of security due to
bugs introduced in implementation. Speed is important because sometimes data
will be encrypted by running the data through the cipher multiple times. These types of cryptographic
operations wind up being performed very often by devices, so the faster they
can be accomplished with the minimal impact to the system, the better. This is why some platforms implement these
cryptographic algorithms in hardware to accelerate the processes and
remove some of the burden from the CPU. For example, modern CPUs from Intel or AMD have AES instructions built
into the CPUs themselves. This allows for
far greater computational speed and efficiency when working on
cryptographic workloads. Let's talk briefly about what was once
a wildly used and popular algorithm but has since been proven to be weak and
is discouraged from use. RC4, or Rivest Cipher 4,
is a symmetric stream cipher that gained widespread adoption because
of its simplicity and speed. RC4 supports key sizes from
40-bits to 2,048-bits. So the weakness of RC4 aren't
due to brute-force attacks, but the cipher itself has inherent weaknesses
and vulnerabilities that aren't only theoretically possible, there are lots
of examples showing RC4 being broken. A recent example of RC4 being
broken is the RC4 NOMORE attack. This attack was able to recover
an authentication cookie from a TLS-encrypted
connection in just 52 hours. As this is an attack on
the RC4 cipher itself, any protocol that uses this cipher is
potentially vulnerable to the attack. Even so, RC4 was used in a bunch
of popular encryption protocols, like WEP for wireless encryption,
and WPA, the successor to WEP. It was also supported in SSL and
TLS until 2015 when RC4 was dropped in all versions of TLS
because of inherent weaknesses. For this reason, most major web
browsers have dropped support for RC4 entirely, along with all versions
of SSL, and use TLS instead. The preferred secure configuration
is TLS 1.2 with AES GCM, a specific mode of operation for the AES block cipher that essentially
turns it into a stream cipher. GCM, or Galois/Counter Mode,
works by taking randomized seed value, incrementing this and
encrypting the value, creating sequentially numbered
blocks of ciphertexts. The ciphertexts are then incorporated
into the plain text to be encrypted. GCM is super popular due to its security
being based on AES encryption, along with its performance, and the fact that it can
be run in parallel with great efficiency. You can read more about the RC4 NOMORE
attack in the next reading. So now that we have covered
symmetric encryption and some examples of symmetric encryption
algorithms, what are the benefits or disadvantages of using
symmetric encryption? Because of the symmetric
nature of the encryption and decryption process, it's relatively
easy to implement and maintain. That's one shared secret that you
have to maintain and keep secure. Think of your Wi-Fi password at home. There's one shared secret,
your Wi-Fi password, that allows all devices to connect to it. Can you imagine having a specific Wi-Fi
password for each device of yours? That would be a nightmare and
super hard to keep track of. Symmetric algorithms are also very
fast and efficient at encrypting and decrypting large batches of data. So what are the downsides of
using symmetric encryption? While having one shared
secret that both encrypts and decrypts seems convenient up front, this
can actually introduce some complications. What happens if your
secret is compromised? Imagine that your Wi-Fi password was
stolen and now you have to change it. Now you have to update your Wi-Fi
password on all your devices and any devices your friends or
family might bring over. What do you have to do when a friend or
family member comes to visit and they want to get on your Wi-Fi? You need to provide them
with your Wi-Fi password, or the shared secret that
protects your Wi-Fi network. This usually isn't an issue since
you hopefully know the person and you trust them, and it's usually
only one or two people at a time. But what if you had a party at
your place with 50 strangers? Side note, why are you having a party
at your home with 50 strangers? Anyhow, how could you
provide the Wi-Fi password only to the people you trust
without strangers overhearing? Things could get really
awkward really fast. In the next lesson, we'll explore other
ways besides symmetric key algorithms to protect data and information.
