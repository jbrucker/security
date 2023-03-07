---
title: Personal CyberSecurity
---

## At Home

Read the NSA's [Best Practices for Securing Your Home Network](https://grc.sc/912).

### Questions

1. IoT devices can be compromised (hacked) and used at attack or spy on other devices on someone's home network.  How should you configure your home network to reduce this threat?  Include a diagram in your answer.

2. Randomware encrypts data on your computer, and will encrypt backups, too.  What should you do to prevent randomware from encrypting backups? (You *do* have a backup of your computer's disk, right?)

3. What kind of IoT device is attacked the most?    
   You might need to search for this, but a hint is that this device is directly exposed to the Internet.

4. A lot of IoT and mobile malware are in-memory only. They ndon't copy themselves to persistent storage.  What can you do to periodically clean out such malware?


### Homework

1. Review every "Security" setting on all your social media accounts.  Write down any changes you make to increase security.

2 Review every "Security" setting in each web browser you use.  Write down any changes you make to increase security.

## Case Study: LastPass

LastPass is a password manager.  It stores all your passwords in an encrypted file called a "vault".
The password vault is saved on your computer and also uploaded to LastPass (so you can access your passwords on many devices).

The vault is encrypted with a long random key, and this
key is encrypted with a master password that the user
must enter.  It's critically important that the key be
securely encrypted and that the encryption is time consuming
to prevent off-line brute force attacks.

<https://blog.lastpass.com/2023/03/security-incident-update-recommended-actions/>

<https://support.lastpass.com/help/incident-2-additional-details-of-the-attack>

These articles explain that the hacker penetrated a LastPass DevOps engineer's home laptop, implanted a keylogger, 
and then stole the DevOps engineer's LastPass password
and data vault containing secrets used to access the
backups on Amazon AWS cloud storage.

Question:
- which of the NSA Home Security recommendations could have prevented this (if the engineer had used the recommendation)?

## Exercise: How Many Times has Your Email been Stolen?

1. Go to <https://haveibeenpwned.com>.  Enter your email address.  What recent data breaches has it been seen in, and what other info was stolen?

   - don't worry if your email address was stolen.  It is more concerning if your password or credit card info was also stolen.

2. On the same web site, enter some of your passwords (they are **not** sent over the Internet).  Have any of them appeared in a data breach?

   - again, don't worry *too much*. The password could be from someone else's account.

3. My email was stolen in hacks of Gravitar and GeekedIn.  What could I do to prtect my email when using low-security sites like this?
