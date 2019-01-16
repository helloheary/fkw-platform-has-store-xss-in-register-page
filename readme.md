[description]

An fkw platform v1 has store xss in register page.

 

[Additional Information]

The vulnerability constructs a malicious payload when submitting the registration information, and fills in the registration information. After the registration is successful, when the login is entered, the personal information page is triggered to be triggered by xss.

At the same time, you can also fill in the malicious payload by modifying the information in the personal information page, and you can also implement the storage type xss.

 

[Vulnerability Type]

Cross Site Scripting (XSS)

 

[Vendor of Product]

fkw platform v1

 

[Attack Vectors]

Submit the registration information in POST mode, enter the following payload in the "Name" field in the info parameter.

```
Test"><img src=x onerror=confirm(/xss/)>
```



[Vulnerability verification]

\1. On the registration page, enter your personal information, including malicious payloads.

 

\2. After clicking Register, successfully register and enter the personal information page.

 

\3. On the "Personal Information" page, you can see the xss code that pops up.

 

Of course, after entering the background, it is also achievable to modify the content of the name field in the personal information page.