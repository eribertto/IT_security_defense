Let's talk about securing network traffic. As we've seen, encryption is used for
protecting data both from the privacy perspective and
the data integrity perspective. A natural application of this technology
is to protect data in transit, but what if our application
doesn't utilize encryption? Or what if we want to provide
remote access to internal resources too sensitive to expose
directly to the Internet? We use a VPN, or
Virtual Private Network solution. A VPN is a mechanism that allows
you to remotely connect a host or network to an internal private network,
passing the data over a public channel, like the Internet. You can think of this as a sort of
encrypted tunnel where all of our remote system's network traffic would flow,
transparently channeling our packets via the tunnel through
the remote private network. A VPN can also be point-to-point, where
two gateways are connected via a VPN. Essentially bridging two private
networks through an encrypted tunnel. There are a bunch of VPN solutions
using different approaches and protocols with differing benefits and
tradeoffs. Let's go over some of
the more popular ones. IPsec, or Internet Protocol Security, is a VPN protocol that was
designed in conjunction with IPv6. It was originally required to be standards
compliant with IPv6 implementations, but was eventually
dropped as a requirement. It is optional for use with IPv6. IPsec works by encrypting an IP packet and encapsulating the encrypted
packet inside an IPsec packet. This encrypted packet then gets routed
to the VPN endpoint where the packet is de-encapsulated and decrypted then
sent to the final destination. IPsec supports two modes of operations,
transport mode and tunnel mode. When transport mode is used, only
the payload of the IP packet is encrypted, leaving the IP headers untouched. Heads up that authentication
headers are also used. Header values are hashed and verified,
along with the transport and application layers. This would prevent the use of anything
that would modify these values, like NAT or PAT. In tunnel mode, the entire IP packet,
header, payload, and all, is encrypted and encapsulated
inside a new IP packet with new headers. While not a VPN solution itself, L2TP, or Layer 2 Tunneling Protocol,
is typically used to support VPNs. A common implementation of L2TP
is in conjunction with IPsec when data confidentially is needed, since
L2TP doesn't provide encryption itself. It's a simple tunneling protocol
that allows encapsulation of different protocols or traffic over a network that may not
support the type of traffic being sent. L2TP can also just segregate and
manage the traffic. ISPs will use the L2TP to deliver
network access to a customer's endpoint, for example. The combination of L2TP and
IPsec is referred to as L2TP IPsec and was officially standardized
in ietf RFC 3193. The establishment of an L2TP IPsec
connection works by first negotiating an IPsec security association. Which negotiates the details of the secure
connection, including key exchange, if used. It can also share secrets, public keys,
and a number of other mechanisms. I've included a link to more info
about it in the next reading. Next, secure communication is established
using Encapsulating Security Payload. It's a part of the IPsec suite of
protocols, which encapsulates IP packets, providing confidentiality, integrity,
and authentication of the packets. Once secure encapsulation has
been established, negotiation and establishment of the L2TP
tunnel can proceed. L2TP packets are now
encapsulated by IPsec, protecting information about
the private internal network. An important distinction to make in this
setup is the difference between the tunnel and the secure channel. The tunnel is provided by L2TP, which permits the passing of unmodified
packets from one network to another. The secure channel, on the other hand,
is provided by IPsec, which provides confidentiality, integrity,
and authentication of data being passed. SSL TLS is also used in some VPN
implementations to secure network traffic, as opposed to individual sessions or
connections. An example of this is OpenVPN,
which uses the OpenSSL library to handle key exchange and encryption
of data, along with control channels. This also enables OpenVPN to make
use of all the cyphers implemented by the OpenSSL library. Authentication methods supported are
pre-shared secrets, certificate-based, and username password. Certificate-based authentication would be
the most secure option, but it requires more support and management overhead since
every client must have a certificate. Username and password authentication can
be used in conjunction with certificate authentication, providing
additional layers of security. It should be called out that OpenVPN
doesn't implement username and password authentication directly. It uses modules to plug into
authentication systems, which we'll cover in the next module. OpenVPN can operate over either TCP or
UDP, typically over port 1194. It supports pushing network configuration
options from the server to a client and it supports two interfaces for networking. It can either rely on a Layer 3 IP
tunnel or a Layer 2 Ethernet tap. The Ethernet tap is more flexible, allowing it to carry
a wider range of traffic. From the security perspective, OpenVPN supports up to 256-bit
encryption through the OpenSSL library. It also runs in user space, limiting the seriousness of potential
vulnerabilities that might be present. There are a lot of acronyms to take in,
so take a minute to go over them and read more about them, and
I'll see you in the next video.
