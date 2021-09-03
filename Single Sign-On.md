Single Sign-On or SSO is an authentication concept that allows users to
authenticate once to be granted access to a lot of different services and
applications. Since reauthentication for each service isn't needed, users don't
need multiple sets of usernames and passwords across a mix of applications and
services. SSO is accomplished by authenticating to a central authentication
server, like an LDAP server. This then provides a cookie, or token that can be
used to get access to applications configured to use SSO. Kerberos is actually a
good example of an SSO authentication service. The user would authenticate
against the Kerberos service once, which would then grant them a ticket granting
ticket. This can then be presented to the ticket granting service in place of
traditional credentials. So, the user can enter credentials once and gain access
to a variety of services. SSO is really convenient. It allows users to have one
set of credentials that grant access to lots of services, making it less likely
that passwords will be written down or stored insecurely. This should also
reduce the overhead for password assistance support and removes time spent
re-authenticating throughout the workday. So, what's the downside? Well, an
attacker that manages to compromise an account has a lot more access under an
SSO scheme. User credentials will grant access to all applications and services
that that account is permitted to access. So, a big plug here for using
multifactor authentication in conjunction with an SSO scheme. But this opens a
new channel of attack, theft of SSO session cookies or tokens. Instead of
targeting credentials directly, attackers can try to steal the SSO tokens
directly which will permit wide access if even for a short amount of time.
Stealing these tokens, also lets an attacker dodge multifactor authentication
protections since the session token permits access without requiring full
authentication until the token expires. An example of an SSO system is the
openID, the centralized authentication system. This is an open standard that
allows participating sites known as Relying Parties to allow authentication of
users utilizing a third party authentication service. This allows sites to
permit authentication without requiring the site itself to have authentication
infrastructure, which can be tricky to implement and maintain. It also lets
users access the site without requiring them to create a new account,
simplifying access management across a wide variety of sites. Instead, a user
just needs to already have an account with an identity provider. To ask for
authentication, first a relying party looks up the openID provider, then
establishes a shared secret with the provider if one doesn't already exist. The
shared secret will be used to validate the openID provider messages. Then, the
user will be redirected or asked to authenticate in a new window through the
identities provider's log and flow. Once authenticated, the user will be
prompted to confirm if they trust the relying party or not. Once confirmed,
credentials are relayed to the relying party, typically in the form of a token
not actual user credentials which indicates the user is now authenticated to the
service. Now it's time for practice quiz on authentication.