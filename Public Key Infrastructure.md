In this lesson, we're going to cover PKI, or Public Key Infrastructure. Spoiler
alert, this is a critical piece to securing communications on the Internet
today. Earlier we talked about Public Key Cryptography and how it can be used to
securely transmit data over an untrusted channel and verify the identity of a
sender using digital signatures. PKI is a system that defines the creation,
storage and distribution of digital certificates. A digital certificate is a
file that proves that an entity owns a certain public key. A certificate
contains information about the public key, the entity it belongs to and a
digital signature from another party that has verified this information. If the
signature is valid and we trust the entity that signed the certificate, then we
can trust the public key to be used to securely communicate with the entity that
owns it. The entity that's responsible for storing, issuing, and signing
certificates is referred to as CA, or Certificate Authority. It's a crucial
component of the PKI system. There's also an RA, or Registration Authority,
that's responsible for verifying the identities of any entities requesting
certificates to be signed and stored with the CA. This role is usually lumped
together with the CA. A central repository is needed to securely store and index
keys and a certificate management system of some sort makes managing access to
storage certificates and issuance of certificates easier. There are a few
different types of certificates that have different applications or uses. The
one you're probably most familiar with is SSL or TLS server certificate. This is
a certificate that a web server presents to a client as part of the initial
secure setup of an SSL, TLS connection. Don't worry, we'll cover SSL, TLS in
more detail in a future lesson. The client usually a web browser will then
verify that the subject of the certificate matches the host name of the server
the client is trying to connect to. The client will also verify that the
certificate is signed by a certificate authority that the client trusts. It's
possible for a certificate to be valid for multiple host names. In some cases, a
wild card certificate can be issued where the host name is replaced with an
asterisk, denoting validity for all host names within a domain. It's also
possible for a server to use what's called a Self Sign Certificate. You may have
guessed from the name. This certificate has been signed by the same entity that
issued the certificate. This would basically be signing your own public key
using your private key. Unless you already trusted this key, this certificate
would fail to verify. Another certificate type is an SSL or TLS client
certificate. This is an optional component of SSL, TLS connections and is less
commonly seen than server certificates. As the name implies, these are
certificates that are bound to clients and are used to authenticate the client
to the server, allowing access control to a SSL, TLS service. These are
different from server certificates in that the client certificates aren't issued
by a public CA. Usually the service operator would have their own internal CA
which issues and manages client certificates for their service. There are also
code signing certificates which are used for signing executable programs. This
allows users of these signed applications to verify the signatures and ensure
that the application was not tampered with. It also lets them verify that the
application came from the software author and is not a malicious twin. We've
mentioned certificate authority trust, but not really explained it. So let's
take some time to go over how it all works. PKI is very much dependent on trust
relationships between entities, and building a network or chain of trust. This
chain of trust has to start somewhere and that starts with the Root Certificate
Authority. These root certificates are self signed because they are the start of
the chain of trust. So there's no higher authority that can sign on their
behalf. This Root Certificate Authority can now use the self-signed certificate
and the associated private key to begin signing other public keys and issuing
certificates. It builds a sort of tree structure with the root private key at
the top of the structure. If the root CA signs a certificate and sets a field in
the certificate called CA to true, this marks a certificate as an intermediary
or subordinate CA. What this means is that the entity that this certificate was
issued to can now sign other certificates. And this CA has the same trust as the
root CA. An intermediary CA can also sign other intermediate CAs. You can see
how this extension of trust from one root CA to intermediaries can begin to
build a chain. A certificate that has no authority as a CA is referred to as an
End Entity or Leaf Certificate. Similar to a leaf on a tree, it's the end of the
tree structure and can be considered the opposite of the roots. You might be
wondering how these root CAs wind up being trusted in the first place. Well,
that's a very good question. In order to bootstrap this chain of trust, you have
to trust a root CA certificate, otherwise the whole chain is untrusted. This is
done by distributing root CA certificates via alternative channels. Each major
OS vendor ships a large number of trusted root CA certificates with their OS.
And they typically have their own programs to facilitate distribution of root CA
certificates. Most browsers will then utilize the OS provided store of root
certificates. Let's do a deep dive into certificates beyond just their function.
The X.509 standard is what defines the format of digital certificates. It also
defines a certificate revocation list or CRL which is a means to distribute a
list of certificates that are no longer valid. The X.509 standard was first
issued in 1988 and the current modern version of the standard is version 3. The
fields defined in X.509 certificate are, the version, what version of the X.509
standard certificate adheres to. Serial number, a unique identifier for their
certificate assigned by the CA which allows the CA to manage and identify
individual certificates. Certificate Signature Algorithm, this field indicates
what public key algorithm is used for the public key and what hashing algorithm
is used to sign the certificate. Issuer Name, this field contains information
about the authority that signed the certificate. Validity, this contains two
subfields, Not Before and Not After, which define the dates when the certificate
is valid for. Subject, this field contains identifying information about the
entity the certificate was issued to. Subject Public Key Info, these two
subfields define the algorithm of the public key along with the public key
itself. Certificate signature algorithm, same as the Subject Public Key Info
field, these two fields must match. Certificate Signature Value, the digital
signature data itself. There are also certificate fingerprints which aren't
actually fields in the certificate itself, but are computed by clients when
validating or inspecting certificates. These are just hash digests of the whole
certificate. You can read about the full X.509 standard in the next reading. And
alternative to the centralized PKI model of establishing trust and binding
identities is what's called the Web of Trust. A Web of Trust is where
individuals instead of certificate authorities sign other individuals' public
keys. Before an individual signs a key, they should first verify the person's
identity through an agreed upon mechanism. Usually by checking some form of
identification, driver's license, passport, etc. Once they determine the person
is who they claim to be, signing their public key is basically vouching for this
person. You're saying that you trust that this public key belongs to this
individual. This process would be reciprocal, meaning both parties would sign
each other's keys. Usually people who are interested in establishing web of
trust will organize what are called Key Signing Parties where participants
performed the same verification and signing. At the end of the party everyone's
public key should have been signed by every other participant establishing a web
of trust. In the future when one of these participants in the initial key
signing party establishes trust with a new member, the web of trust extends to
include this new member and other individuals they also trust. This allows
separate webs of trust to be bridged by individuals and allows the network of
trust to grow.