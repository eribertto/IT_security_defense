Kerberos is a network authentication protocol that uses tickets to allow
entities to prove their identity over potentially insecure channels to provide
mutual authentication. It also uses symmetric encryption to protect protocol
messages from eavesdropping and replay attacks. The name Kerberos is taken from
the Greek mythical character of the same name. A three headed guard dog
protecting the gates to Hades, the underworld. Seems like an appropriate choice
for an authentication protocol, don't you think? Kerberos was originally
developed at the Massachusetts Institute of Technology in the US, and was
published in the 1980s as version four. Years later, in 1993, version 5 was
published. Today Kerberos supports AES encryption, and implements checksums to
ensure data integrity and confidentiality. When joined to a Windows domain,
Windows 2000 and newer versions will use Kerberos as the default authentication
protocol. Microsoft also implemented their own Kerberos service with some
modifications to the open protocol like the addition of the RC 4 Stream Cipher.
We mentioned tickets earlier which is a sort of token that proves your identity.
They can be used for authenticating to services protected using Kerberos or in
other words or within the Kerberos realm. The authentication tickets let users
authenticate to services without requiring username and password authentication
for every service individually. A ticket will expire after some time, but it has
provisions for automatic transparent renewal of the ticket. Let's run down the
details of how the Kerberos protocol operates. First, a user that wants to
authenticate enters their username and password on their client machine. Their
Kerberos client software, will then take the password and generate a symmetric
encryption key from it. Next, the client sends a plain text message to the
Kerberos, AS or Authentication Server which includes the user ID of the
authenticating user. The password or secret key derive from the password aren't
transmitted. The AS uses the user ID to check if there is an account in the
authentication database, like an active directory server. If so the AS will
generate the secret key using the hashed password stored in the key distribution
center server. The AS will then use the secret key to encrypt and send a message
containing the client TGS session key. This is a secret key use for encrypting
communications with the Ticket Granting Service or TGS, which is already known
by the Authentication Server. The AS also sends a second message with a Ticket
Granting Ticket or TGT, which is encrypted using the TGS secret key. The Ticket
Granting Ticket has information like the client ID, ticket validity period, and
the client taking granting service session key. So the first message can be
decrypted using the shared secret key derived from the user password. It then
provides the secret key that can decrypt the second message giving the client a
valid Ticket Granting Ticket. Now, the client has enough information to
authenticate with the Ticket Granting Server. Since the client has authenticated
and received a valid Ticket Granting Ticket, it can use the Ticket Granting
Ticket to request access to services from within the Kerberos realm. This is
done by sending a message to the Ticket Granting Service with the encrypted
Ticket Granting Ticket received from the AS earlier along with the service name
or ID the client is requesting access to. The client also sends a message
containing in authenticator which has the client ID and a time stamp that's
encrypted with the client Ticket Granting Ticket session key from the AS. The
Ticket Granting Service decrypts the Ticket Granting Ticket using the Ticket
Granting Service secret key, which provides the Ticket Granting Service with the
client Ticket Granting Service session key. It then uses the key to decrypt the
authenticator message. Next, it checks the client ID of these two messages to
ensure they match. If they do, it sends two messages back to the client. The
first one, contains the client to server ticket which is comprised of the client
ID, client address, validity period, and the client-server session key encrypted
using the service's secret key. The second message, contains the client-server
session key itself, and is encrypted using the client Ticket Granted Service
session key. Finally, the client has enough information to authenticate itself
to the service server or SS. The client sends two messages to the SS. The first
message is the encrypted client to server ticket received from the Ticket
Granting Service. The second is a new authenticator with the client ID and time
stamp encrypted using the client-server session key. The SS decrypts the first
message using its secret key which provides it with the client-server session
key. The key is then used to decrypt the second message, and it compares the
client ID in the authenticator to the one included in the client to server
ticket. If these IDs match, then the SS sends a message containing the time
stamp from the client supplied authenticator encrypted using the client-server
session key. The client, then decrypts this message, and checks that the time
stamp is correct authenticating the server. If this all succeeds, then the
server grants access to the requested service on the client. Wow, okay, are you
with me? I know that was a lot. Kerberos has received some criticism because
it's a single monolithic service. This creates a single point of failure danger.
If the Kerberos service goes down, new users won't be able to authenticate and
log in. Aside from the availability issues, if the central Kerberos server is
compromised, the attacker would be able to impersonate any user by generating
valid Kerberos tickets for their user account. Kerberos enforces strict time
requirements requiring the client and server clocks to be relatively closely
synchronized, otherwise, authentication will fail. This is usually accomplished
by using NTP to keep both parties synchronized using an NTP server. The trust
model of Kerberos is also problematic, since it requires clients and services to
have an established trust in the Kerberos server in order to authenticate using
Kerberos. This means, it's not possible for users to authenticate using Kerberos
from unknown or untrusted clients. So things like BYOD or Bring Your Own Device,
and cloud computing are incompatible, or at least very challenging to implement
securely with Kerberos authentication. Now as an IT support specialist, you're
likely to encounter Kerberos authentication especially, in an environments
running Microsoft Active Directory. Understanding how the underlying protocol
functions will help when troubleshooting issues that may come with it.