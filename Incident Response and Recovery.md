Once a threat has been detected and contained, it has to be removed or
remediated. When it comes to malware infection, this means removing the malware
from affected systems. But in some cases, this may not be possible, so the
affected systems have to be restored to a known good configuration. This can be
done by rebuilding the machine or restoring from backup. Take care when removing
malware from systems because some malware is designed to be very persistent,
which means it's resistant to being removed. But before we can start the
recovery, we have to contain the incident. This might involve shutting down
affected systems to prevent further damage or spread of an infection. On the
flip side of that, affected systems may just have network access removed to cut
off any communication with the compromised system. Again, the motivating factor
here would be to prevent the spread of any infection or to remove remote access
to the system. The containment strategy varies depending on the nature of the
affected system. Let's say a critical piece of networking infrastructure was
compromised. A quick shutdown may not work since it would impact other business
operations. On top of that, removing networking access might trigger fail safes
in attack software or malware. Let's say a piece of malware is designed to
periodically check into a command and control server. Severing network
communications with the infected host might cause the malware to trigger a self
destruct function in an attempt to destroy evidence. Forensic analysis may need
to be done to analyze the attack. This is especially true when it comes to a
malware infection. In the case of forensic analysis, affected machines might be
investigated very closely to determine exactly what the attacker did. This is
usually done by taking an image of the disk, essentially making a virtual copy
of the hard drive. This lets the investigator analyze the contents of the disk
without the risk of modifying or altering the original files. If that happened,
it would compromise the integrity of any forensic evidence. Usually, evidence
gathering is also part of the incident response process. This provides evidences
to law enforcement if the organization wants to pursue legal action against the
attackers. Forensic evidence is super useful for providing details of the attack
to the security community. It allows others security teams to be aware of new
treats and lets them better defends themselves. It's also very important that
you get members from your legal team involved in any incident handling plans.
Because an incident can have legal implications for the company, a lawyer should
be available to consult and advise on the legal aspects of the investigation.
It's crucial in order to avoid complications or issues of liability. Members of
the public relations team should also get involved since these incidents can
have an impact on a company's reputation. There is another part of the cleanup
and recovery phase I should call out. We'll need to use information from the
analysis to prevent any further intrusions or infections. First, we determine
the entry point to figure out how the attacker got in, or what vulnerability the
malware exploited. This needs to be done at the same time as the cleanup. If you
remove the malware infection without also addressing the underlying
vulnerability, systems could become reinfected right after you clean them up. As
you learned in the system administration and IT infrastructure services course,
postmortems can be a great way to document incidents. The learnings from
postmortems can be used to prevent those incidents from happening again. If a
critical system has been compromised, remediation can be complicated because of
downtime during remediation and recovery. Logs have to be audited to determine
exactly what the attacker did while they had access to the system. They'll also
tell you what data the attacker accessed. Systems must be scrutinized to ensure
no back doors have been installed, or malware planted on the system. Depending
on the severity of the compromise or infection, it might be necessary to rebuild
the system from the ground up. Cleanup would typically involve restoring from a
backup point to a known good configuration. Infected or corrupted system files
could be restored from known good copies. Sometimes, cleanup can be very simple
and quick. I hope that's what you find more often than not. If a website was
defaced, the attacker may have simply uploaded their defaced HTML file and
pointed the web server at the new file. A configuration file change and deletion
of the attacker's HTML file would undo those changes. Even so, efforts need to
be made to determine how the attacker got access. That vulnerability should be
closed to prevent any future attacks. When all traces of the attack have been
removed and discovered and the known vulnerabilities have been closed, you can
move on to the last step. That's when systems need to be thoroughly tested to
make sure proper functionality has been restored. Usually, affected systems
would also remain under close watch, sometimes with additional detailed
monitoring and logging enabled. This is to watch for any additional signs of an
intrusion in case something was missed during the cleanup. It's also possible
that the attacker will attempt to attack the same target again. There's a very
high chance that they use the same or similar attack methodology on other
targets in your network. It's important to incorporate the lessons you've
learned from any incident into your overall security defenses. Update firewall
rules and ACLs if an exposure was discovered in the course of the investigation.
Create new definitions and rules for intrusion detections systems that can watch
for the signs of the same attack again. Stay vigilant and prepared to protect
your system from attacks. Remember that at some point, some sort of security
breach will happen. Just stay calm and execute your plan to counterattack the
breach.