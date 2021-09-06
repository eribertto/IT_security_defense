We covered Packet Capture and Analysis, which is related to our next topic,
Intrusion Detection and Prevention Systems or IDS/IPS. IDS or IPS systems
operate by monitoring network traffic and analyzing it. As an IT support
specialist, you may need to support the underlying platform that the IDS/IPS
runs on. You might also need to maintain the system itself, ensuring that rules
are updated, and you may even need to respond to alerts. So, what exactly do IDS
and IPS systems do? They look for matching behavior or characteristics that
would indicate malicious traffic. The difference between an IDS and an IPS
system, is that IDS is only a detection system. It won't take action to block or
prevent an attack, when one is detected, it will only log an alert. But an IPS
system can adjust firewall rules on the fly, to block or drop the malicious
traffic when it's detected. IDS and IPS system can either be host based or
network based. In the case of a Network Intrusion Detection System or NIDS, the
detection system would be deployed somewhere on a network, where it can monitor
traffic for a network segment or sub net. A host based intrusion detection
system would be a software deployed on the host that monitors traffic to and
from that host only. It may also monitor system files for unauthorized changes.
NIDS systems resemble firewalls in a lot of ways. But a firewall is designed to
prevent intrusions by blocking potentially malicious traffic coming from
outside, and enforce ACLs between networks. NIDS systems are meant to detect and
alert on potential malicious activity coming from within the network. Plus,
firewalls only have visibility of traffic flowing between networks they've set
up to protect. They generally wouldn't have visibility of traffic between hosts
inside the network. So, the location of the NIDS must be considered carefully
when you deploy a system. It needs to be located in the network topology, in a
way that it has access to the traffic we'd like to monitor. A good way that you
can get access to network traffic is using the port mirroring functionality
found in many enterprise switches. This allows all packets on a port, port
range, or entire VLAN to be mirrored to another port, where NIDS host would be
connected. With this configuration, our NIDS machine would be able to see all
packets flowing in and out of hosts on the switch segment. This lets us monitor
host to host communications, and traffic from hosts to external networks, like
the internet. The NIDS hosts would analyzed this traffic by enabling promiscuous
mode on the analysis port. This is the network interface that's connected to the
mirror port on our switch, so it can see all packets being passed, and perform
an analysis on the traffic. Since this interface is used for receiving mirrored
packets from the network we'd like to monitor, a NIDS host must have at least
two network interfaces. One is for monitoring an analysis, and a separate one is
for connecting to our network for management and administrative purposes. Some
popular NID or NIP systems are Snort, Suricata, and Bro NIDS, which you can read
about more in the supplementary readings. Placement of a NIP system or Network
Intrusion Prevention system, would differ from a NIDS system. This is because of
a prevention system being able to take action against a suspected malicious
traffic. In order for a NIPS device to block or drop traffic from a detected
threat, it must be placed in line with the traffic being monitored. This means,
that the traffic that's being monitored must pass through the NIPS device. If it
wasn't the case, the NIPS host wouldn't be able to take action on suspected
traffic. Think of it this way, a NIDS device is a passive observer that only
watches the traffic, and sends an alert if it sees something. This is unlike a
NIPS device, which not only monitors traffic, but can take action on the traffic
it's monitoring, usually by blocking or dropping the traffic. The detection of
threats or malicious traffic is usually handled through signature based
detection, similar to how antivirus software detects malware. As an IT Support
Specialist, you might be in charge of maintaining the IDS or IPS setup, which
would include ensuring that rules and signatures are up to date. Signatures are
unique characteristics of known malicious traffic. They might be specific
sequences of packets, or packets with certain values encoded in the specific
header field. This allows Intrusion Detection and Prevention Systems from easily
and quickly recognizing known bad traffic from sources like botnets, worms, and
other common attack vectors on the internet. But similar to antivirus, less
common are targeted attacks might not be detected by a signature based system,
since they're might not be signatures developed for these cases. So, it's also
possible to create custom rules to match traffic that might be considered
suspicious, but not necessarily malicious. This would allow investigators to
look into the traffic in more detail to determine the badness level. If the
traffic is found to be malicious, a signature can be developed from the traffic,
and incorporate it into the system. What actually happens when a NIDS system
detects something malicious? This is configurable, but usually the NIDS system
would log the detection event along with a full packet capture of the malicious
traffic. An alert would also usually be triggered to notify the investigating
team to look into that detected traffic. Depending on the severity of the event,
the alert may just email a group, or create a ticket to follow up on, or it
might page someone in the middle of the night if it's determined to be a really
high severity and urgent. These alerts would usually also include reference
information linking to a known vulnerability, or some more information about the
nature of the alert to help the investigator look into the event. Well, we
covered a lot of ground on securing your networks. I hope you feel secure enough
to move on. If not, you can review any of these concepts that we've talked
about. Once you've done that, it's time for a peer review assessment, to give
you some hands on experience with packet sniffing analysis. When you're
finished, I'll see you in the next video, where we'll cover defense in depth.