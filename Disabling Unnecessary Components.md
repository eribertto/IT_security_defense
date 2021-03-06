Think back to the beginning of this course when we talked about attacks and
vulnerabilities. The special class of vulnerabilities we discussed called
zero-day vulnerabilities are unique since they're unknown until they're
exploited in the wild. The potential for these unknown flaws is something you
should think about when looking to secure your company's systems and networks.
Even though it's an unknown risk, it can still be handled by taking measures to
restrict and control access to systems. Our end goal overall is risk reduction.
Two important terms to know when talking about security risks are attack vectors
and attack surfaces. An attack vector is a method or mechanism by which an
attacker or malware gains access to a network or system. Some attack vectors are
email attachments, network protocols or services, network interfaces, and user
input. These are different approaches or paths that an attacker could use to
compromise a system if they're able to exploit it. An Attack Surface is the sum
of all the different attack vectors in a given system. Think of this as the
combination of all possible ways an attacker could interact with our system,
regardless of known vulnerabilities. It's not possible to know of all
vulnerabilities in the system. So, make sure to think of all avenues that an
outside actor could interact with our systems as a potential Attack Surface. The
main takeaway here is to keep our Attack Surfaces as small as possible. This
reduces the chances of an attacker discovering an unknown flaw and compromising
our systems. There are lots of approaches you can use as an IT support
specialist to reduce Attack Surfaces. All of them boil down to simplifying
systems and services. The less complex something is, the less likely there will
be undetected flaws. So, make sure to disable any extra services or protocols.
If they're not totally necessary, then get them out of there. Every additional
surface that's operating represents additional Attack Surfaces, that could have
an undiscovered vulnerability. That vulnerability could be exploited and lead to
compromise. This concept also applies to access and ACLs. Only allow access when
totally necessary. So, for example, it's probably not necessary for employees to
be able to access printers directly from outside of the local network. You can
just adjust firewall rules to prevent that type of access. Another way to keep
things simple is to reduce your software deployments. Instead of having five
different software solutions to accomplish five separate tasks, replace them
with one unified solution, if you can. That one solution should require less
complex code, which reduces the number of potential vulnerabilities. You should
also make sure to disable unnecessary or unused components of software and
systems deployed. By disabling features not in use, you're reducing even more
tech services, even more. You're not only reducing the number of ways an
attacker can get in, but you're also minimizing the amount of code that's
active. It's important to take this approach at every level of systems and
networks under your administration. It might seem obvious to take these measures
on critical networking infrastructure and servers, but it's just as important to
do this for desktop and laptop platforms that your employees use. Lots of
consumer operating systems ship a bunch of default services and software-enabled
right out of the box, that you probably won't be using in an enterprise network
or environment. For example, Telnet access for a managed switch has no business
being enabled in a real-world environment. You should disable it immediately if
you find it on the device. Any vendor-specific API access should also be
disabled if you don't plan on using these services or tools. They might be
harmless especially if you set up strong firewall rules and network ACLs. This
one service might represent a fairly low risk, but why take any unnecessary risk
at all? Remember, the defense in depth concept is all about risk mitigation and
implementing layers of security. Now, let's think about the layered approach to
security. What if our access control measures are bypassed or fail, in some
unforeseen way? As an IT support specialist, this is exactly what you want to
think about. How do we keep this component secure if the security systems above
it have failed?