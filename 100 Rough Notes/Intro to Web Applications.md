# Session 1
## Intro to Web Applications

"Web applications" are more interactive

"Websites" are the old static types (Web 1.0)

Documented and methodical approach to testing a web app from the ground

   https://github.com/OWASP/wstg/tree/master/document/4-Web_Application_Security_Testing

-------------------
## Types of Attacks

https://cheatsheetseries.owasp.org/index.html
### SQL injection

   Obtaining Active Directory usernames and performing a password spraying attack against a VPN or email portal.

### File Inclusion

   Reading source code to find a hidden page or directory which exposes additional functionality that can be used to gain remote code execution.

### Unrestricted File Upload

   A web application that allows a user to upload a profile picture that allows any file type to be uploaded (not just images). This can be leveraged to gain full control of the web application server by uploading malicious code.

### Insecure Direct Object Referencing (IDOR)

When combined with a flaw such as broken access control, this can often be used to access another user's files or functionality. An example would be editing your user profile browsing to a page such as /user/701/edit-profile. If we can change the 701 to 702, we may edit another user's profile!

Broken Access Control Another example is an application that allows a user to register a new account. If the account registration functionality is designed poorly, a user may perform privilege escalation when registering. Consider the POST request when registering a new user, which submits the data username=bjones&password=Welcome1&email=bjones@inlanefreight.local&roleid=3. What if we can manipulate the roleid parameter and change it to 0 or 1. We have seen real-world applications where this was the case, and it was possible to quickly register an admin user and access many unintended features of the web application.

  

# Web Application Layout

----------------------

## Web Application Infrastructure

**Client-Server**  

* Clients (users/devices) request services or data

* A centralized **server** processes the requests and sends back responses

* Common in web apps, games, and corporate systems

* Simpler architecture, easier to manage initially  

**One Server**

* All services (app, database, files) hosted on a **single physical or virtual server**

* Easy to deploy and maintain

* Good for **small-scale apps**, local networks, or learning

* **Single point of failure** — if it goes down, everything stops

**Many Servers – One Database**

* Multiple app or service servers **connect to a shared database**

* Allows for **load balancing**, better performance, and scalability

* The **database becomes the bottleneck** if not scaled properly

* Used in many modern web apps (e.g., microservices)

**Many Servers – Many Databases**  

* Each server has **its own database** (or sharded/distributed databases)

* Can improve **fault tolerance**, scalability, and data locality

* More complex to manage: **syncing, consistency, data integrity**

* Common in large-scale systems like global SaaS platforms or distributed services


# Web Application Components

--------------------------

1. Client

2. Server

  - Webserver

  - Web Application Logic

  - Database

3. Services (Microservices)

  - Paypal, Stripe, Google Sign-in/Auth

  - Completely modular (separate from your actual code. Good for not keeping everything in one basket)

  - 3rd Party Integrations

  - Web Application Integrations

4. Functions (Serverless)

  

# Front End

--------------

- Everything having to do with the UI/UX of the clients view. Including the main three languages HTML, CSS, JS.

- These are other tasks related to the front end, but still boil down to our main three languages.

- Visual Concept Web Design

- User Interface (UI) design

- User Experience (UX) design

  

# Back End

-------------

**Back end servers**

   - As implied will host our other components (web servers,DB, APIs, DNS)

   - The architecture applied here will determine security benefits/flaws (many databases,many servers etc..)

**Web Servers**

   - Handles the content given when requesting a simple web page, the initial HTML/JS/CSS files.

   - Handles the HTTP requests (GET, POST, DEL, UPDATE) and connection to the DB when needed

   - Apache, NGINX, and IIS

**Databases**

   - Stores our data

   - MySQL, Oracle, MongoDB

**Development Frameworks**

   - Fancy name for the frameworks that build your Web App

   - Laravel, Spring, Django

# White box testing

-----------------

**White box testing** (also called clear box or glass box testing) is a software testing method where the tester knows the internal workings of the system — the code, architecture, and logic

**Key Points**

   - Tester has full visibility into the source code.

   - Tests are designed to cover specific code paths, branches, and conditions.

   - Helps find hidden bugs, logic errors, or security flaws inside the software.

   - Often done by developers or security testers who can read and understand the code.

  

# Black Box testing

-----------------

Opposite of white box testing

Usually means external hacking or cyber warfare attack with no knowledge of the system being attacked.

No information, we are in blind figure out what we can gather as we go.

  

OWASP Top 10 Web app vulnerabilities
https://owasp.org/www-project-top-ten/

  

# URL Encoding

-------------

Basically percent encoding. Only ASCII can be used in URLs, thats why you will see %20 as a replacement for space.

Others like !,",#,$ have a percentage encoding used %21,%22, etc..

# Session 2
# Front End Vulnerabilities

-----------------------------

* ### HTML injection
	Occurs when unfiltered user input is displayed on the page. This can either be through retrieving previously submitted code, like retrieving a user comment from the back end database, or by directly displaying unfiltered user input through JavaScript on the front end.  

* ### Cross-Site Scripting (XSS) 
	Similar to HTML injection but injects javascript code. More advanced attacks due to JS capabilities

- ### Reflected XSS
	Occurs when user input is displayed on the page after processing (e.g., search result or error message).

- ### Stored XSS
	Occurs when user input is stored in the back end database and then displayed upon retrieval (e.g., posts or comments).

- ### DOM XSS: 
	Occurs when user input is directly shown in the browser and is written to an HTML DOM object (e.g., vulnerable username or page title).

  

* Cross-Site Request Forgery (CSRF)

   Utilize XSS vulnerabilities to perform certain queries, and API calls on a web application that the victim is currently authenticated to.

   Example: crafting a JavaScript payload that automatically changes the victim's password to the value set by the attacker.

  

Prevention

To stop these vulnerabilities it all comes down to any where the user can interact or give input (comments, posts, text fields). Especially if they are stored on the backend, as thats how most of these will gain the most of their exploit, from the server displaying it. Filtering is the best way, listed below are the ways.

Sanitization: Removing special characters and non-standard characters from user input before displaying it or storing it.

Validation: Ensuring that submitted user input matches the expected format (i.e., submitted email matched email format)

Web application firewall (WAF)

https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html

  
  

Back End Components

------------------------------------

LAMP Linux, Apache, MySQL, and PHP.

WAMP Windows, Apache, MySQL, and PHP.

WINS Windows, IIS, .NET, and SQL Server

MAMP macOS, Apache, MySQL, and PHP.

XAMPP Cross-Platform, Apache, MySQL, and PHP/PERL.

  

* Web Servers

is an application that runs on the back end server, which handles all of the HTTP traffic from the client-side browser, routes it to the requested pages, and finally responds to the client-side browser. (HTTP requests, codes like 404 or 200)

  

Example You do a web request, 80 or 443, does the site exist, is he authorized, respond with the content (html/css files) and code (200 OK).

IMPORTANT: The pages and files that the webserver processes and routes traffic to are the WEB APPLICATION core files.

  

Web servers also accept various types of user input within HTTP requests, including text, JSON, and even binary data (i.e., for file uploads).

  

Web Server Frameworks

Apache host more than 40% of all internet websites. Runs on PHP (Apple, Adobe)

NGINX 2nd most common, 30% of all sites. Runs on C (Google,Facebook,Twitter)

  

* Databases

Relation (SQL)

   Typically use SQL for managing its data, MySQL being the most popular.

Non-Relational (NoSQL)

   Does not use tables, rows, columns, primary keys, relationships, or schemas.

   Very scalable and flexible

 Storage models (the architecture used to store data)

   Key-Value: stored in JSON, standard key-data pair format. (MongoDB, ElasticSearch, Apache Cassandra)

   Docuent-Based: stores in complex JSON objects, while storing the rest in key-value

   Wide-Column

   Graph

  

Use in Web Apps

* Development Frameworks & APIs

  

Important self-notes

The process of constantly asking for HTML requests is outdated, as now we have SPA's (Single Page Apps)

As the name implies this single page is a full on app that will change dynamically without having to be requesting again and again a new HTML file..

How? 

Using Javascript bundles that will change the site within your web browser, 

and any missing info thats needed (comments, product names, prices) from the DB it uses API calls (returns JSON\text info) that go to the web server that then obtain the info from the DB server, finally return back. Browser → API call → Web Server → DB →  … → Browser

API calls essentially bypass the need to request new whole pages, instead reusing that same page.


# Session 3

Data Flow 
[Browser]
   ↓ (HTTP request for static HTML/JS)
[Web Server]
   ↓ (Serves React app)
[Browser runs React app]
   ↓ (API call via fetch/axios to backend)
[API Server]
   ↓ (SQL call)
[Database Server]
   ↑ (Query result)
[API Server]
   ↑ (JSON response)
[React Frontend]

Back End Components
-------------------------------
* Development Frameworks & APIs
  "A development framework is a pre-structured set of tools, libraries, and conventions that help you build applications faster, more cleanly, and with fewer bugs."
  
  Meaning it can refer to ANY of the typical web frameworks used to help in faciliating the process
  This can apply to any of the development areas listed below.
  Frontend, Backend, APIs, Database, Full-Stack(encompasses all previous)

APIs
   A set of functions, libraries, or protocols that allow software to interact directly with other software or hardware — without using HTTP or web technologies.
   Explanation: An interface/app that allows one application or piece of software to communicate with another (like a database or system library). It's like a translator or mediator that lets two systems — which wouldn't naturally understand each other — exchange data or commands in a standardized way.
   
   Plenty of diff API's that arent Web API's. Such as OS, SDK, DB, and Hardware APIs
   
Web APIs
  A set of HTTP-based rules that allows the frontend or web server to communicate with the backend. It sends requests (like GET, POST) and receives data (usually JSON)
  Explanation: In this case we see that the communication is done through HTTP (hence web), and allows front end (react) to communicate with the DB (SQL). SQL cant understand HTTP calls and react cant write SQL language = Web api needed for translation/communication.

Standard style/language for Web APIs
 SOAP Simple Objects Access Protocol
  This style uses XML
  Still uses HTTP, so the communication is similar to REST APIs.
  But instead of hitting a GET /api/user/1, you can only send as POST to a single endpoint like /UserService.
  Inside the body is an XML-formatted envelope that tells the server what action you want. Example below (Looks like HTML)
  <soap:Envelope
  xmlns:soap="http://www.example.com/soap/soap/"
  soap:encodingStyle="http://www.w3.org/soap/soap-encoding">
 REST Representational State Transfer
 "An API design style that uses standard HTTP methods to operate on resources identified by URLs. It is stateless, scalable, and commonly used for web 
  APIs to enable easy communication between frontend and backend."
  Uses standard HTTP methods:
    GET (retrieve data)
    POST (create data)
    PUT (update data)
    DELETE (remove data)
  Data is usually in JSON format
  Resources (data entities) are represented as URLs/endpoints, e.g., /users/123.

Back End Vulnerabilities
-----------------------------
* Common Web Vulnerabilities
  Broken Authentication
   Refers to vulnerabilities that allow attackers to bypass authentication functions,a normal user to become an administrator without having the privileges to do so.
  Broken Access Control
   Broken Access Control refers to vulnerabilities that allow attackers to access pages and features they should not have access to. For example, a normal user gaining access to
   the admin panel.
  Types of attacks
   Malicious File Upload
   Command Injection: Being able to execute commands on a server. (For instance a text field thats used in executing OS commands, and you specify additional to the params | ip a)
    https://www.exploit-db.com/exploits/45274
   SQL Injection (SQLi)
    Same as command injection but you are dealing with SQL now. Text field that interacts with SQL DB or most likely the API(SQL) -> DB. Manipulating the text field to add
    additional query results
* Public Vulnerabilities
  Public CVE
   A record and score assigned to a vulnerability.
   Proof of concept is usually given and these exploits available for public use
   First step in identify vulnerabilities in a system
   "The first step is to identify the version of the web application. This can be found in many locations, like the source code of the web application. For open source web 
    applications, we can check the repository of the web application and identify where the version number is shown (e.g,. in (version.php) page), and then check the same page on 
    our target web application to confirm."
   Some public exploit database sites
    https://www.exploit-db.com/
    https://www.rapid7.com/db/
    https://www.vulnerability-lab.com
   Common Vulnerability Scoring System (CVSS)
    A score system that takes many different variables into account for how sever a vulnerability/exploit is.
    Used by many organizations and governments
    NVD (https://nvd.nist.gov/)
     Provides CVSS scores for almost all know, publicly disclosed vulnaribilities.
     Only provides Base scores, temporal and enviromental will need to be provided additionally.