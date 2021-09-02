So far, we've talked about two forms of encryption, symmetric and asymmetric. In
this next lesson, we're going to cover a special type of function that's widely
used in computing and especially within security, hashing. No, not the breakfast
kind, although those are delicious. Hashing or a hash function is a type of
function or operation that takes in an arbitrary data input and maps it to an
output of a fixed size, called a hash or a digest. The output size is usually
specified in bits of data and is often included in the hashing function name.
What this means exactly is that you feed in any amount of data into a hash
function and the resulting output will always be the same size. But the output
should be unique to the input, such that two different inputs should never yield
the same output. Hash functions have a large number of applications in computing
in general, typically used to uniquely identify data. You may have heard the
term hash table before in context of software engineering. This is a type of
data structure that uses hashes to accelerate data lookups. Hashing can also be
used to identify duplicate data sets in databases or archives to speed up
searching of tables or to remove duplicate data to save space. Depending on the
application, there are various properties that may be desired, and a variety of
hashing functions exist for various applications. We're primarily concerned with
cryptographic hash functions which are used for various applications like
authentication, message integrity, fingerprinting, data corruption detection and
digital signatures. Cryptographic hashing is distinctly different from
encryption because cryptographic hash functions should be one directional.
They're similar in that you can input plain text into the hash function and get
output that's unintelligible but you can't take the hash output and recover the
plain text. The ideal cryptographic hash function should be deterministic,
meaning that the same input value should always return the same hash value. The
function should be quick to compute and be efficient. It should be infeasible to
reverse the function and recover the plain text from the hash digest. A small
change in the input should result in a change in the output so that there is no
correlation between the change in the input and the resulting change in the
output. Finally, the function should not allow for hash collisions, meaning two
different inputs mapping to the same output. Cryptographic hash functions are
very similar to symmetric key block ciphers and that they operate on blocks of
data. In fact, many popular hash functions are actually based on modified block
ciphers. Lets take a basic example to quickly demonstrate how a hash function
works. We'll use an imaginary hash function for demonstration purposes. Lets say
we have an input string of "Hello World" and we feed this into a hash function
which generates the resulting hash of E49A00FF. Every time we feed this string
into our function, we get the same hash digest output. Now let's modify the
input very slightly so it becomes "hello world", all lower case now. While this
change seems small to us, the resulting hash output is wildly different,
FF1832AE. Here is the same example but using a real hash function, in this case
md5sum. Hopefully, the concept of hash functions make sense to you now. In the
next section, we will explore some examples of hashing algorithms and dive into
weaknesses or attacks on hash functions.