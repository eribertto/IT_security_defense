Congrats on getting this far, you're over halfway through the course, and so
close to completing the program. In this section, we'll cover ways few to harden
your networks. Network hardening is the process of securing a network by
reducing its potential vulnerabilities through configuration changes, and taking
specific steps. In the next few lessons, we'll do a deep dive on the best
practices that an IT support specialist should know for implementing network
hardening. We'll also discuss network security protection along with network
monitoring and analysis. There's a general security principle that can be
applied to most areas of security, it's the concept of disabling unnecessary
extra services or restricting access to them. Since any service that's enabled
and accessible can be attacked, this principle should be applied to network
security too. Networks would be much safer if you disable access to network
services that aren't needed and enforce access restrictions. Implicit deny is a
network security concept where anything not explicitly permitted or allowed
should be denied. This is different from blocking all traffic, since an implicit
deny configuration will still let traffic pass that you've defined as allowed,
you can do this through ACL configurations. This can usually be configured on a
firewall which makes it easier to build secure firewall rules. Instead of
requiring you to specifically block all traffic you don't want, you can just
create rules for traffic that you need to go through. You can think of this as
whitelisting, as opposed to blacklisting. While this is slightly less
convenient, it's a much more secure configuration. Before a new service will
work, a new rule must be defined for it reducing convenience a bit. If you want
to learn more about how to configure a firewall rules and Linux and other
implementations, take a look at the references in the supplementary reading.
Another very important component of network security is monitoring and analyzing
traffic on your network. There are a couple of reasons why monitoring your
network is so important. The first is that it lets you establish a baseline of
what your typical network traffic looks like. This is key because in order to
know what unusual or potential attack traffic looks like, you need to know what
normal traffic looks like. You can do this through network traffic monitoring
and logs analysis. We'll dive deeper into what network traffic monitoring is a
bit later, but let's quickly summarize how laws can be helpful in this context.
Analyzing logs is the practice of collecting logs from different network and
sometimes client devices on your network, then performing an automated analysis
on them. This will highlight potential intrusions, signs of malware infections
or a typical behavior. You'd want to analyze things like firewall logs,
authentication server logs, and application logs. As an IT support specialist,
you should pay close attention to any external facing devices or services.
They're subject to a lot more potentially malicious traffic which increases the
risk of compromise. Analysis of logs would involve looking for specific log
messages of interests, like with firewall logs. Attempted connections to an
internal service from an untrusted source address may be worth investigating.
Connections from the internal network to known address ranges of Botnet command
and control servers could mean there's a compromised machine on the network. As
you learned in earlier courses of this program, log and analysis systems are a
best practice for IT supports specialists to utilize and implement. This is true
too for network hardening. Logs analysis systems are configured using
user-defined rules to match interesting or a typical log entries. These can then
be surfaced through an alerting system to let security engineers investigate the
alert. Part of this alerting process would also involve categorizing the alert,
based on the rule matched. You'd also need to assign a priority to facilitate
this investigation and to permit better searching or filtering. Alerts could
take the form of sending an email or an SMS with information, and a link to the
event that was detected. You could even wake someone up in the middle of the
night if the event was severe enough. Normalizing logged data is an important
step, since logs from different devices and systems may not be formatted in a
common way. You might need to convert log components into a common format to
make analysis easier for analysts, and rule-based detection systems, this also
makes correlation analysis easier. Correlation analysis is the process of taking
log data from different systems, and matching events across the systems. So, if
we see a suspicious connection coming from a suspect source address and the
firewall logs to our authentication server, we might want to correlate that
logged connection with the log data of the authentication server. That would
show us any authentication attempts made by the suspicious client. This type of
logs analysis is also super important in investigating and recreating the events
that happened once a compromise is detected. This is usually called a post fail
analysis, since it's investigating how a compromise happened after the breach is
detected. Detailed logging and analysis of logs would allow for detailed
reconstruction of the events that led to the compromise. Hopefully, this will
let the security team make appropriate changes to security systems to prevent
further attacks. It could also help determine the extent and severity of the
compromise. Detailed logging would also be able to show if further systems were
compromised after the initial breach. It would also tell us whether or not any
data was stolen, and if it was, what that data was. One popular and powerful
logs analysis system is Splunk, a very flexible and extensible log aggregation
and search system. Splunk can grab logs data from a wide variety of systems, and
in large amounts of formats. It can also be configured to generate alerts, and
allows for powerful visualization of activity based on logged data. You can read
more about Splunk and the supplementary readings in this lesson. Flood guards
provide protection against Dos or denial of service attacks. Think back to the
CIA triad we covered earlier, availability is an important tenet of security and
is exactly what Flood guard protections are designed to help ensure. This works
by identifying common flood attack types like SYN floods or UDP floods. It then
triggers alerts once a configurable threshold of traffic is reached. There's
another threshold called the activation threshold. When this one is reached, it
triggers a pre-configured action. This will typically block the identified
attack traffic for a specific amount of time. This is usually a feature on
enterprise grade routers or firewalls, though it's a general security concept. A
common open source flood guard protection tool is Fail2ban. It watches for signs
of an attack on a system, and blocks further attempts from a suspected attack
address. Fail to ban is a popular tool for smaller scale organizations. So, if
you're the sole IT support specialist in your company or have a small fleet of
machines, this can be a helpful tool to use. This flood guard protection can
also be described as a form of intrusion prevention system, which we'll cover in
more detail in another video. Network separation or network segmentation is a
good security principle for an IT support specialists to implement. It permits
more flexible management of the network, and provides some security benefits.
This is the concept of using VLANs to create virtual networks for different
device classes or types. Think of it as creating dedicated virtual networks for
your employees to use, but also having separate networks for your printers to
connect to. The idea here is that the printers won't need access to the same
network resources that employees do. It probably doesn't make sense to have the
printers on the employee network. You might be wondering how employees are
supposed to print if the printers are on a different network. It's actually one
of the benefits of network separation, since we can control and monitor the flow
of traffic between networks more easily. To give employees access to printers,
we'd configure routing between the two networks on our routers. We'd also
implement network ACLs that permit the appropriate traffic