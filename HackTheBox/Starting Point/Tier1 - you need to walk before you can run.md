# Appointment

I**ntroduction**

We will find out how to perform an SQL Injection against an SQL Database enabled web application. Our target is running a website with search capabilities against a backend database containing searchable items vulnerable to this type of attack. Not all items in this database should be seen by any user, so different privileges on the website will grant you different search results.

The “Tables” of information will be separate. However, for an attacker with knowledge on web application vulnerabilities - specifically SQL Injection - the separation between those tables will mean nothing, as they will be able to exploit the web application to directly query any table found on the SQL Database of the webserver.

An excellent example of how an SQL Service typically operates is the log-in process utilized for any user. Each time the user wants to log in, the web application sends the log-in page input (username/password combination) to the SQL Service, comparing it with stored database entries for that specific user. Suppose the specified username and password match any entry in the database. In that case, the SQL Service will report it back to the web application, which will, in turn, log the user in, giving them access to the restricted parts of the website. Post-log-in, the web application will set the user a special permission in the form of a cookie or authentication token that associates his online presence with his authenticated presence on the website. This cookie is stored both locally, on the user’s browser storage, and the webserver.

Afterward, if the user wants to search through the list items listed on the page for something in particular, he will input the object’s name in a search bar, which will trigger the same SQL Service to run the SQL query on behalf of the user. Suppose an entry for the searched item exists in the database, typically under a different table. In that case, the associated information is retrieved and sent to the web application to be presented to the user as images, text, links, and other types, such as comments and reviews.

The reason websites use databases, is that the data they collect or serve needs to be stored somewhere. Data could be usernames, passwords, posts, messages, or more sensitive stes such as PII (Personally Identifiable Information), which is protected by international data privacy laws.

SQL Injection is a common way of exploiting web pages that use SQL statements that retrieve and store user input data. If configured incorrectly, one can use this attack to exploit the well-known SQL Injection vulnerability, which is very dangerous. There are many different techniques of protecting from SQL Injections, some of them being input validation, parameterized queries, stored procedures, and implementing a WAF (Web Application Firewall) on the perimeter of the server’s network. However, instances can be found where none of these fixes are in place, hence why this type of attack is prevalent, according to the OWASP Top 10 list of web vulnerabilities.

**Enumeration**

First, we perform an nmap scan to find the open and available ports and their services. If no alternative flag is specified in the command syntax, nmap will scan the most common 1000 TCP ports for active services.

Additionally, we will need super-user privileges to run the command with the -sC or -sV flags. This is because script scanning (-sC) and version detection (-sV) are considered more intrusive methods of scanning the target. This results in a higher probability of being caught by a perimeter security device on the target’s network.

_**-sC :**_ performs a script scan using the default set of scripts. It is equivalent to —script=default. Some of the scripts in this category are considered intrusive and should not be run against a target network without permission.

_**-sV :**_ enables version detection, which will detect what versions are running on what port.

`**$ sudo nmap -sC -sV {target_IP}**`

The only open port we detect is port 80 TCP, which is running the Apache httpd server.

Apache HTTP Server is a free and open-source application that runs web pages on either physical or virtual web servers. It is one of the most popular HTTP servers, and it usually runs on standard HTTP ports such as ports 80 TCP, 443 TCP, and alternatively on HTTP ports such as 8080 TCP or 8000 TCP.

The nmap scan provided us with the exact version of the Apache httpd service. Usually, a good idea would be to search up the service version on popular vulnerability databases online to see if any vulnerability exists for the specified version.

In order to further enumerate the service running on port 80, we can navigate directly to the IP address of the target from our browser.

**Foothold**

we need to check for any default credentials or bypass the login page somehow. To check for default credentials, we could type the most common combinations in the username and password fields:

admin : admin

guest : guest

user : user

root : root

administrator : password

After attempting all of those combinations, we have still failed to log in. We could, hypothetically, use a tool to attempt brute-forcing the log-in page. However, that would take much time and might trigger a security measure.

The next sensible tactic would be to test the log-in form for a possible SQL Injection vulnerability.

If the code is vulnerable to SQL Injection attacks, you can modify the query through the log-in form on the web page to make the query do something that is not supposed to do - bypass the log-in altogether.

Note that we can specify the username and password through the log-in form on the web page. However, it will be directly embedded in the $sql variable that performs the SQL query without input validation. Notice that no regular expressions or functions forbid us from inserting special characters such as a single quote or hashtag. This is a dangerous practice because those special characters can be used for modifying the queries. The pair of single quotes are used to specify the exact data that needs to be retrieved from the SQL Database, while the hashtag symbol is used to make comments. Therefore, we could manipulate the query command by inputting the following:

Username : admin’#

We will close the query with that single quote, allowing the script to search for the admin username. By adding the hashtag, we will comment out the rest of the query, which will make searching for a matching password for the specified username obsolete. Since we have skipped the password search part of our query, the script will now only search if any entry exists with the username admin. In this case, we got lucky. There is indeed an account called admin, which will validate our SQL injection and return the 1 value for the $count variable, which will be put through the if statement, allowing us to log-in without knowing the password. If there was no admin account, we could try any other accounts until we found one that existed (administrator, root, john_doe, etc). Any valid, existing username would make our SQL injection work.

In this case, because the password-search part of the query has been skipped, we can throw anything we want at the password field, and it will not matter:

Passoword : abc123

After pressing the log-in button, the exploit code is sent, and as suspected, we are presented with the flag.

# Sequel

Learning how to navigate databases is of considerable importance because most of the critical data is stored in them, including usernames and passwords, which can potentially be used to gain the highest privileged access to the target system.

That data could represent usernames, passwords, posts, messages, the exact date when the users joined, and other information - depending on the website’s purpose.

For example, if there is a website that has a small social network and e-commerce section, there would be a need for several separate sections which should not be inter-accessible:

-   one containing user’s private information, such as emails addresses, geolocations, log-in history, and attached IP addresses, real names, credit card information, and more.
-   one containing publicly searchable information such as products, services, music, videos, and other types.

An excellent example of how an SQL Service typically operates is the log-in process utilized for any user. Each time the user wants to log in, the web application sends the log-in page input (username/password combination) to the SQL Service, comparing it with stored database entries for that specific user. Suppose the specified username and password match any entry in the database. In that case, the SQL service will report it back to the web application, which will, in turn, log the user in, giving them access to the restricted parts of the website. Post-log-in, the web application will set the user a special permission in the form of a cookie or authentication token that associates his online presence with his authenticated presence on the website. This cookie is stored both locally, on the user’s browser, and the webserver.

**Enumeration**

`**$ sudo nmap -sC -sV {target_IP}**`

We only found one port - 3306, which runs a service named MySQL - MariaDB.

MySQL is a service designed for database management: creating, modifying, and updating databases, changing and adding data, and more.

**Foothold**

In order to communicate with the database, we need to install either mysql or mariadb on our local machine. To do that, you need to run the following command. Make sure you include the * symbol at the end of the command to include all the related MySQL packages available.

**`$ sudo apt update && sudo apt install mysql*`**

After the installation is complete, you can run the following command to see how the service commands are used.

**`$ my sql --help`**

Note that the MySQL clients usually authenticate with the service with a username/password combination. However, it is essential to test for passwordless authentication, as there might be an intentional misconfiguration in the service, which would allow personnel to easily log into the service during the deployment stage of the project to easily interact with it before making it available to other colleagues. In the present situation, an initial attempt can be to attempt a log-in as the ‘root’ user, naturally having the highest level of privileges on the system.

**`$ mysql -h {target_IP} -u root`**

-h : connect to host

-u : user for log-in if not current user.

With luck, our connection is accepted without a password requirement. We are placed in a MySQL service shell from where we can explore the tables and data therein that are available to us.

The _commands_ we are going to use are _essential for navigation:_

SHOW database; : prints out the databases we can access.

USE {database_name}; : set to use the database named {database_name}.

SHOW tables; : prints out the available tables inside the current database.

SELECT * FROM {table_name}; : prints out all the data from the table {table_name}.

Note that it is essential to end each command with the ; symbol, as it declares the end of the command. Apart from that, SQL is a query-oriented language, which means that you supply it with one query at a time.

`>**SHOW databases;**`

From the output, the htb database seems of value. In order to see what rests inside it, we will need to “select” the htb database as the active one - the database we want to actively interact with for our subsequent commands. To achieve this, the “USE htb;” command can be used.

`**> USE htb;**`

We have successfully changed the database. The next step is to check what tables does the ‘htb’ database contain. We can achieve this by following up with the “SHOW tables;” command.

`**> SHOW tables;**`

We have two tables: config and users. These can be checked sequentially for their content by using the SELECT * FROM {table_name} command, where {table_name} is the exact name of the table you want to explore, taken from the output above. Once we query the ‘config’ table for contents, the ‘flag’ entry is output in our terminal, alongside its’ value.

# Crocodile

Credentials could be lost somewhere in a publicly accessible folder which would let you login through a remote shell untended and unmonitored. A misconfigured service could be leaking information that might allow you to impersonate the digital identity of a victim. Any number of possibilities exist in the real world.

**Enumeration**
`sudo nmap -sC -sV {target_IP}`

We have two open ports: 21 and 80. Port 21 is the port dedicated to FTP (File Transfer Protocol), meaning that its' primary use is to transfer files between hosts on the same network.
Users could connect to the FTP server anonymously if the server is configured to allow it, meaning that we could use it even if we had no vaild credentials. Looking back at the nmap scan result, the FTP server is indeed configured to allow anonymous login:
" ftp-anon: Anonymous FTP login allowed (FTP code 230)"

To connect to the remote FTP server, we will need to specify the target's IP address. The prompt will then ask us for our login credentials, which is where we can fill in the _anonymous_ username. 
`ftp {target_IP}`

We will use _dir_ and _get_ to list the directories and manipulate the files stored on the FTP server. With the _dir_ command, we can check the contents of our current directory on the remote host, where we find two files.
Both files can easily be downloaded using the _get_ command. 
`ftp> get allowed.userlist`
`ftp> get allowed.userlist.passwd`

Termination of the FTP connection can be done by using the _exit_ command.

In order to read the content of the files we just downloaded, we can use the _cat_ command, followed by the name of the file we want to open.

**Foothold**
During the nmap scan, the service running on port 80 was reported as an Apache HTTP server. Typing in the IP address of the target into our browser's URL search bar results. It seems to be a storefront for a server hosting company.

We might get lucky and find an administrative panel login page that could help us find leverage against the target in combination with the credentials we extracted from the FTP server.
`gobuster dir --url http://{target_IP}/ --wordlist /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -x php.html`

One of the most interesting files gobuster retrieved is the /login.php page. Navigating manually to the URL (http://{target_IP}/login.php), we are met with a login page asking for a username/password.
If the lists of credentials we found had been longer, we could have used a Metasploit module or a login brute-force script to run through combinations from both lists faster. In this case the lists are relatively small.
After attempting several username/password combinations, we manage to log in and are met with a Server Manager admin panel. 

We successfully got the flag!

