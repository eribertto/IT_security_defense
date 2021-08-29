A network attack that is simple in concept, but can cause a lot of damage is a
DNS Cache Poisoning attack. You probably remember from the bits and bytes of
computer networking course, that DNS works by getting information about IP
addresses and names to make it easier for you to find a website. A DNS Cache
Poisoning attack works by tricking a DNS server into accepting a fake DNS record
that will point you to a compromised DNS server. It then feeds you fake DNS
addresses when you try to access legitimate websites. Not only that, DNS Cache
Poisoning can spread to other networks too. If other DNS servers are getting
their DNS information from a compromised server, they'll serve those bad DNS
entries to other hosts. Several years ago, there was a large scale DNS Cache
Poisoning attack in Brazil. It appeared that attackers managed to poison the DNS
cache of some local ISPs, by inserting fake DNS records for various popular
websites like Google, Gmail, or Hotmail. When someone attempted to visit one of
those sites, they were served a fake DNS record and were sent to a server that
the attacker controlled, which hosted a small java applet. The user would then
be tricked into installing the applet, which was actually a malicious banking
trojan designed to steal banking credentials. This is an example of the real
world damage DNS Cache Poisoning attacks can pose. You can learn more about it
in the next supplementary reading. A man-in-the-middle attack, is an attack that
places the attacker in the middle of two hosts that think they're communicating
directly with each other. It's clearly a name that needs some updating, men
aren't the only hackers out there. The attack will monitor the information going
to and from these hosts, and potentially modify it in transit. A common
man-in-the-middle attack is a session hijacking or cookie hijacking. Let's say
you log into a website and forget to log out. Now, you've already authenticated
yourself to the website and generated a session token that grants you access to
that website. If someone was performing a session hijacking, they could steal
that token and impersonate you on the website, and no one wants that. This is
another reason to think about the CIA's of security, you always want to make
sure that the data that you are sending or receiving has integrity and isn't
being tampered with. Another way a man-in-the-middle attack can be established
is a rogue access point attack. A rogue AP is an access point that is installed
on the network without the network administrator's knowledge. Sometimes, in
corporate environments, someone may plug a router into their corporate network
to create a simple wireless network. Innocent enough, right? Wrong. This can
actually be pretty dangerous, and could grant unauthorized access to an
authorized secure network. Instead of an attacker having to gain access to a
network by plugging directly into a network port, they can just stand outside
the building and hop onto this wireless network. A final man-in-the-middle
method will cover is called an evil twin. It's similar to the rogue AP example
but has a small but important difference. The premise of an evil twin attack is
for you to connect to a network that is identical to yours. This identical
network is our networks evil twin and is controlled by our attacker. Once we
connect to it, they will be able to monitor our traffic. I wonder if Fred
Weasley ever did this to George, probably not, they were wizards. They could
just magic their way out of problems. Must be nice.