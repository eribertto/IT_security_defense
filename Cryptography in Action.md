In this section, we'll dive into some real world applications of the encryption
concepts that we've covered so far. In the last section, we mentioned SSL/TLS
when we were talking about digital certificates. Now that we understand how
digital certificates function and the crucial roles CAs play, let's check out
how that fits into securing web traffic via HTTPS. You've probably heard of
HTTPS before, but do you know exactly what it is and how it's different from
HTTP? Very simply, HTTPS is the secure version of HTTP, the Hypertext Transfer
Protocol. So how exactly does HTTPS protect us on the Internet? HTTPS can also
be called HTTP over SSL or TLS since it's essentially encapsulating the HTTP
traffic over an encrypted, secured channel utilizing SSL or TLS. You might hear
SSL and TLS used interchangeably, but SSL 3.0, the latest revision of SSL, was
deprecated in 2015, and TLS 1.2 is the current recommended revision, with
version 1.3 still in the works. Now, it's important to call out that TLS is
actually independent of HTTPS, and is actually a generic protocol to permit
secure communications and authentication over a network. TLS is also used to
secure other communications aside from web browsing, like VoIP calls such as
Skype or Hangouts, email, instant messaging, and even Wi-Fi network security.
TLS grants us three things. One, a secure communication line, which means data
being transmitted is protected from potential eavesdroppers. Two, the ability to
authenticate both parties communicating, though typically, only the server is
authenticated by the client. And three, the integrity of communications, meaning
there are checks to ensure that messages aren't lost or altered in transit. TLS
essentially provides a secure channel for an application to communicate with a
service, but there must be a mechanism to establish this channel initially. This
is what's referred to as a TLS handshake. I'm more of a high five person myself,
but we can move on. The handshake process kicks off with a client establishing a
connection with a TLS enabled service, referred to in the protocol as
ClientHello. This includes information about the client, like the version of the
TLS that the client supports, a list of cipher suites that it supports, and
maybe some additional TLS options. The server then responds with a ServerHello
message, in which it selects the highest protocol version in common with the
client, and chooses a cipher suite from the list to use. It also transmits its
digital certificate and a final ServerHelloDone message. The client will then
validate the certificate that the server sent over to ensure that it's trusted
and it's for the appropriate host name. Assuming the certificate checks out, the
client then sends a ClientKeyExchange message. This is when the client chooses a
key exchange mechanism to securely establish a shared secret with the server,
which will be used with a symmetric encryption cipher to encrypt all further
communications. The client also sends a ChangeCipherSpec message indicating that
it's switching to secure communications now that it has all the information
needed to begin communicating over the secure channel. This is followed by an
encrypted Finished message which also serves to verify that the handshake
completed successfully. The server replies with a ChangeCipherSpec and an
encrypted Finished message once the shared secret is received. Once complete,
application data can begin to flow over the now the secured channel. High five
to that. The session key is the shared symmetric encryption key using TLS
sessions to encrypt data being sent back and forth. Since this key is derived
from the public-private key, if the private key is compromised, there's
potential for an attacker to decode all previously transmitted messages that
were encoded using keys derived from this private key. To defend against this,
there's a concept of forward secrecy. This is a property of a cryptographic
system so that even in the event that the private key is compromised, the
session keys are still safe. The SSH, or secure shell, is a secure network
protocol that uses encryption to allow access to a network service over
unsecured networks. Most commonly, you'll see SSH use for remote login to
command line base systems, but the protocol is super flexible and has provisions
for allowing arbitrary networks and traffic over those ports to be tunneled over
the encrypted channel. It was originally designed as a secure replacement for
the Telnet protocol and other unsecured remote login shell protocols like rlogin
or r-exec. It's very important that remote login and shell protocols use
encryption. Otherwise, these services will be transmitting usernames and
passwords, along with keystrokes and terminal output in plain text. This opens
up the possibility for an eavesdropper to intercept credentials and keystrokes,
not good. SSH uses public key cryptography to authenticate the remote machine
that the client is connecting to, and has provisions to allow user
authentication via client certificates, if desired. The SSH protocol is very
flexible and modular, and supports a wide variety of different key exchange
mechanisms like Diffie-Hellman, along with a variety of symmetric encryption
ciphers. It also supports a variety of authentication methods, including custom
ones that you can write. When using public key authentication, a key pair is
generated by the user who wants to authenticate. They then must distribute those
public keys to all systems that they want to authenticate to using the key pair.
When authenticating, SSH will ensure that the public key being presented matches
the private key, which should never leave the user's possession. PGP stands for
Pretty Good Privacy. How's that for a creative name? Well, PGP is an encryption
application that allows authentication of data along with privacy from third
parties relying upon asymmetric encryption to achieve this. It's most commonly
used for encrypted email communication, but it's also available as a full disk
encryption solution or for encrypting arbitrary files, documents, or folders.
PGP was developed by Phil Zimmerman in 1991 and it was freely available for
anyone to use. The source code was even distributed along with the software.
Zimmerman was an anti nuclear activist, and political activism drove his
development of the PGP encryption software to facilitate secure communications
for other activists. PGP took off once released and found its way around the
world, which wound up getting Zimmerman into hot water with the US federal
government. At the time, US federal export regulations classified encryption
technology that used keys larger than 40 bits in length as munitions. This meant
that PGP was subject to similar restrictions as rockets, bombs, firearms, even
nuclear weapons. PGP was designed to use keys no smaller than 128-bit, so it ran
up against these export restrictions, and Zimmerman faced a federal
investigation for the widespread distribution of his cryptographic software.
Zimmerman took a creative approach to challenging these restrictions by
publishing the source code in a hardcover printed book which was made available
widely. The idea was that the contents of the book should be protected by the
first amendment of the US constitution. Pretty clever? The investigation was
eventually closed in 1996 without any charges being filed, and Zimmerman didn't
even need to go to court. You can read more about why he developed PGP in the
next reading. PGP is widely regarded as very secure, with no known mechanisms to
break the encryption via cryptographic or computational means. It's been
compared to military grade encryption, and there are numerous cases of police
and government unable to recover data protected by PGP encryption. In these
cases, law enforcement tend to resort to legal measure to force the handover of
passwords or keys. Originally, PGP used the RSA algorithm, but that was
eventually replaced with DSA to avoid issues with licensing.