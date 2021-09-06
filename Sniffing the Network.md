Now, in order to monitor what type of traffic is on your network, you need a
mechanism to capture packets from network traffic for analysis and potential
logging. Packet Sniffing or Packet Capture, is a process of intercepting network
packets in their entirety for analysis. It's an invaluable tool for IT support
specialists to troubleshoot issues. There are lots of tools that make this
really easy to do. Before we dive into the details of how to use them, let's
cover some basic concepts of Packet Sniffing. By default, network interfaces and
the networking software stack on an OS are going to behave like a well-mannered
interface, They will only be accepting and processing packets that are addressed
with specific interface address usually identified by a MAC address. If a packet
with a different destination address is encountered, the interface will just
drop the packet. But, if we wanted to capture all packets that an interface is
able to see, like when we're monitoring all network traffic on a network
segment, this behavior would be a pain for us. To override this, we can place
the interface into what's called Promiscuous Mode. This is a special mode for
Ethernet network interfaces that basically says, "Give me all the packets."
Instead of only accepting and handling packets destined for its address, it will
now accept and process any packet that it sees. This is much more useful for
network analysis or monitoring purposes. I should also call out that admin or
root privileges are needed to place an interface into promiscuous mode and to
begin to capture packets. Details for various platforms on how to get into
promiscuous mode can be found in the supplemental reading section. Many packet
capture tools will handle this for you too. Another super important thing to
consider when you perform packet captures is whether you have access to the
traffic you like to capture and monitor. Let's say you wanted to analyze all
traffic between hosts connected to a switch and your machine is also connected
to a port on the switch. What traffic would you be able to see in this case?
Because this is a switch, the only traffic you'd be able to capture would be
traffic from your host or destined for your host. That's not very useful in
letting you analyze other hosts traffic. If the packets aren't going to be sent
to your interface in the first place, Promiscuous Mode won't help you see them.
But, if your machine was inserted between the uplink port of the switch and the
uplink device further upstream now you'd have access to all packets in and out
of that local network segment. Enterprise manage switches usually have a feature
called Port Mirroring, which helps with this type of scenario. Port Mirroring,
allows the switch to take all packets from a specified port, port range, or the
entire VLAN and mirror the packets to a specified switch port. This lets you
gain access to all packets passing on a switch in a more convenient and secure
way. There's another handy though less advanced way that you can get access to
packets in a switched network environment. You can insert a hub into the
topology with the device or devices you'd like to monitor traffic on, connected
to the hub and our monitoring machine. Hubs are a quick and dirty way of getting
packets mirrored to your capture interface. They obviously have drawbacks
though, like reduced throughput and the potential for introducing collisions. If
you capture packets from a wireless network, the process is slightly different.
Promiscuous Mode applied to a wireless device would allow the wireless client to
process and receive packets from the network it's associated with destined for
other clients. But, if we wanted to capture and analyze all wireless traffic
that we're able to receive in the immediate area, we can place our wireless
interface into a mode called monitor mode. Monitor mode, allows us to scan
across channels to see all wireless traffic being sent by APs and clients. It
doesn't matter what networks they're intended for and it wouldn't require the
client device to be associated or connected to any wireless network. To capture
wireless traffic, all you need is an interface placed into monitor mode. Just
like enabling promiscuous mode, this can be done with a simple command, but
usually, the tools used for wireless packet captures can handle the enabling and
disabling of the mode for you. You need to be near enough to the AP and client
to receive a signal, and then you can begin capturing traffic right out of the
air. There are a number of open source wireless capture and monitoring
utilities, like Aircrack-ng and Kismet. It's important to call out that if a
wireless network is encrypted, you can still capture the packets, but you won't
be able to decode the traffic payloads without knowing the password for the
wireless network. So, now we're able to get access to some traffic we like to
monitor. So, what do we do next? We need tools to help us actually do the
capture and the analysis. We'll learn more about those in the next lesson.