In the last section, we mentioned client certificates as a form of
authentication. As we learned earlier, certificates are public keys that are
signed by a certificate authority or CA as a sign of trust. We covered TLS
server certificates, but there can also be client certificates. These operate
very similarly to server certificates but are presented by clients and allow
servers to authenticate and verify clients. As an IT support specialist, it's
important for you to understand client certificates and certificate-based
authentication, since you might encounter these in the course of your career.
It's not uncommon for VPN systems or enterprise Wi-Fi setups to use client
certificates for authentication. So understanding how they work will help you
troubleshoot issues. In order to issue client certificates, an organization must
set up and maintain CA infrastructure to issue and sign certificates. Part of
certificate authentication also involves the client authenticating the server,
giving us mutual authentication. This is a positive since the client can verify
that it's talking to the real authentication server and not an impersonator. In
this case, all clients that are using certificate authentication would also need
to have the CA certificate in their certificate trust store. This establishes
trust with the CA and allows the client to verify it's talking to the real
server when trying to authenticate. Certificate authentication is like
presenting identification at the airport. You show your ID or your certificate
to prove who you are. The ID is checked to see if it was issued by an authority
that is trusted by the verifier. Was it issued by a government entity or is it a
novelty license from a gift shop? Obviously, one of those IDs would be accepted
at the airport, similar to a certificate being signed by a trusted CA. When
you're at the airport, the expiration date on your ID will also be checked to
ensure it's still valid. The same thing applies to certificate authentication,
although the certificates have two dates that need to be verified. Not valid
before, and not valid after. Not valid before is checking to see if the
certificate is valid yet since it's possible to have certificates issued for
future use. Not valid after is a straightforward expiration date, after which
the certificate is no longer valid. Airport authorities also have a list of
specific IDs that are flagged. If your ID is on that list, then you'll be
rejected for air travel. Similarly, the certificate will be checked against a
revocation list or a CRL. This is a signed list published by the CA which
defines certificates that have been explicitly revoked. One last step that's
performed as part of the authentication server verification process is to prove
possession of the corresponding private key, since the certificate is a signed
public key. If we don't prove possession, there's nothing stopping an attacker
from copying the certificate, since it's not considered secret, and pretending
to be the owner. To avoid this, possession of the private key is verified
through a challenge response mechanism. This is where the server requests a
randomized bit of data to be signed using the private key corresponding to the
public key presented for authentication. This is similar to how the airport
checks the photo on your ID to make sure you look like the person in the photo
and aren't impersonating them.