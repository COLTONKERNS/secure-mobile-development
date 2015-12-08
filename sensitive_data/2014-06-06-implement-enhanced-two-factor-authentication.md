---
layout: guide
title: "Implement Enhanced / Two-Factor Authentication"
description: "Weak passwords do not offer significant protection."
published: 1
categories:
  - handling-sensitive-data
series:
  name: Handling Sensitive Data
  index: 33
order: 209
--- 

## Details 

Attackers can tamper with or install a backdoor on an app, re-sign it and publish the malicious version to third-party app marketplaces. Such attacks typically target popular apps and financial apps.

## Remediation

A password should not be simplistic. Support or require complex passwords, including length of at least six alphanumeric characters (more characters is always stronger). Requiring the selection of a secret word or icon (which the user does not create themselves) as part of the log-in process can help protect users' accounts in the event they re-use passwords and their password was exposed as part of another data compromise.

In some cases, a username and password does not provide sufficient security for a mobile app. When sensitive data or transactions are involved, implement two-factor authentication. This may not be feasible every time a user logs in but can be used at intervals or when accessing selected functions. Consider step-up authentication methods to provide normal access to non-transactional areas but require a second layer of authentication for sensitive functions.

Options for enhanced authentication include:

 * Additional secret word/icon.*
 
 * Additional code provided by SMS or email -- but beware that an attacker will likely have access to both on a stolen device.*
 
 * Password plus additional user-known value, for example user-selected personal factor.*
 
 * Security questions and answers, selected by the user in advance (e.g. during registration).*

For the highest level of security, use one-time passwords that require the user to not only possess the correct credentials, but also a physical token including the one time password.

## CWE/OWASP 

 * [M5 - Poor Authorization and Authentication](https://www.owasp.org/index.php/Mobile_Top_10_2014-M5)
 * [CWE-308: Use of Single-factor Authentication](http://cwe.mitre.org/data/definitions/308.html)
