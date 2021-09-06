Now that we've covered the security options available for protecting wireless
networks, what do you think the most secure option would be? In an ideal world,
we'd all be protecting our wireless networks using 802.1X with EAP-TLS. It
offers arguably the best security available, assuming proper and secure handling
of the PKI aspects of it. But, this option also requires a ton of added
complexity and overhead. This is because it requires the use of a radius server
and an additional authentication back-end at a minimum. If EAP-TLS is
implemented, then all the public key infrastructure components will also be
necessary. This adds even more complexity and management overhead. Not only do
you have to securely deploy PKI on the back-end for certificate management, but
a system must be in place to sign the client's certificates. You also have to
distribute them to each client that would be authenticating to the network. This
is usually more overhead than many companies are willing to take on, because of
the security versus convenience trade-off involved. If 802.1X is too complicated
for a company, the next best alternative would be WPA2 with AES/CCMP mode,. But
to protect against brute force or rainbow table attacks, we should take some
steps to raise the computational bar. A long and complex passphrase that
wouldn't be found in a dictionary would increase the amount of time and
resources an attacker would need to break the passphrase. Changing the SSID to
something uncommon and unique, would also make rainbow tables attack less
likely. It would require an attacker to do the computations themselves,
increasing the time and resources required to pull off an attack. When using a
long and complex Wi-Fi password, you might be tempted to use WPS to join clients
to the network. But we saw earlier that this might not be a good idea from a
security perspective. In practice, you won't see WPS enabled in an enterprise
environment, because it's a consumer-oriented technology. If your company values
security over convenience, you should make sure that WPS isn't enabled on your
APs. Make sure this feature is disabled on your AP's management console. You
might want to also verify the feature is actually disabled using a tool like
Wash, which scans and enumerates a piece that have WPS enabled. This independent
verification is recommended, since some router manufacturers don't allow you to
disable it. In some cases, disabling the feature through the management console
doesn't actually disable the feature. Ready for another quiz? Don't worry, it's
just a practice one, to help make sure you're getting all this wireless info
wired into your brain.