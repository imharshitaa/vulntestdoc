sophos testing

URL - 

https://central.sophos.com/ 

https://central.sophos.com/manage/central-login?forwardTo=%2Flogin

https://cloud-assets.sophos.com/assets/mfe/791152a3b6196199b9ceb1bd2dd27ab1593850c5/central-login/styles.css

---------------------------

1 - automated Tested on zap active scan - showed alert server leaks version information on HTTP response header - server name details.
![1 zap test leak server details](https://github.com/user-attachments/assets/51f0a165-4ce9-4720-b13b-bbc9a566167d)

2 - inspect page html head code - Cross-Domain JavaScript Source Inclusion - external javascript without validation.
![2 external javascript without validation](https://github.com/user-attachments/assets/2df05fec-8e51-4b06-9342-39d7626ce3d1)

3 - inspec page html head code - JavaScript Dependency Vulnerabilities - external domain source without validating.
![3 javascript dependency vuln external domain](https://github.com/user-attachments/assets/da0e8243-0d4b-4dbe-a890-923f8c5ec0aa)

4 - from zap alert for cross domain javascript source file inclusion - content security policy headers not mentioned which could lead to potential XSS Attacks. 
potential information leakage for id data and cause unauthorized access. 
![4 security headers not mentioned   client id info leaked](https://github.com/user-attachments/assets/990ec7d9-9e43-4083-b884-ddf122ba97fb)

5 - mfa not supported causing unauthorized access.
![5 MFA LACKING](https://github.com/user-attachments/assets/0fc4574c-69a3-48c5-b0ae-94bab885427d)

6 - potential Cross-Site Scripting (XSS) vulnerability reflected - on login page - input field accepts the payload script tag - error message reflects the same input - might allow to inject malicious scripts in user input. 
![6 reflected xss attack user input display error message](https://github.com/user-attachments/assets/2070ffd9-889d-48cd-81e5-4faede58c059)

7 - cross domain misconfiguration - header access control allow origin * - leads to unauthorized access to any source API or domain. 
![7 CORS header - unauthorized access to API - domains](https://github.com/user-attachments/assets/ec8bb199-41b0-4c34-908d-66b2d7e6a82e)












