We've already alluded to attacks on hashes. Now let's learn more details,
including how to defend against these attacks. One crucial application for
cryptographic hash functions is for authentication. Think about when you log
into your e-mail account. You enter your e-mail address and password. What do
you think happens in the background for the e-mail system to authenticate you?
It has to verify that the password you entered is the correct one for your
account. You could just take the user supplied password and look up the password
on file for the given account and compare them. Right? If they're the same, then
the user is authenticated. Seems like a simple solution but does that seem
secure to you? In the authentication scenario, we'd have to store user passwords
in plain text somewhere. That's a terrible idea. You should never ever store
sensitive information like passwords in plain text. Instead, you should do what
pretty much every authentication system does, store a hash of the password
instead of the password itself. When you log into your e-mail account the
password you entered is run through the hashing function and then the resulting
hash digest is compared against the hash on file. If the hashes match, then we
know the password is correct, and you're authenticated. Password shouldn't be
stored in plain text because if your systems are compromised, passwords for
other accounts are ultimate prize for the attacker. If an attacker manages to
gain access to your system and can just copy the database of accounts and
passwords, this would obviously be a bad situation. By only storing password
hashes, the worst the attacker would be able to recover would be password
hashes, which aren't really useful on their own. What if the attacker wanted to
figure out what passwords correspond to the hashes they stole? They would
perform a brute force attack against the password hash database. This is where
the attacker just tries all possible input values until the resulting hash
matches the one they're trying to recover the plain text for. Once there's a
match, we know that the input that's generated that matches the hash is the
corresponding password. As you can imagine, a brute force attack can be very
computationally intensive depending on the hashing function used. An important
characteristic to call out about brute force attacks is, technically, they're
impossible to protect against completely. A successful brute force attack
against even the most secure system imaginable is a function of attacker time
and resources. If an attacker has unlimited time and or resources any system can
be brute force. Yikes. The best we can do to protect against these attacks, is
to raise the bar. Make it sufficiently time and resource intensive so that it's
not practically feasible in a useful timeframe or with existing technology.
Another common method to help raise the computational bar and protect against
brute force attacks is to run the password through the hashing function multiple
times, sometimes through thousands of interactions. This would require
significantly more computations for each password guess attempt. That brings us
to the topic of rainbow tables. Don't be fooled by the colorful name. These
tables are used by bad actors to help speed up the process of recovering
passwords from stolen password hashes. A rainbow table is just a pre-computed
table of all possible password values and their corresponding hashes. The idea
behind rainbow table attacks is to trade computational power for disk space by
pre-computing the hashes and storing them in a table. An attacker can determine
what the corresponding password is for a given hash by just looking up the hash
in their rainbow table. This is unlike a brute force attack where the hash is
computed for each guess attempt. It's possible to download rainbow tables from
the internet for popular password lists and hashing functions. This further
reduces the need for computational resources requiring large amounts of storage
space to keep all the password and hash data. You may be wondering how you can
protect against these pre-computed rainbow tables. That's where salts come into
play. And no, I'm not talking about table salt. A password salt is additional
randomized data that's added into the hashing function to generate the hash
that's unique to the password and salt combination. Here's how it works. A
randomly chosen large salt is concatenated or tacked onto the end of the
password. The combination of salt and password is then run through the hashing
function to generate hash which is then stored alongside the salt. What this
means now for an attacker is that they'd have to compute a rainbow table for
each possible salt value. If a large salt is used, the computational and storage
requirements to generate useful rainbow tables becomes almost unfeasible. Early
Unix systems used a 12 Bit salt, which amounts to a total of 4,096 possible
salts. So, an attacker would have to generate hashes for every password in their
database, 4,096 times over. Modern systems like Linux, BSD and Solaris use a 128
bit salt. That means there are two to the 128 power possible salt values, which
is over 340 undecillion. That's 340 with 36 zeros following. Clearly, 128 bit
salt raises the bar high enough that a rainbow table attack wouldn't be possible
in any realistic time-frame. Just another scenario when adding salt to something
makes it even better. That runs out our lesson on hashing functions. Up next
we'll talk about real world applications of cryptography and explain how it's
used in various applications and protocols. But first, a project that will help
you get hands on with hashing. Hashtag, get it done.