Earlier, we covered authentication, the first component of the three A's of
security. Next up, we'll cover authorization, which is usually tightly coupled
with authentication. Now, while authentication is related to verifying the
identity a user, authorization pertains to describing what the user account has
access to or doesn't have access to. These are separate and distinct components
of AAA that have different purposes. A user may successfully authenticate to a
system by presenting valid credentials. But if the username they authenticated
as isn't also authorized to access the system in question, they'll be denied
access. When we talked about Kerberos earlier, the user authenticated and
received a ticket-granting ticket. This can then be used to request access to a
specific service by sending a request to the ticket-granting service. This is
when authorization comes into play, since the ticket-granting service will
decide whether or not the user in question is permitted to access the service
being requested. If they're not permitted or authorized to access the service,
the request will be denied by the ticket-granting service. If the user is
authorized, the ticket-granting service would return a ticket, which authorized
the user to access the service. One very popular open standard for authorization
and access delegation is OAuth, used by companies like Google, Facebook, and
Microsoft. We'll go in to OAuth in the next video.