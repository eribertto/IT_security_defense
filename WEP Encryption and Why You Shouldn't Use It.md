In this lesson, we'll cover the best practices for implementing wireless
security. As an IT support specialist, you'll be responsible for WiFi
configuration and infrastructure. So understanding the security options
available for wireless networks is super important to making sure that the best
solution is chosen. We already covered the nuts and bolts of the wireless 802.11
protocol and explained how wireless networks work, so we won't rehash that. But
we'll take a closer look at the security implementations available to protect
wireless networks. Before we jump into the nitty-gritty details of wireless
security, take a second and ask yourself this question, what do you think the
best security option is for securing a WiFi network? It's okay if you're not
sure, just keep this question in mind as we go over all the options available
along with their benefits and drawbacks. Spoiler alert, there's some pretty
technical security stuff coming your way, so put your thinking caps on. The
first security protocol introduced for Wi-Fi networks was WEP or Wired
Equivalent Privacy. It was part of the original 802.11 standard introduced back
in 1997. WEP was intended to provide privacy on par with the wired network, that
means the information passed over the network should be protected from third
parties eavesdropping. This was an important consideration when designing the
wireless specification. Unlike wired networks, packets could be intercepted by
anyone with physical proximity to the access point or client station. Without
some form of encryption to protect the packets, wireless traffic would be
readable by anyone nearby who wants to listen. WEP was proven to be seriously
bad at providing confidentiality or security for wireless networks. It was
quickly discounted in 2004 in favor of more secure systems. Even so, we'll cover
it here for historical purposes. I want to drive home the point that no one
should be using WEP anymore. You never know, you may see seriously outdated
systems when working as an IT support specialist. So it's important that you
fully understand why WEP is outdated and what you can do instead. WEP use the
RC4 symmetric stream cipher for encryption. It used either a 40-bit or 104-bit
shared key where the encryption key for individual packets was derived. The
actual encryption key for each packet was computed by taking the user-supplied
shared key and then joining a 24-bit initialization vector or IV for short. It's
a randomized bit of data to avoid reusing the same encryption key between
packets. Since these bits of data are concatenated or joined, a 40-bit shared
key scheme uses a 64-bit key for encryption and the 104-bit scheme uses a
128-bit key. Originally, WEP encryption was limited to 64-bit only because of US
export restrictions placed on encryption technologies. Now once those laws were
changed, 128-bit encryption became available for use. The shared key was entered
as either 10 hexadecimal characters for 40-bit WEP, or 26 hex characters for
104-bit WEP. Each hex character was 4-bits each. The key could also be specified
by supplying 5 ASCII characters or 13, each ASCII character representing 8-bits.
But this actually reduces the available keyspace to only valid ASCII characters
instead of all possible hex values. Since this is a component of the actual key,
the shared key must be exactly as many characters as appropriate for the
encryption scheme. WEP authentication originally supported two different modes,
Open System authentication and Shared Key authentication. The open system mode
didn't require clients to supply credentials. Instead, they were allowed to
authenticate and associate with the access point. But the access point would
begin communicating with the client encrypting data frames with the pre-shared
WEP key. If the client didn't have the key or had an incorrect key, it wouldn't
be able to decrypt the frames coming from the access point or AP. It also
wouldn't be able to communicate back to the AP. Shared key authentication worked
by requiring clients to authenticate through a four-step challenge response
process. This basically has the AP asking the client to prove that they have the
correct key. Here's how it works. The client sends an authentication request to
the AP. The AP replies with clear text challenge, a bit of randomized data that
the client is supposed to encrypt using the shared WEP key. The client replies
to the AP with the resulting ciphertext from encrypting this challenge text. The
AP verifies this by decrypting the response and checking it against the plain
text challenge text. If they match, a positive response is sent back. Does
anything jump out at you as potentially insecure in the scheme? We're
transmitting both the plain text and the ciphertext in a way that exposes both
of these messages to potential eavesdroppers. This opens the possibility for the
encryption key to be recovered by the attacker. A general concept in security
and encryption is to never send the plain text and ciphertext together, so that
attackers can't work out the key used for encryption. But WEP's true weakness
wasn't related to the authentication schemes, its use of the RC4 stream cipher
and how the IVs were used to generate encryption keys led to WEP's ultimate
downfall. The primary purpose of an IV is to introduce more random elements into
the encryption key to avoid reusing the same one. When using a stream cipher
like RC4, it's super important that an encryption key doesn't get reused. This
would allow an attacker to compare two messages encrypted using the same key and
recover information. But the encryption key in WEP is just made up of the shared
key, which doesn't change frequently. It had 24-bits of randomized data,
including the IV tucked on to the end of it. This results in only a 24-bit pool
where unique encryption keys will be pulled from and used. Since the IV is made
up of 24-bits of data, the total number of possible values is not very big by
modern computing standards. That's only about 17 million possible unique IVs,
which means after roughly 5,000 packets, an IV will be reused. When an IV is
reused, the encryption key is also reused. It's also important to call out that
the IV is transmitted in plain text. If it were encrypted, the receiver would
not be able to decrypt it. This means an attacker just has to keep track of IVs
and watch for repeated ones. The actual attack that lets an attacker recover the
WEP key relies on weaknesses in some IVs and how the RC4 cipher generates a
keystream used for encrypting the data payloads. This lets the attacker
reconstruct this keystream using packets encrypted using the weak IVs. The
details of the attack are outside what we'll cover in this course, but the full
paper detailing the attack is available in the supplementary readings if you
want to check it out. You could also take a look at open source tools that
demonstrate this attack in action, like Aircrack-ng or AirSnort, they can
recover a WEP key in a matter of minutes, it's kind of terrifying to think
about. So now you've heard the technical reasons why WEP is inherently
vulnerable to attacks. In the next video, we'll talk about the solution that
replaced WEP. But before we get there, you might be asking yourself why it's
important to know WEP, since it's not recommended for use anymore. Well, as an
IT support specialist, you might encounter some cases where legacy hardware is
still running WEP. It's important to understand the security implications of
using this broken security protocol so you can prioritize upgrading away from
WEP. All right, now let's dive into the replacement for WEP in the next video.