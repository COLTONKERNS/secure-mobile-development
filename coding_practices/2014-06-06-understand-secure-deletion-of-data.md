---
layout: guide
title: "Understand Secure Deletion of Data"
description: "On Android, calling file.delete() will not securely erase the file, and as long as it is not overwritten it can be carved from a physical image of the device."
published: 1
categories:
  - coding-practices
series:
  name: Coding Practices
  index: 36
order: 107
--- 

## Details 

On Android, calling file.delete() will not securely erase the target file, and as long as it is not overwritten it can be carved from a physical image of the device. Traditional approaches to wipe a file generally do not work on mobile devices due to the aggressive management of the NAND Flash memory.

## Remediation

Operate under the assumption that any data written to a device can be recovered. In some instances, encryption might add an additional layer of protection.

The following is not recommended for most applications, but it may be possible to delete a file and overwrite all available space with a large file (which would force the NAND Flash to erase all unallocated space). Drawbacks of this technique include wearing out the NAND Flash, causing the app and the entire device to respond slowly, and significant power consumption.

Wherever possible, avoid storing sensitive data on the device. See [BPXX Avoid storing sensitive data].

Encrypting the sensitive data stored in files, rewriting the contents of the file and syncing before deleting can help, but as described above, they're not fully reliable solutions to the problem.

## References 

 * [General Purpose Cypto](https://developer.apple.com/library/mac/documentation/security/conceptual/cryptoservices/GeneralPurposeCrypto/GeneralPurposeCrypto.html)
 
## CWE/OWASP

 * [M4 - Unintended Data Leakage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M4)
 * [CWE-312: Cleartext Storage of Sensitive Information](http://cwe.mitre.org/data/definitions/312.html)
 * [CWE-313: Cleartext Storage in a File or on Disk](http://cwe.mitre.org/data/definitions/313.html)
