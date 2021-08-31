A Denial-of-Service, or DoS attack, is an attack that tries to prevent access to
a service for legitimate users by overwhelming the network or server. Think
about how you normally get on a website. Most major websites are capable of
serving millions of users. But for this example, imagine you have a website that
could only serve 10 users. If someone was performing a Denial-of-Service attack,
they would just take up all 10 of those spots, and legitimate users would have
been denied the service, because there's no more room for them. Now apply that
to a website like Google, or Facebook. DoS attacks try to take up those
resources of a service, and prevent real users from accessing it, not a pretty
picture. The Ping of Death or POD, is a pretty simple example of a DoS attack.
It works by sending a malformed ping to a computer. The ping would be larger in
size than what the internet protocol was made to handle. So it results in a
buffer overflow. This can cause the system to crash and potentially allow the
execution of malicious code. Another example is a ping flood, which sends tons
of ping packets to a system. More specifically, it sends ICMP echo requests,
since a ping expects an equal number of ICMP echo replies. If a computer can't
keep up with this, then it's prone to being overwhelmed and taken down. Not cool
ping flood, not cool. Similar to a ping flood is a SYN flood. Remember that to
make a TCP connection, a client sends a SYN packet to a server it wants to
connect to. Next, the server sends back a SYN-ACK message, then the client sends
in ack message. In a SYN flood, the server is being bombarded with the SYN
packets. The server is sending back SYN-ACK packets but the attacker is not
sending ack messages. This means that the connection stays open and is taking up
the server's resources. Other users will be unable to connect to the server
which is a big problem. Since the TCP connection is half-open, we also refer to
SYN floods as half-open attacks, sounds messy, right? It is, the DoS attacks
we've learned about so far only use a single machine to carry out an attack. But
what if attackers could utilize multiple machines? A much scarier scenario,
they'd be able to take down services in greater volumes and even quicker rates.
Even scarier, attackers can absolutely do that. A DoS attack using multiple
systems, is called a distributed denial-of-service attack or DDoS. DDoS attacks
need a large volume of systems to carry out an attack and they're usually helped
by botnet attackers. In that scenario, they can gain access to large volumes of
machines to perform an attack. In October of 2016, a DDoS attack occurred the
DNS service provider, Dyn was a target of a DDoS. Fake DNS look up requests
along with SYN floods that botnets to performing overloaded their system. Dyn
handled the DNS for major website like Reddit, GitHub, Twitter, etc. So once
that went down, it also took down its customers, making those services
inaccessible. Don't get between people on the Reddit threads or Twitter feeds, I
know from experience, it's not pretty.