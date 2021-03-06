Congratulations. You've reached the last chunk of the last course of this
program. You are totally ready to lock down every single operation of your
organization and make it airtight. Right? Not quite. If you're responsible for
an organization of users, there's a delicate balance between security and user
productivity. We've seen this balance in action when we dove into the different
security tools and systems together. Before you start to design a security
architecture, you need to define exactly what you like it to accomplish. This
will depend on what your company thinks is most important. It will probably have
a way it wants different data to be handled and stored. You also need to know if
your company has any legal requirements when it comes to security. If your
company handles credit card payments, then you have to follow the PCI DSS or
Payment Card Industry Data Security Standard depending on local laws. We'll take
a closer look at PCI DSS which is a great example of clearly defined security
goals. PCI DSS is broken into six broad objectives, each with some requirements.
The first objective is to build and maintain a secure network and systems. This
includes the requirements to install and maintain a firewall configuration to
protect cardholder data and to not use vendor supply default for system
passwords and other security parameters. As you can tell, the requirements are
related to the objective. The objective is the end goal or what we'd like to
achieve and the requirements are the actions that can help achieve that goal.
PCI DSS goes into more detailed actions for each requirement. It provides more
specific guidance around what a firewall configuration should control. For
example, a secure firewall configuration should restrict connections between
untrusted networks and any systems in the cardholder data environment. That's a
little generic, but it does give us some guidance on how to meet the
requirements. The second objective category is to protect cardholder data. In
this objective, the first requirement is to protect stored cardholder data. The
second is to encrypt the transmission of cardholder data across open public
networks. I want to call out again how the broad objective is to protect
sensitive data that's stored in systems within our control. The requirements
give us specific guidelines on how to get this done. The specifics of these
requirements help clarify some of the points like what constitutes an open
network. They also recommend using strong cryptography and offer some examples.
But not all requirements are technical in nature. Let's look at the requirement
to protect stored cardholder data for example, it has requirements for data
retention policies to make sure that sensitive payment information isn't stored
beyond the time it's required. Once payment is authorized, authentication data
shouldn't be needed anymore and it should be securely deleted. This highlights
the fact that good security defenses aren't just technical in nature. They are
also procedural and policy-based. The third objective is to maintain a
vulnerability management program. The first requirement is to protect all
systems against malware and regularly update antivirus software or programs. The
second is to develop and maintain secure systems and applications. You'll find
more detailed implementation procedures within these requirements. They'll cover
things like ensuring all systems have antivirus software installed and making
sure this software is kept up to date. They also require that scans are run
regularly and logs are maintained. There are also requirements for ensuring
systems and software are protected against known vulnerabilities by applying
security patches at least one month from the release of a security patch. Use of
third-party security vulnerability databases is also listed to help identify
known vulnerabilities within managed systems. The fourth objective is to
implement strong access control measures. This objective has three requirements.
The first is to restrict access to cardholder data by business need-to-know. The
second is to identify and authenticate access to system components. And the
third is to restrict physical access to cardholder data. This highlights the
importance of good access control measures along with good data access policies.
The first objective, restricting access to data by business need-to-know, means
that any sensitive data should be directed to data access policies to make sure
that customer data isn't misused. Part of this requirement is to enforce
password authentication for system access and two factor authentication for
remote access, that's the minimum requirement. Another important piece
highlighted by the PCI DSS requirements is access control for physical access.
This is a critical security aspect to keep in mind since we need to protect
systems and data from both physical theft and virtual attacks. The fifth
objective is to regularly monitor and test networks. The first requirement is to
track and monitor all access to network resources and cardholder data. The
second is to regularly test security systems and processes. The requirement for
network monitoring and testing is another essential part of a good security
plan. This refers to things like setting up and configuring intrusion detection
systems and conducting vulnerability scans of the network which will cover a bit
more later. Testing defenses is another super important part of this. Just
having the systems in place isn't enough. It's really helpful to test defense
systems regularly to make sure that they provide the protection that you want.
It also ensures that the alerting systems are functional. But don't worry, we'll
dive deeper into this a little bit later when we cover penetration testing. The
sixth and final objective is to maintain an information security policy. It only
has one requirement, to maintain a policy that addresses information security
for all personnel. This requirement addresses why we need to have
well-established security policies. They help govern and regulate user behavior
when it comes to information security aspects. It's important to call out that
this requirement mentions that the policy should be for all personnel. The
responsibility of information security isn't only on the security teams. Every
member of an organization is responsible for information security. Well-designed
security policies address the most common questions or use cases that users
would have based on the specific details of the organization. Every one that
uses systems on your organization's network, is able to get around security.
They might not mean to, but they can reduce the overall security with their
actions and practices. That's why having well-thought-out security policies in
place also need to be easy to find, and easy to read. We'll cover more details
about user education and getting users involved in the overall security plan in
another upcoming video of this course.