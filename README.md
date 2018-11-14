# Project 8 - Pentesting Live Targets

Time spent: **3** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue
**Vulnerability #1: SQL Injection Attack**
 <img src="https://github.com/eddenk/Codepathweek8/blob/master/SQL_Injection.gif" alt="SQL_Injection" title="SQL_Injection" />
**Walkthrough:**
1.	Go to any salepersons profile (for example: ex. /blue/public/staff/salespeople/show.php?id=9)
2.	After the link is visited, inject SQL statement ‘ OR 1=1—'



**Vulnerability #2: Session Hijacking Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/Session_Hijacking.gif" alt="Session_Hijacking" title="Session_Hijacking" />
**Walkthrough:**
1.	An unknown user(attacker) changes the PHPSESSION of the site. (using: https://35.184.88.145/blue/public/hacktools/change_session_id.php)
2.	When the admin is logged in, attacker is able to steal the session if of the admin using the /hackertool/ and is able to bypass the need for logging in with a username and password.



## Green

**Vulnerability #1: Enumeration Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/Enumeration_Attack.gif" alt="Enumeration_Attack" title="Enumeration_Attack" />
**Walkthrough:**
1.	Try and login and type a username that you know exists on the database, logging in with the wrong password.
2.	Now, attempt to login for a user that you don’t know if it exits on the database.
3.	A username that exists on the database with the wrong password will be printed in **bold**
4.	But, a username that does exist with the wrong password inputted will not be in bold.


**Vulnerability #2: Stored Cross Site Scripting Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/XSS_Attack.gif" alt="XSS_Attack" title="XSS_Attack" />
**Walkthrough:**
1.	Go to the Contact Form of the website and write feedback with the following script in the comment section
<script>alert(‘Edden found the XSS!’)</script>
2.	Log into the site
3.	View feedback, and the user with alerted.


## Red

**Vulnerability #1: IDOR Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/IDOR_Attack.gif" alt="IDOR_Attack" title="IDOR_Attack" />
**Walkthrough:**
1.	When you are on the “Find a Salesperson” section of the site, there is a query string of an id parameter which is exploitable.
Ex: ?id=9
2.	Change the id parameter until you find information that should not be accessible. 

**Vulnerability #2: CSRF Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/CSRF_Attack.gif" alt="CSRF_Attack" title="CSRF_Attack" />
**Walkthrough:**
1.	Vulnerability in the user’s section of Globitek Red
2.	Go to a user’s page, and inspect the page source
3.	Create a new HTML file using the same edit form and resubmit it without using a csrf token.
4.	Open the vulnerable html file and update the user information, and it will change the user information directly on the website. 



## Notes

Describe any challenges encountered while doing the work


