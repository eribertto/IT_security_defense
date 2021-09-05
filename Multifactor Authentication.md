In the last video, we learned about basic authentication in the form of
username, password, sometimes referred to as single-factor authentication. But
there are other more complex and secure authentication mechanisms. Keep in mind
the security versus usability tradeoff, as we work through the different types
of multifactor authentication. Multifactor authentication is a system where
users are authenticated by presenting multiple pieces of information or objects.
The many factors that comprise a multifactor authentication system can be
categorized into three types. Something you know, something you have, and
something you are. Ideally, a multifactor system will incorporate at least two
of these factors. Something you know would be something like a password, or a
pin for your bank or ATM card. Something you have would be a physical token,
like your ATM or bank card. Something you are would be a piece of biometric
data, like a fingerprint or iris scan. The premise behind multifactor
authentication is that an attacker would find it much more difficult to steal or
clone multiple factors of authentication, assuming different types are used. If
multiple passwords are used, security isn't enhanced by that much. This is
because passwords, however many, are still susceptible to phishing or keylogging
attacks. By using a password in conjunction with a security token is a game
changer. Even if the password is compromised by a phishing attack, the attacker
would also need to steal or clone the physical token to be able to access the
account. And that's much less likely to happen. We won't cover passwords again
here since we talked about them in detail in the last section. But here's the
quick rundown. Physical tokens can take a few different forms. Common ones
include a USB device with a secret token on it, a standalone device which
generates a token, or even a simple key used with a traditional lock. A physical
token that's commonly used generates a short-lived token. Typically a number
that's entered along with a username and password. This number is commonly
called a One-Time-Password or OTP since it's short-lived and constantly changing
value. An example of this is the RSA SecurID token. It's a small,
battery-powered device with an LCD display, that shows a One-Time-Password
that's rotated periodically. This is a time-based token sometimes called a TOTP,
and operates by having a secret seed or randomly generated value on the token
that's registered with the authentication server. The seed value is used in
conjunction with the current time to generate a One-Time-Password. Now, as long
as the user has possession of their token, or can view the display of the token,
they are able to log in. I should also call out that the scheme requires the
time between the authenticator token, and the authentication server to be
relatively synchronized. This is usually achieved by using the Network Time
Protocol or NTP. An attacker would need to either steal the physical token or
clone the token if they're able to steal the secret seed value. Since a
time-based token is synchronized with the server using time, which is not a
secret, that would be sufficient for an attacker to clone a token. There are
also counter-based tokens, which use a secret seed value along with the secret
counter value that's incremented every time a one-time password is generated on
the device. The value is then incremented on the server upon successful
authentication. This is more secure than the time-based tokens for two reasons.
First, the attacker would need to recover the seed value and the counter value.
Second, the counter value is also incrementing when it's being used. So, a
cloned token would only be useful for a short period of time before the counter
value changes too much and the clone token becomes un-synchronized from the real
token and the server. These token generators can either be physical, dedicated
devices, or they can be an app installed on a smartphone that performs the same
functionality. Another very common method for handling multifactor today, is
that the delivery of one-time password tokens using SMS. But this has been
subject to some criticism, because of the observed attacks through this channel.
The problem with relying on SMS to transmit an additional authentication factor
is that you're dependent on the security processes of the mobile carrier. SMS
isn't encrypted, nor is it private. And it's possible for SMS to be intercepted
by a well-funded attacker. Even worse, there have been accounts of SMS based
multifactor codes being stolen by calling the mobile provider. The attacker
impersonates the owner of the line of service to redirect phone calls and SMS to
a phone the attacker controls. If the attacker has already compromised the
password and can get SMS redirected to them, they now get full access to the
account. Of course, there's a convenience tradeoff when you use a physical
token. You have to carry around another device in order to authenticate. If the
device is lost or damaged, the user won't be able to authenticate until the
device is replaced. This also requires support overhead, since devices will
fail, be lost, run off batteries, and get out of sync with the server. Using an
app on a smartphone addresses some of these issues, but still, require some
additional support and inconvenience. When prompted to log in, the user must
retrieve a device or phone from their pocket and manually transcribe the numbers
into the authentication page. These generated one-time passwords are also
susceptible to man in the middle style phishing attacks. A user can be tricked
into going to a fake authentication page by sending a phishing email. Something
on the lines of, "your account has been compromised, please log in and change
your password immediately." When the victim enters their credentials in the fake
page, including the one-time password, the attacker has all the information
needed to take over the account. The other category of multifactor
authentication is biometrics, which has gained in popularity in recent years,
especially in mobile devices. Biometric authentication is the process of using
unique physiological characteristics of an individual to identify them. By
confirming the biometric signature, the individual is authenticated. A very
common use of this in mobile devices is fingerprint scanners to unlock phones.
This works by registering your fingerprints first, using an optical sensor that
captures images of the unique pattern of your fingerprint. Much like how
passwords should never be stored in plain text, biometric data used for
authentication, so, it also never be stored directly. This is even more
important for handling biometric data. Unlike passwords, biometrics are an
inherent part of who someone is. So, there are privacy implications to theft or
leaks of biometric data. Biometric characteristics can also be super difficult
to change in the event that they are compromised unlike passwords. So, instead
of storing the fingerprint data directly, the data is run through a hashing
algorithm and the resulting unique hash is stored. One advantage of biometric
authentication over knowledge or token-based systems, is that it's more reliable
to identify an individual for authentication, since biometric features aren't
usually shareable. For example, you can't give your friend your fingerprints so
that they can log in as you. Well, you'd hope not anyway. But as schools start
to introduce fingerprint based attendance recording systems, students are
finding ways to trick the system. They're creating fake fingerprints using
things like glue, allowing friends to marking each other as present if they're
late or if they skip school. This is harder to achieve than sharing a password,
but it's sort of ingenious of these kids to think up. They really go the extra
mile to skip school these days. Not that I'm condoning this behavior, but you
can read more about it just after this video. Other biometric systems use
features like iris scans, facial recognition, gate detection and even voice.
Microsoft developed the biometric authentication system for Windows 10, called
Windows Hello, which supports fingerprint identification, iris identification
and facial recognition. It uses two cameras, one for color and one for infrared,
which allows for depth detection. This way, it's not possible to trick the
system using a printout of an authorized user's face. An evolution of physical
tokens is the U2F or Universal Second Factor. It's a standard developed jointly
by Google, Yubico and NXP Semiconductors. The finalized standard for U2F are
being hosted by the FIDO alliance. U2F incorporates a challenge-response
mechanism, along with public key cryptography to implement a more secure and
more convenient second-factor authentication solution. U2F tokens are referred
to as security keys and are available from a range of manufacturers. Support for
U2F authentication is built into the Chrome browser and the Opera browser, with
native Firefox support coming soon. Security keys are essentially small embedded
cryptoprocessors, that have secure storage of asymmetric keys and additional
slots to run embedded code. Let's do a quick rundown on how exactly security
keys work, and how their improvement over an OTP solution. The first step is
registration, since the security key must be registered with a site or service.
At registration time, the security key generates a private-public key pair
unique to that site, and submits the public key to the site for registration. It
also binds the identity of the site with the key pair. The reason for unique key
pairs for each site is for privacy reasons. If a site is compromised, this
prevents cross-referencing registered public keys, and discovering commonalities
between sites based on registration data. Once registered with the site, the
next time you're prompted to authenticate, you'll be prompted for your username
and password as usual. But afterwards, you'll be prompted to tap your security
key. When you physically tap the security key, it's a small check for user
presence to ensure malware cant authenticate on your behalf, without your
knowledge. This tap will unlock the private keys stored in the security key,
which is used to authenticate. The authentication happens as a
challenge-response process, which protects against replay attacks. This is
because the authentication session can't be used again later by an eavesdropper,
because the challenge and resulting response will be different with every
authentication session. What happens is the site generates a challenge,
essentially, some randomized data and sends this to the client that's attempting
to authenticate. The client will then select the private key matching the site,
and use this key to sign the challenge and send the signed data back. The site
can now verify the signature using the public key that was registered earlier.
If the signature checks out, the user is authenticated. From a security
perspective, this is a much more secure design than OTPs. This is because, the
authentication flow is protected from phishing attacks, given the interactive
nature of the process. While U2F doesn't directly protect against man in the
middle attacks, the authentication should take place over a secure TLS
connection, which would provide protection from this type of attack. Security
keys are also resistant to cloning or forgery, because they have unique,
embedded secrets on them and are protected from tampering. From the convenience
perspective, this is a much nicer authentication flow compared to OTPs since the
user doesn't have to manually transcribe a string of numbers into the
authentication dialog. All they have to do is tap their security key. Nice and
easy. As an IT support specialist, you may come across multifactor
authentication setups, that you'll be responsible for supporting. You might even
be tasked with helping to implement one. So, it's important to understand how
they provide enhanced account protection, along with the options that are
available.