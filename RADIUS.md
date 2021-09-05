RADIUS or Remote Authentication Dial-In User Service, is a protocol that
provides AAA services for users on a network. It's a very common protocol used
to manage access to internal networks, WiFi networks, email services and VPN
services. Originally designed to transport authentication information for remote
dial up users, It's evolved to carry a wide variety of standard authentication
protocols like EAP or Extensible Authentication Protocol. While it's unlikely
that you'd be responsible for configuring RADIUS server as an IT support
specialist, you might be supporting clients that authenticate against a RADIUS
back end server. In those cases, it's good to understand what role the RADIUS
server plays in this authentication scenario so you're better prepared to
troubleshoot issues that may come up. Clients who want to authenticate to a
RADIUS server don't directly interact with it. Instead, when a client wants to
access a resource that's protected, the client will present authentication
credentials to a NAS or Network Access Server which will relay the credentials
to the RADIUS server. The RADIUS server will then verify the credentials using a
configured authentication scheme. RADIUS servers can verify user authentication
information stored in a flat file or can plug into external sources like SQL
databases, LDAP, Kerberos or Active Directory. Once the RADIUS server has
evaluated the user authentication request, it replies with one of three messages
access reject, access challenge or access accept.