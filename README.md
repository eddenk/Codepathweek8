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
(x)**Vulnerability #1: SQL Injection Attack**
 <img src="https://github.com/eddenk/Codepathweek8/blob/master/SQL_Injection.gif" alt="SQL_Injection" title="SQL_Injection" />
**Walkthrough:**
1.	Go to any salepersons profile (for example: ex. /blue/public/staff/salespeople/show.php?id=9)
2.	After the link is visited, inject SQL statement ‘ OR 1=1—'



[x]**Vulnerability #2: Session Hijacking Attack**
<img src="https://github.com/eddenk/Codepathweek8/blob/master/Session_Hijacking.gif" alt="Session_Hijacking" title="Session_Hijacking" />
**Walkthrough:**
1.	An unknown user(attacker) changes the PHPSESSION of the site. (using: https://35.184.88.145/blue/public/hacktools/change_session_id.php)
2.	When the admin is logged in, attacker is able to steal the session if of the admin using the /hackertool/ and is able to bypass the need for logging in with a username and password.
