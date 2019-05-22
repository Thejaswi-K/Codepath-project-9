# Project 9 - Pentesting Live Targets

Time spent: 20 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The possible exploits are:
### Username Enumeration 
> Green

The developer used different classes. The developer used class "failed" which is not defined in the /green/public/styles.css file when a non existant user tries to login. The error displayed is not bold. But when existing user logs in the class "failure" is used.
### GIF Walkthrough  
![userenumeration](https://user-images.githubusercontent.com/34077891/58156790-cb6f0780-7c2b-11e9-90a7-3439481e89c6.gif)
 
 
 
### Insecure Direct Object Reference (IDOR)
> Red

When you change the id parameter the salesperson details are retrieved if there exists a user with that id. 
### GIF Walkthrough
![IDOR](https://user-images.githubusercontent.com/34077891/58156894-08d39500-7c2c-11e9-842f-49570a541e0a.gif)



### SQL Injection (SQLi)
> Blue

We can inject "%27%20OR%20SLEEP(5)=0--%27" into the id parameter's value and make the server sleep for 5 seconds
### GIF Walkthrough
![SQLi](https://user-images.githubusercontent.com/34077891/58156947-256fcd00-7c2c-11e9-967a-e328a52a7184.gif)



### Cross-Site Scripting (XSS)
> Green

we can insert a blind XSS through the feedback form. It gets triggered when admin tries to open the list of feedback
### GIF Walkthrough
![XSS](https://user-images.githubusercontent.com/34077891/58157914-2d307100-7c2e-11e9-9194-4aa46b6202a8.gif)



### Cross-Site Request Forgery (CSRF)
### Session Hijacking/Fixation
> Blue

Web Browsers: Chrome and Internet Explorer
We can log in to the blue website in Chrome using the pperson account. Once logged in, We can go to https://104.198.208.81/blue/public/hacktools/change_session_id.php and use this tool to copy the session ID. We can then launch Internet Explorer and go to the blue website login page. We can go to the change_session_id.php page and paste the session ID from the Google Chrome session. When we go back to the blue login page in Internet Explorer, click Public, and we get logged into the portal as if the user pperson was logged in already.

Each version of the site has been given two of the six vulnerabilities.

## Blue

Vulnerability #1: SQLi

Vulnerability #2: Session Hijacking


## Green

Vulnerability #1: User Enumeration

Vulnerability #2: XSS


## Red

Vulnerability #1: IDOR

Vulnerability #2: CSRF


## Notes

Describe any challenges encountered while doing the work

