# Stored Cross-Site Scripting Vulnerability in WonderCMS

Vendor and Product Information:

    Vendor: WonderCMS
    Product: WonderCMS
    Affected Version: 3.5.0
    Product URL: https://www.wondercms.com

# Executive Summary
WonderCMS 3.5.0 is vulnerable to a Blind Stored Cross-Site Scripting (XSS) in the homepage content editor. An authenticated attacker can inject arbitrary JavaScript payloads into the homepage content, which will be executed in the context of any user who visits the affected page.

# Issue Description
An authenticated attacker with access to the admin panel can inject a malicious JavaScript payload into editable content fields (e.g., the Home Page ditor). When any privileged or unprivileged user visits the affected page, the script is executed in their browser, leading to stored Cross-Site Scripting (XSS). The vulnerability is blind in nature as it executes without immediate reflection.

# Proof Of Concept

https://drive.google.com/file/d/1JE4v_YbkQwKQKNI4Zc6ddxWcB3napwg_/view?usp=sharing

# Impact:

- When viewed by any user (even themselves), the injected payload executes. 
- Can lead to session hijacking, credential theft, or other malicious behaviors.  
- Requires only authenticated access, which is available to CMS admins.

# Remediation:

Implement proper input validation and output encoding to prevent malicious code from being injected into the web application. Use server-side validation to ensure that user input is properly sanitized before being stored in a database or displayed on a web page. Use output encoding to ensure that any user input that is displayed on the web page is properly encoded to prevent malicious code from being executed.

# References:

https://portswigger.net/web-security/cross-site-scripting/stored
https://owasp.org/www-community/attacks/xss/

# Weakness Enumeration:

https://cwe.mitre.org/data/definitions/79.html
