
2024-12-24 12:21

Status:

Tags:


# Node Js - Security



2024-12-23 23:09

Status:

Tags:

## Learning objectives

- OWASP resources and security threats
- Cross-site scripting and denial of service attacks
- Managing packages in a Node.js app
- Adding two-factor and read-only tokens with npm
- Using prepared statements for SQL/NoSQL
- Encrypting user data and session management
- Adding HTTPS protocol to an application
- Using cookie attributes
- Tools for testing

Here are the key takeaways from the "Node.js: Security" course:  
  

- **Understanding Security Threats**: Learn about common security risks in Node.js, including cross-site scripting, denial of service attacks, and server-side injection.
- **Best Practices**: Discover best practices for managing packages, handling data securely, and securing the server level, including using HTTPS, rate limiting, and cookie attributes.
- **Tools for Testing**: Get familiar with tools like Snyk and Burp for testing and finding vulnerabilities in your Node.js projects.

# OWASP    
https://owasp.org/
https://github.com/OWASP/NodeGoat

OWASP stands for the Open Web Application Security Project. It's a community that provides resources to help you understand and protect against security threats in web applications.
- **Key Resources**:  
    - **Social Media Groups**: Join OWASP's Facebook group and other social networks to stay updated.
    - **Attack References**: Find detailed information on different types of attacks, like how they work and what risks they pose.
    - **Code Snippets**: Get examples of code to help protect against specific security threats.
    - **Vulnerabilities Section**: Learn about potential weak spots in your application that could be exploited.
    - **Node.js Goat Project**: A specific project for securing Node.js applications with the latest threat information.

https://owasp.org/www-project-developer-guide/draft/training_education/owasp_top_ten/
https://www.jit.io/resources/security-standards/the-in-depth-guide-to-owasps-top-10-vulnerabilities

- **Server-side injection** involves injecting untrusted data into the server as part of a command or query, which can trick the server into executing malicious code.
- **Common methods** used by attackers include `eval`, `setTimeout`, `setInterval`, and `function` methods to process harmful code.
- **Preventive measures** include:  
    - Always validating and sanitizing user input.
    - Avoiding the use of `eval`, `setTimeout`, `setInterval`, and `function` to parse user input.
    - Using `JSON.parse` for parsing user input and safer parse methods like `parseInt` for type conversion.
    - Including `use strict` in your code to enforce stricter parsing and error handling.


**server validators use** 
1. validator.js package 
2. safe-regex package
3. helmet https://helmetjs.github.io/
4. crypto
5. window.localstorage -> session storage
6. letsencrypt.org ssl cetificate
7. rate limiting expree-rate-limit -> minimizing dos attack denial of service
![[Pasted image 20241224010555.png]]
8. redis
9. csrf protectionf for all api endpoints -> csurf 
![[Pasted image 20241224010856.png]]

10. cookie attr -> only accessible by https, avoid by using the js
![[Pasted image 20241224011117.png]]

https://github.com/expressjs/cookie-session


### Introduction to OWASP dependency check

**Dependency check**

![[Pasted image 20241224012015.png]]



https://owasp.org/www-project-developer-guide/draft/implementation/dependencies/dependency_check/

https://jeremylong.github.io/DependencyCheck/general/thereport.html

1. owasp depenancy
2. Snyk
3. Burp

![[OWASP Top 10-2017 (en).pdf]]
# Reference

# Reference