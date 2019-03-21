# Website Test Report

## Issues Identified

There are generally xxx issues I have found from the work in progress ransomware dashboard website.

1. Password on login page is submitted using clear-text over http.

2. Submitting correct or wrong usernames can get different reponses. And there is no verification codes required. Usernames can be acquaried by brute force attack. Also the passwords.

3. The user doesn't exist reply contains the user typed username. There is a XSS vulnerability.

4. 'admin' account use weak password 'admin'.

5. The error alerts are all transfering via cookie session variable. There are simillar XSS vulnerabilities in all error messages by modifing the cookie.

6. JWT in cookie is used as user identity. But HttpOnly flag is not set. 

7. User password can be easily changed via clear-text http GET request. There is and no current passwrod required. Also no CSRF Token for this request. This may cause CSRF attack.

8. The logout action also has CSRF vulnerability.

9. After changing password, current account is not logout. Current JWT in cookie is still valid and all other cookies used in other browser are also not affected.

10. After logout, the cookie is also not destroied and valid for 1 week. The system only redirects brower to the login page and overwrite cookie to 'anonymous'. The original cookie can still be used to login and conduct all other operations.

## Recommendation on CSRF

Among all the observations addressed above, I believe the CSRF for changing other users' password should be the highest-risk vulnerability for this web application. Even the admin does not using a weak password, other users can still get the admin password by create an changing password link.

The possible fixes including:

1. Require old password for changing password

2. Generate random CSRF Token with expire time and secret for the form

 

