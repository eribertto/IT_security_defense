When you were little, did you and your siblings ever communicate in a secret
language around your parents? It didn't really matter what you were talking
about, as long as your parents didn't know what it was. That was the fun part,
right? It may have seemed like a fun game when you were younger. But for as long
as humans have been around, we've created ways to keep messages secret from
others. In this lesson, we'll cover how this plays out through symmetric
encryption, asymmetric encryption, and hashing. We'll also go over how to
describe the most common algorithms in cryptography. And learn how to choose the
most appropriate cryptographic method in any given scenario. But before we dive
into the nitty-gritty details of cryptography, the various types that exist in
our applications, let's go over some terminology and general principles that
will help you understand the details later. The topic of cryptography, or hiding
messages from potential enemies, has been around for thousands of years. It's
evolved tremendously with the advent of modern technology, computers and
telecommunications. Encryption is the act of taking a message, called plaintext,
and applying an operation to it, called a cipher. So that you receive a garbled,
unreadable message as the output, called ciphertext. The reverse process, taking
the garbled output and transforming it back into the readable plain text is
called decryption. For example, let's look at a simple cipher, where we
substitute e for o and o for y. We'll take the plaintext Hello World and feed it
into our basic cipher. What do you think the resulting ciphertext will be?
Hopefully, you've got Holly Wyrld. It's pretty easy to decipher the ciphertext
since this is a very basic example. There are much more complex and secure
ciphers or algorithms that we'll cover later in the section. A cipher is
actually made up of two components, the encryption algorithm and the key. The
encryption algorithm is the underlying logic or process that's used to convert
the plaintext into ciphertext. These algorithms are usually very complex
mathematical operations. But there are also some very basic algorithms that we
can take a closer look at that don't necessarily require a PhD in math to
understand. The other crucial component of a cipher is the key, which introduces
something unique into your cipher. Without the key, anyone using the same
algorithm would be able to decode your message, and you wouldn't actually have
any secrecy. So to recap, first you pick an encryption algorithm you'd like to
use to encode your message, then choose a key. Now you have a cipher, which you
can run your plaintext message through and get an encrypted ciphertext out ready
to be sent out into the world, safe and secure from prying eyes. Doesn't this
make you feel like an international person of mystery? Just wait, given that the
underlying purpose of cryptography is to protect your secrets from being read by
unauthorized parties, it would make sense that at least some of the components
of a cipher would need to be kept secret too, right? You can keep the argument
that by keeping the algorithm secret, your messages are secured from a snooping
third party, and technically you wouldn't be wrong. This general concept is
referred to as, security through obscurity, which basically means, if no one
knows what algorithm were using or general security practice, then we're safe
from attackers. Think of hiding your house key under you doormat, as long as the
burglar doesn't know that you hide the spare key under the mat, you're safe. But
once that information is discovered, all security goes out the window along with
your valuables. So clearly, security through obscurity isn't something that you
should rely on for securing communication or systems, or for your house for that
matter. This overall concept of cryptography is referred to as Kerckhoff's
principle. This principle states that a cryptosystem, or a collection of
algorithms for key generation and encryption and decryption operations that
comprise a cryptographic service should remain secure, even if everything about
the system is known except for the key. What this means is that even if your
enemy knows the exact encryption algorithm you use to secure your data, they're
still unable to recover the plaintext from an intercepted ciphertext. You may
also hear this principle referred to as Shannon's maxim or the enemy knows the
system. The implications are the same. The system should remain secure, even if
your adversary knows exactly what kind of encryption systems you're employing,
as long as your keys remain secure. We already defined encryption, but the
overarching discipline that covers the practice of coding and hiding messages
from third parties is called cryptography. The study of this practice is
referred to as cryptology. The opposite of this looking for hidden messages or
trying to decipher coded message is referred to as cryptanalysis. These two
fields have co-evolved throughout history with new ciphers and cryptosystems
being developed as previous ones were broken or found to vulnerable. One of the
earliest recorded descriptions of cryptanalysis is from a ninth century Arabian
mathematician. Who described a method for frequency analysis to break coded
messages. Frequency analysis is the practice of studying the frequency with
which letters appear in ciphertext. The premise behind this type of analysis is
that in written languages, certain letters appear more frequently than others,
and some letters are more commonly grouped together than others. For example,
the most commonly used letters in the English language are e, t, a, and o. The
most commonly seen pairs of these letters are th, er, on, and an. Some ciphers,
especially classical transposition and substitution ciphers preserve the
relative frequency of letters in the plaintext. And so our potentially
vulnerable to this type of analysis. During World War I and World War II,
cryptography and cryptanalysis played an increasingly important role. There was
a shift away from linguistics and frequency analysis and a move towards more
mathematical based analysis. This was due to more complex and sophisticated
ciphers being developed. A major turning point in the field of cryptanalysis was
during World War II when the US allies began to incorporate sophisticated
mathematics to aid in breaking access encryption schemes. This also saw the
first use of automation technology applied to cryptanalysis in England at
Bletchley Park. The first programmable digital computer, named Colossus, was
developed to aid in this effort. While early computers were applied to breaking
cryptography, this opened the door for a huge leap forward and a development of
even more sophisticated and complex cryptosystems. Steganography is a related
practice but distinctly different from cryptography. It's the practice of hiding
information from observers, but not encoding it. Think of writing a message
using invisible ink. The message is in plaintext and no decoding is necessary to
read the text but the text is hidden from sight. The ink is invisible and must
be made visible using a mechanism known to the recipient. Modern steganographic
techniques include embedding messages and even files into other files like
images or videos. To a casual observer, they would just see a picture of a cute
puppy. But if you feed that image into steganography software, it would extract
a message hidden within the image file. What's not so secret is how fun it is to
learn about all of this spy stuff, don't you think? Stick around, because next,
we'll talk about specific cryptographic methods and systems.