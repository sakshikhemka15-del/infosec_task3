# Security Concepts

## 1. Security Through Obscurity

**The Core Idea:**

Security Through Obscurity is the idea that a system is safe simply because its inner details are hidden from users or attackers.
Instead of using strong security mechanisms, the assumption is that if attackers do not know where something is or how it works, they will not be able to exploit it.

**The Reality and why it fails:**

This approach can act as a small additional layer, but it is not a reliable security strategy on its own. 
A secure system should remain secure even if an attacker understands how it is designed.  (known as Kerckhoffs’s Principle).

Hiding information doesn't actually stop a skilled attacker; it only delays them.
Once the hidden detail is discovered, the protection completely breaks as there are no real locks behind it.

**Examples:**

* *Bad Practice:* Hiding a sensitive file or login page at an unusual location and assuming no one will find it.
* *Better Practice:* Using proper authentication, strong passwords, file permissions, and encryption. Even if the attacker knows the location, access is still blocked.
---
 ## 2. Attack Surface
 
**The Core Idea:**

The Attack Surface is the sum total of all the different points where an attacker can try to enter data into, or extract data from, a system.
The larger the attack surface, the more opportunities an attacker has to exploit weaknesses.

**What Contributes to an Attack Surface:**

* Technical: Open network ports, running services (like a web server), misconfigured file permissions and outdated software.
* Human: User accounts, email addresses (for phishing), and weak passwords.
* Physical: Exposed USB ports or unlocked server rooms.

**Reducing attack surface:**

Good security is about "shrinking" this area as much as possible:
* Disabling unused services
* Closing unnecessary ports
* Limiting user permissions
* Removing default credentials

**Example:**

A company server hosts a public website and an email service, but it is also running an old, unused file-sharing service (FTP).
Although the FTP service is no longer needed, it still remains active and accessible.
By disabling this unnecessary service, the company reduces its attack surface, eliminating a potential entry point that attackers could otherwise exploit.

