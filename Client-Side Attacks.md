We've talked a lot about security attacks that target victims directly, but they
aren't the only type of attacks that occur in the web. One day, you may find
yourself in software development or software engineering. And you'll need to
know about these other types of attacks in order to ensure the security of your
work. A common security exploit that can occur in software development and runs
rampant on the web is the possibility for an attacker to inject malicious code.
We refer to these types of attacks as injection attacks. So how do injection
attacks work? Great question. For simplicity's sake, we won't get into the
details of the code implementation, but imagine a car. You keep your car running
by putting gas in it. Now, consider someone who wants to do something malicious
to that car. That person could inject your gas tank with a strawberry banana
milkshake. While that may sound delicious, it could also ruin your car. So how
do you fight against that? A hypothetical method to prevent this is adding a
mechanism to your car that only accepts gasoline and no other liquids. Injection
attacks in websites work the exact same way, except without the mouthwatering
strawberry banana milkshakes, and without having overly complex solutions.
Injection attacks can be mitigated with good software development principles,
like validating input and sanitizing data. Is anyone else getting hungry?
Milkshake break? No? Okay, we'll move on. Cross-site scripting, or XSS attacks,
are a type of injection attack where the attacker can insert malicious code and
target the user of the service. XSS attacks are a common method to achieve a
session hijacking. It would be as simple as embedding a malicious script in a
website, and the user unknowingly executes the script in their browser. The
script could then do malicious things like steal a victims cookies and have
access to a log in to a website. Mm, cookies. Another type of injection attack
is a SQL, or S-Q-L, injection attack. Unlike an XSS that targets a user, a SQL
injection attack targets the entire website if the website is using a SQL
database. Attackers can potentially run SQL commands that allow them to delete
website data, copy it, and run other malicious commands. Now that that's out of
the way, it's snack time.