OAuth is an open standard that allows users to grant third-party websites and
applications access to their information without sharing account credentials.
This can be thought of as a form of access delegation because access to the
user's account is being delegated to the third party. This is accomplished by
prompting the user to confirm that they agree to permit the third party access
to certain information about their account. Typically, this prop will
specifically list which pieces of information or access are being requested.
Once confirmed, the identity provider will supply the third party with a token
that gives them access to the user's information. This token can then be used by
the third party to access data or services offered by the identity provider
directly on behalf of the user. OAuth is commonly used to grant access to third
party applications, to APIs offered by large internet companies like Google,
Microsoft, and Facebook. Let's say you want to use a third party meme creation
website. This website lets you create memes using templates and gives you the
option to save your creations and email them to your friends. Instead of the
site sending the emails directly, which would appear to be coming from an
address your friends wouldn't recognize, the site uses OAuth to get permission
to send the memes using your email account directly. This is done by making an
OAuth request to your email provider. Once you approve this request, the email
provider issues an access token to the site, which grants the site access to
your email account. The access token would have a scope, which says that it can
only be used to access email, not other services associated with the account. So
it can access email but not your cloud storage files or calendar, for example.
It's important that users pay attention to what third party is requesting access
and what exactly they're granting access to. OAuth permissions can be used in
phishing style attacks to gain access to accounts without requiring credentials
to be compromised. This works by sending phishing emails to potential victims
that look like legitimate OAuth authorization requests, which ask the user to
grant access to some aspects of their account through OAuth. Once the user
grants access, the attacker has access to the account through the OAuth
authorization token. This was used in an OAuth based worm attack in early 2017.
There was a rash of phishing emails that appeared to be from a friend or
colleague who wanted to share a google doc. When the sharing link was followed,
the victim was prompted to log in and authorize access to email documents and
contacts for some third party service, which only identified itself as the name
Google Apps. But it was actually a malicious service that would then email
contacts from their email account perpetuating the attack. In case you like to
read more about it, I've included a link in the next reading. It's important to
distinguish between OAuth and OpenID. OAuth is specifically an authorization
system and OpenID is an authentication system. Though they're usually used
together, OpenID Connect is an authentication layer built on top of OAuth 2.0
designed to improve upon OpenID and build better integration with OAuth
authorizations. Since TACACS plus is a full AAA system, it also handles
authorization along with authentication. This is done once a user is
authenticated by allowing or disallowing access for the user account to run
certain commands or access certain devices. This lets you not only allow admin
access for users that administer devices while still allowing less privileged
access to other users when necessary. Here's an example, since your networking
teams are responsible for configuring and maintaining your network switches,
routers, and other infrastructure. You'd give them admin access to your network
and equipment. Meanwhile, you can have limited read-only access to your support
team since they don't need to be able to make changes to switch configurations
in their jobs. Read-only access is enough for them to troubleshoot problems. The
rest of the user accounts would have no access at all and wouldn't be permitted
to connect to the networking infrastructure. So more sophisticated or
configurable AAA systems may even allow further refinement of authorization down
to the command level. This gives you much more flexibility in how your access is
granted to specific users or groups in your organization. RADIUS also allows you
to authorize network access. For example, you may want to permit some users to
have Wi-Fi and VPN access while others may not need this. When they authenticate
to the RADIUS server, if the authentication succeeds, the RADIUS server returns
configuration information to the network access server. This includes
authorizations which specifies what network services the user is permitted to
access.