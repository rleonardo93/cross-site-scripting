# Cross Site Scripting (XSS)

## Overview
Cross-Site Scripting(XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicous code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or enconding it.

An attacker can use XSS to send a malicious script to and unsuspecting user.
The end user's browser has no way to know that the script should not be trusted, and will execute the script. Because it thinks the script came from a trusted source, the malicious script can access any cookies, session tokes, or other sensitive information retained by the browser and used with that site.
These scripts can even rewrite the content of the HTML page.

## Description
Cross-Site-Scripting (XSS) attacks occur when:
1. Data enters a Web application thorugh an untrusted source, most frequently a web request.
2. The data is included in dynamic content that is sent to a web user without being validated for malicious content.

The variety of attacks based on XSS is almost limitless, but they commonly include transmitting private data, like cookies or other session information, to the attacker, redirecting the victim to web content controller by the attacker, or performing other malicious operations on the user's machine under the guise of the vulnerable site.

## Types of XSS

### Stored XSS
Stored XSS generally occurs when user input is stored on the target server, such as in a database, in a message forum, visitor log, comment field, etc.
And then a victim is able to retrieve the stored data from the web application without that data being made safe to render in the browser. With the advent of HTML5, and other browser technologies, we can envision the attack payload being permanently stored in the victim's browser, such as an HTML5 database, and never being sent to the server at all.

### Reflected XSS
Reflected XSS occurs when user input is immediately returned by a web application in an error message, search result, or any other response that includes some or all of the provided by the user as part of the request, without that data being made safe to render in the browser and without permanently storing the user provided data.

### DOM Based XSS
DOM Based XSS is a form of XSS where the entire tainted data flow from source to sink takes place in the browser, i.e., the source of the data is in the DOM, the sink is also in the DOM, and the data flow never leaves the browser. For example, the source (where malicious data is read) could be the URL of the page(e.g., document.location.href), or it could be an element of the HTML, and the sink is a sensitive method call that causes the execution of the malicious data(e.g., document.write).
