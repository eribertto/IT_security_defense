Last but not least, the final A of the Triple A's of security is Accounting.
This means, keeping records of what resources and services your users access or
what they did when they were using your systems. A critical component of this is
auditing, which involves reviewing these records to ensure that nothing is out
of the ordinary. If we're watching and recording usage of our systems, but never
actually checking the usage data, that's not super useful. So what exactly do
counting systems keep track of? Well, that depends on the purpose and intent of
the system. For example, a TACACS+ server would be more concerned with keeping
track of user authentication, what systems they authenticated to, and what
commands they ran during their session. This is because TACACS+ plus is a device
access AAA system that manages who has access to your network devices and what
they do on them. CISCO's AAA system supports accounting of individual commands
executed, connection to and from network devices, commands executed in
privileged mode, and network services and system details like configuration
reloads or reboots. RADIUS will track details like session duration, client
location and bandwidth, or other resources used during the session. This is
because radius is a network access AAA system. So it tracks details about
network access and usage. RADIUS accounting kicks off with the Network Access
Server sending an accounting request packet to the accounting server that
contains an event record to be logged. This starts the accounting session on the
server. The server replies with an accounting response indicating that the
message was received. The NASS will continue sending periodic accounting
messages with statistics of the session until an accounting stop packet is
received. RADIUS accounting can be used for billing purposes by ISPs because it
records the length of a session and the amount of data sent and received by the
user. This data can also be used to enforce data or time quotas, limiting the
duration of sessions or restricting the amount of data that can be sent or
received. But, this accounting information isn't detailed and won't contain
specifics of what exactly the user did during the session. Information like
websites visited or what protocols were used aren't recorded. Other logging
utilities that will cover later meet that use case. Wow. Okay. We covered a lot
in this module. Great work. Take the time to go over anything that may have been
a little dense. When you're ready, we've got a project for you that will test
you on authentication, authorization, and accounting system concepts. Once
that's done, you can head to the next video, where we'll dive into network
security, monitoring, and logging.