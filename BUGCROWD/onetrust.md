Target Location - https://pentest-app.onetrust.com/

Target category - Web App

VRT - Cross-Site Scripting (XSS)

Bug URL - https://pentest-app.onetrust.com/auth/login

--------------------------

Description:

Cross-Site Scripting from CSP wildcard directive
-
Content security policy is used to get rid of XSS attacks. And if they are not build and revised properly it can lead to XSS attacks.
XSS cross site scripting attack allows attacker to inject malicious code into input of the web page.

Business Impact
-
XSS could lead to data theft through the attacker’s ability to manipulate data through their access to the application, and their ability to interact with other users, 
including performing other malicious attacks, which would appear to originate from a legitimate user. 
These malicious actions could also result in reputational damage for the business through the impact to customers’ trust.

Steps to Reproduce
- 
1. Automated scan on zaproxy - showed alert as csp wildcard directive.
2. Inspect in page source - Network > login > content security policy header > check for *, unsafe-eval, unsafe-inline > potential XSS vuln --> the wildcards were missing.
3. Manual test - login page enter invalid email - shows error in the next page before entering password - potential XSS injection point.

Proof of Concept (PoC)
-

![1 zap testing](https://github.com/user-attachments/assets/515d42bc-1793-4795-ab38-e276ea1e102f)

![2 inspect page](https://github.com/user-attachments/assets/e5f82db1-2bf6-4d47-991e-6aae1ca35ef6)

![3 invalid show before entering password](https://github.com/user-attachments/assets/9cc99cdf-38d6-4460-881d-b202bf6fc12c)


Mitigation:
- 
Revise content security policy.
Implement input validation for fields that display error messages.
Test using security tools regularly.










