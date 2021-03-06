We've covered Security Risk Assessment a little bit in the last lesson. But
there's lots more to talk about. Security is all about determining risks or
exposure understanding the likelihood of attacks; and designing defenses around
these risks to minimize the impact of an attack. This thought process is
actually something that everyone uses in their daily life, whether they know it
or not. Think of when you cross a busy intersection, you assess the probability
of being hit by an oncoming car and the minimize that risk by choosing the right
time to cross the road. Security risk assessment starts with threat modeling.
First, we identify likely threats to our systems, then we assign them priorities
that correspond to severity and probability. We do this by brainstorming from
the perspective of an outside attacker putting ourselves in a hackers shoes. It
helps to start by figuring out what high value targets an attacker may want to
go after. From there, you can start to look at possible attack vectors that
could be used to gain access to high value assets. High-value data usually
includes account information, like usernames and passwords. Typically, any kind
of user data is considered high value, especially if payment processing is
involved. Another part of risk measurement is understanding what vulnerabilities
are on your systems and network. One way to find these out is to perform regular
vulnerabilities scanning. There are lots of open source and commercial solutions
that you can use. They can be configured to perform scheduled, automated scans
of designated systems or networks to look for vulnerabilities. Then they
generate a report. Some of these tools are Nessus, OpenVas and Qualys which I've
linked to in the next reading. Let me break down what vulnerability scanners do.
Heads up, this might be a little dense, so feel free to go over it again.
Vulnerability scanners are services that run on your system within your control
that conduct periodic scans of configure networks. The service then conducts
scans to find and discover hosts on the network. Once hosts are found either
through a ping sweep or port scanning more detailed scans are run against
discovered hosts scans, upon scans, upon scans. A port scan of either common
ports or all possible valid ports is conducted against discovered hosts to
determine what services are listening. These services are then probed to try to
discover more info about the type of service and what version is listening on
the relevant port. This information can then be checked against databases of
known vulnerabilities. If a vulnerable version of a service is discovered, the
scanner will add it to its report. Once the scan is finished the discovered
vulnerabilities and hosts are compiled in a report, that way and analysts can
quickly and easily see where the problem areas are on the network. Found
vulnerabilities are prioritized according to severity, and other categorization.
Severity takes into account a number of things, like how likely the
vulnerability is to be exploited. It also considers the type of access the
vulnerability would provide to an attacker and whether or not it can be
exploited remotely or not. Vulnerabilities and the report will have links to
detailed and disclosed information about the vulnerability. In some cases, it
will also have recommendations on how to get rid of it. Vulnerability scanners
will detect lots of things, ranging from misconfigured services that represent
potential risks, to detecting the presence of back doors and systems. It's
important to call out that vulnerability scanning can only detect known and
disclose vulnerabilities and insecure configurations. That's why it's important
for you to have an automated vulnerability scan conducted regularly. You'll also
need to keep the vulnerability database up to date, to make sure new
vulnerabilities are detected quickly. But vulnerability scanning isn't the only
way to put your defenses to the test. Conducting regular penetration tests is
also really encouraged to test your defenses even more. These tests will also
ensure detection and alerting systems are working properly. Penetration Testing
is the practice of attempting to break into a system or network to verify the
systems in place. Think of this as playing the role of a bad guy, for
educational purposes. This exercise isn't designed to see if you have the acting
chops it's intended to make you think like an attacker and use the same tools
and techniques they would use. This way, you can test your systems to make sure
they protect you like they're supposed to. The results of the penetration
testing reports will also show you, where weak points or blind spots exist.
These tests help improve defenses and guide future security projects. They can
be conducted by members of your in-house security team. If your internal team
doesn't have the resources for this exercise you can hire a third party company
that offers penetration testing as a service. You can even do both. That would
help give you more perspectives on your defense systems and you'll get a more
comprehensive test this way.