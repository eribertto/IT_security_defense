We try our best to protect our systems and networks. But it's pretty likely that
some sort of incident will happen. This could be anything from a full system
compromise and data theft, to someone accidentally leaking a memo. Regardless of
the nature of the incident, proper incident handling is important to
understanding what exactly happened, and how it happened and how to avoid it
from happening again. The very first step of handling an incident is to detect
it in the first place. Hopefully, our intrusion detection systems caught the
telltale signs of an ongoing attack, and alerted us to the threat. Incidents can
be brought to your attention in other ways too. An employee may have noticed
something suspicious and reported it to the security team for investigation, or
maybe they leaked information that ended up in the news. However, you found out
about the incident. The next step is to analyze it and determine the effects and
scope of damage. Was it a data leak? Or information disclosure? If so, what
information got out? How bad is it? Were systems compromised? What systems? And
what level of access did they manage to get? Is it a malware infection, what
systems were infected? Some attacks are really obvious with very clear signs of
an intrusion like a defaced webpage or unusual process consuming all resources
in the system. Others may be way more subtle and almost impossible to detect,
like a small change to a single system configuration file. This is why having
good monitoring in place is so important along with understanding your baseline.
Once you figure out what normal traffic looks like on your network and what
services you expect to see, outliers will be easier to detect. This is important
because every false lead that the incident response team has to investigate
means time and resource is wasted. This has the potential to allow real
intrusions to go undetected and uninvestigated longer. During detection and
scoping, correlating data from different systems can reveal a much bigger
picture of what's happened. It might show how an intruder gained access. For
example, you could see a connection event logged by the firewall from a
suspicious IP address, searching for other events related to this IP address may
reveal logging attempts and the authentication logs for a system. This would
provide insight into where the attacker is coming from and what they attempted
to do on the network. The authentication logs would also indicate, whether or
not they were able to successfully log into an account. If so, that's lets you
know what account is compromised. Once the scope of the incident is determined,
the next step is containment. You need to contain the breach to prevent further
damage. For system compromises and malware infection, this is a pretty time
sensitive step. You don't want the malware or attacker to use one compromised
machine to pivot to other machines inside your network. This could broaden the
incidence scope and cause even more damage. Containment strategies will vary
depending on the nature of the incident. If an account was compromised, change
the password immediately. If the owner is unable to change the password right
away, then lock the account. Also, revoke any long-lived authentication tokens,
since the attacker may have one of those too. If it's a malware infection, can
our anti-malware software quarantine? Or remove the infection? If not, the
infected machine needs to be removed from the network as soon as possible to
prevent lateral movement around the network. To do this, you can adjust
network-based firewall rules to effectively quarantine the machine. You can also
move the machine to a separate VLAN used for security quarantining purposes.
This would be a VLAN with strict restrictions and filtering applied to prevent
further infection of other systems and networks. It's important during this
phase that efforts are made to avoid the destruction of any logs or forensic
evidence. Attackers will usually try to cover their tracks by modifying logs and
deleting files, especially when they suspect they've been caught. They'll take
measures to make sure they keep their access to compromised systems. This could
involve installing a backdoor or some kind of remote access malware. Another
step to watch out for is creating a new user account that they can use to
authenticate within the future. With effective logging configurations and
systems in place, these activities would show up in audit logs. So this type of
access should be detected during an incident investigation, then actions can be
taken to remove access. I hope I'm not scaring you with all these scenarios, but
it's better to be safe than sorry. Another part of incident analysis is
determining severity, impact, and recoverability of the incident. Severity
includes factors like what and how many systems were compromised and how the
breach affects business functions. An incident that's compromised a bunch of
machines in the network would be more severe than one where a single web server
was hacked, for example. You can imagine that the effort required to fix a large
scale compromise would negatively affect the ability to do normal work. So, the
impact of an incident is also an important issue to consider. If the
organization only had one web server and it was compromised, it might be
considered a much higher severity breach. It would probably have a direct
externally visible impact on the business. Data exfiltration, is the
unauthorized transfer of data from a computer. It's also a very important
concern when a security incident happens. Hackers may try to steal data for a
number of reasons. They may want to steal account information to provide access
later. They may target business data to publish online to cause financial loss
or damage to the organization's reputation. In some cases, the attacker may just
want to cause damage and destruction, which might involve deleting or corrupting
data. What actions have been taken will affect the recoverability of the
incident? The recoverability is how complicated and time-consuming the recovery
effort will be. An incident that can be recovered with a simple restoration from
backup by following documented procedures would be considered easily recovered
from. But, an incident where an attacker deleted large amounts of customer
information and wrecked havoc across lots of critical infrastructure systems
would be way more difficult to recover from. It might not be possible to recover
from it at all. In some cases, depending on backup systems and configurations,
some data may be lost forever and can't be restored. Backups won't contain any
changes or new data that were made after the last backup run.