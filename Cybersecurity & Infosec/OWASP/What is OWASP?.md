The Open Web Application Security Project maintains a regularly-updated list of the most pressing web application security concerns.

**What is OWASP?**

Is an international non-profit organization dedicated to web application security. One of OWASP’s core principles is that all of their materials be freely available and easily accessible. The materials they offer include documentation, tools, videos, and forums. Perhaps their best-known project is the OWASP Top 10.

**What is the OWASP Top 10?**

Is a regularly-updated report outlining security concerns for web application security, focusing on the 10 most critical risks. The report is put together by a team of security experts from all over the world. OWASP refers to the Top 10 as an ‘awareness document’ and they recommend that all companies incorporate the report into their processes in order to minimize and/or mitigate security risks.

**What’s changed in the Top 10 for 2021**

There are three new categories, four categories with naming and scoping changes, and some consolidation in the Top 10 for 2021. We’ve changed names when necessary to focus on the root cause over the symptom.
![[Screenshot 2022-03-08 at 15.44.40.png]]

##### A01:2021 - Broken Access Control
**Description**

Access control enforces policy such that users cannot act outside of their intended permissions. Failures typically lead to unauthorized information disclosure, modification, or destruction of all data or performing a business function outside the user’s limits.

Common access control vulnerabilities include:

-   Violation of the principle of least privilege or deny by default, where access should only be granted for particular capabilities, roles, or users, but is available to anyone.
-   bypassing access control checks by modifying the URL (parameter tampering or force browsing), internal application state, or the HTML page, or by using an attack tool modifying API requests.
-   permitting viewing or editing someone else’s account, by providing its unique identifier (insecure direct object references).
-   accessing API with missing access controls for POST, PUT and DELETE.
-   Elevation of privilege. Acting as a user without being logged in or acting as an admin when logged in as a user.

**How to prevent**

Access control is only effective in trusted server-side code or serverless API, where the attacker cannot modify the access control check or metadata.

Developers and QA staff should include functional access control unit and integration tests.

##### A02:2021 - Cryptographic failures
https://owasp.org/Top10/A02_2021-Cryptographic_Failures/

Previously known as Sensitive Data Exposure, which was broad symptom rather than a root cause. The renewed focus here is on failures related to cryptography (or lack thereof), which often leads to sensitive data exposure or system compromise. 

**_Description:_** the first thing is to determine the protection needs of data in transit and at rest. For example, passwords, credit card numbers, health records, personal information, and business secrets require extra protection, mainly if that data falls under privacy laws (GDPR), or regulations. 

**_How to prevent:_**
- classify data processed, stored, or transmitted by an application. Identify which data is sensitive according to privacy laws, regulatory requirements,  or business needs.
- Don't store sensitive data unnecessarily. Discard it as soon as possible. Data that is not retained cannot be stolen.
- Make sure to encrypt all sensitive data at rest.
- Ensure up-to-date and strong standard algorithms, protocols, and keys are in place; use proper key management.
- Encrypt all data in transit with secure protocols such as TLS with forward secrecy (FS) ciphers, cipher prioritization by the server, and secure parameters. Enforce encryption using directives like HTTP Strict Transport Security (HSTS).
- Disable caching for response that contain sensitive data.
- Do not use legacy protocols such as FTP and SMTP for transporting sensitive data. 
- Always use authenticated encryption instead of just encryption.

##### A03:2021 - Injection
**_Description:_** an application is vulnerable to attack when:
- user-supplied data is not validated, filtered, or sanitized by the application.
- Dynamic queries or non-parameterized calls without context-aware escaping are used directly in the interpreter.
- Hostile data is used within object-relational mapping (ORM) search parameters to extract additional, sensitive records.
- Hostile data is directly used or concatenated. The SQL or command contains the structure and malicious data in dynamic queries, commands, or stored procedures.

Source code review is the best method of detecting if applications are vulnerable to injections. Automated testing of all parameters, headers, URL, cookies, JSON. SOAP, and XML data inputs is strongly encouraged. 

**_How to prevent:_** preventing injection requires keeping data separate from commands and queries.
- the preferred option is to use a safe API, which avoids using the interpreter entirely, provides a parameterized interface, or migrates to Object Relational Mapping Tools (ORMs). 
- Use positive server-side input validation. This is not a complete defense as many applications require special characters, such as text areas or APIs for mobile applications.
- Use LIMIT and other SQL controls within queries to prevent mass disclosure of records in case of SQL injection.

##### A04:2021 - Insecure Design
