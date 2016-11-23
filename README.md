# SSMS-Spec
## Overview
This document describes phase I of the Simply Secure Messaging System, or SSMS. The main purpose of SSMS is to provide simple encrypted messaging that is just as easy to use as Facebook Messenger, while at the same time, providing complete security of the data and application.

Data security goals are:
 * Long term encryption protection against large agencies and governments.
 * End-to-End Encryption
 * Forward Security

Application security goals are:
 * Protection against DNS Hijacking
 * Protection against malicious version releases
 * Protection against Man-in-the-Middle Attacks.

Phase I focuses primarily on Application security. This is because the encryption methods we have today are really strong when implemented correctly and they are not likely cracked by even large government agencies. A more realistic attack avenue is on the software and the software maintainers. This XKCD comic is most relevant to this.

![XKCD](https://imgs.xkcd.com/comics/security.png)

Assuming we have an encrypted Messenger app that runs on mobile devices(Apple/Android) and as a Web Application, then aside from cracking the encryption, there are only a few ways to get the unencrypted data. This document groups these attacks into three categorizes: Software Attacks, Infrastructure Attacks and Social Engineering.

 * Attacks on Software
   * Embedding hidden backdoors that leak encrypted data.
 * Attacks on Infrastructure
    * Hacking servers to release modified software versions.
    * DNS Hijacking to direct users to another site that leaks their encryption keys.
    * Hacking or coercing Google Play or Itunes to release modified software versions.
 * Social Engineering
   * Forcing Users to give up their encryption keys.
   * Forcing Maintainers to implement backdoors into the software.

While these are not *all* the attack vectors, these are the ones that will cause a mass leak of for all users of the application. This document focuses on preventing the possibility of these category of attacks. To handle these attacks the scope of trust needs to first brought down to the user and the software maintainers.

As it stands, we are forced to trust 3rd parties when delivering software. For example, we must trust that we will always have complete control over a domain; that the DNS provider doesn't hand over the domain name to somebody or that they get hacked. We trust Google and Itunes that our software isn't getting tampered with while it's in their online stores. We have to trust that our servers are not going to be compromised by the hosting provider. We must trust SSL Certificate Authorities with our communication streams.
