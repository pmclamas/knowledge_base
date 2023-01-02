##### Injection (Severity 1)
Injection flaws are very common in applications today. These flaws occur because user controlled input is interpreted as actual commands or parameters by the application. Injection attacks depend on what technologies are being used and how exactly the input is interpreted by these technologies.
*Some common examples include:*
- *SQL Injection -* this occurs when user controlled input is passed to SQL queries. As a result, an attacker can pass in SQL queries to manipulate the outcome of such queries.
- *Command Injection:* this occurs when user input is passed to system commands. As a result, an attacker is able to execute arbitrary system commands on application servers.

If an attacker is able to successfully pass input that is interpreted correctly, they would be able to do the following:
- access, modify and delete information in a database when this input is passed into database queries. This would mean that an attacker can steal sensitive information such as personal details and credentials.
- Execute Arbitrary system commands on a server that would allow an attacker to gain access to users' systems. This would enable them to steal sensitive data and carry out more attacks against infrastructure linked to the server on which the command is executed.

The main defence for preventing injection attacks is ensuring that user controlled input is not interpreted as queries or commands. There are different ways of doing this:
- *using an allow list -* when input is sent to the server, this input is compared to a list of safe input or characters. If the input is marked as safe, then it is processed. Otherwise, it is rejected and the application throws an error.
- *Stripping input -* if the input contains dangerous characters, these characters are removed before they are processed.

Dangerous characters or input is classified as any input that can change how the underlying data is processed. Instead of manually constructing allow lists or even just stripping input, there are various libraries that perform these actions for you.

##### OS Command Injection (Severity 1)
Command Injection occurs when server-side code in a web application makes a system call on the hosting machine. It is a web vulnerability that allows an attacker to take advantage of that made system call to execute operating system commands on the server- Sometimes this won't always end in something malicious, like a "whoami" or just reading of files.
But the thing about command injection is it opens up many options for the attacker. The worst thing they could do would be to spawn a reverse shell to become the user that the web server is running as.
A simple ```;nc -e /bin/bash``` (some variants of netcat don't support the -e option) is all that's needed and they own your server.
You can use a list of [these](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md) reverse shells as an alternative.

Once the attacker has a foothold on the web server, they can start the usual enumeration of your systems and start looking for ways to pivot around.

**What is Active Command Injection?**
Blind command injection occurs when the system command made to the server does not return the response to the user in the html document. Active Command Injection will return the response to the user. It can be made visible through several html elements.

##### Broken Authentication (Severity 2)
Authentication and session management constitute core components of modern web applications. Authentication allows users to gain access to web applications by verifying their identities. The most common form of authentication is using a username and password mechanism. A user would enter these credentials, the server would verify them. If they are correct, the server would then provide the users' browser with a session cookie. A session cookie is needed because web servers use HTTP(S) to communicate which is stateless. Attaching session cookies means that the server will know who is sending what data. The server can then keep track of users' actions.

If an attacker is able to find flaws in an authentication mechanism, they would then successfully gain access to other users' accounts. This would allow the attacker to access sensitive data (depending on the purpose of the application).
*Some common flaws in authentication mechanisms include:*
- *Brute Force Attacks:* if a web application uses usernames and passwords, an attacker is able to launch brute force attacks that allow them to guess the username and passwords using multiple authentication attempts.
- *Use of weak credentials:* web applications allow users to set passwords such as 'password1' or common passwords, then an attacker is able to easily guess them and access user accounts. They can do this without brute forcing and without multiple attempts.
- *Weak session cookies:* session cookies are how the server keeps track of users. If session cookies contain predictable values, an attacker can set their own session cookies and access users' accounts.

There can be various mitigation for broken authentication mechanisms depending on the exact flaw:
- To avoid password guessing attacks, ensure the application enforces a strong password policy.
- to avoid brute force attacks, ensure that the application enforces n automatic lockout after a certain number of attempts. This would prevent an attacker from launching more brute force attacks.
- Implement Multi Factor Authentication - if a user has multiple methods of authentication, then it would be difficult for an attacker to get access to both credentials to get access to their account.




