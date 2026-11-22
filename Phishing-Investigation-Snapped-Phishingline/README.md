Phishing Investigation and Credential Harvesting Analysis

Project Overview

This project documents a hands-on phishing investigation completed through TryHackMe. The exercise involved investigating a suspicious phishing URL, examining a downloaded phishing kit, analysing PHP source code, identifying credential-harvesting behaviour, and decoding a flag using CyberChef.

Objectives

Investigate a suspicious phishing URL.

Examine downloaded phishing-related files.

Perform static analysis of PHP scripts.

Identify credential collection and data exfiltration mechanisms.

Extract indicators of compromise (IOCs).

Decode an encoded flag using CyberChef.

Tools Used

Firefox: Investigating the phishing URL and navigating directories.

7-Zip: Extracting the downloaded archive.

Text Editor: Inspecting PHP source code and configuration files.

CyberChef: Decoding Base64-encoded data and reversing the decoded output.

TryHackMe: Hands-on cybersecurity learning environment.

Investigation and Methodology

1. Phishing URL Investigation

Investigated a suspicious URL associated with a fake Office 365 login page and explored the available web directories.

2. Phishing Kit Extraction

Downloaded and extracted the Update365 archive. Identified several suspicious files, including:

index.php

blocker.php

submit.php

script.st

robots.txt

3. Static Code Analysis

Inspected the PHP scripts without executing them.
Key observations:

The phishing kit collected email addresses and passwords.

It recorded victim IP addresses and browser User-Agent information.

It used geolocation functionality to identify victims' countries.

It implemented password-length validation.

It redirected victims after credential submission.

4. Credential Exfiltration Analysis

Identified an email destination in submit.php:xxxxx
The script used PHP's mail function to transmit collected credentials and victim information.
Another destination was identified in script.st, demonstrating that different components of the phishing kit referenced separate email destinations.

5. Evasion Analysis

Inspected blocker.php and identified functionality intended to restrict access from certain automated scanners and suspicious visitors.

6. Flag Recovery and Decoding

Located the flag.txt file through the phishing URL's directory structure.
Used CyberChef with the following operations:

From Base64

Reverse

Successfully decoded the flag and completed the challenge.

Key Findings

Identified a credential-harvesting phishing kit impersonating Office 365.

Confirmed the collection of sensitive login information.

Identified credential exfiltration through email.

Observed IP address and geolocation collection.

Identified anti-analysis and access-restriction functionality.

Successfully recovered and decoded the challenge flag.

Skills Demonstrated

Phishing investigation

URL analysis

Static malware analysis

PHP source-code inspection

IOC identification

Credential-harvesting detection

CyberChef usage

Basic threat investigation

Lessons Learned

This exercise reinforced the importance of examining suspicious files rather than relying solely on the appearance of a phishing webpage. Analysing the underlying PHP code provided evidence of credential collection, information gathering and data exfiltration.
It also demonstrated how CyberChef can be used to decode suspicious strings during an investigation.

Conclusion

Successfully completed the TryHackMe phishing investigation challenge, gaining practical experience in phishing analysis, static code inspection, IOC identification and encoded-data analysis.
All analysis was performed within an authorised cybersecurity training environment.
