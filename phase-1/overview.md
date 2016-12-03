## Phase 1 Contents

* [Simply Secure Messenger Service](ssms.md)
* [End-User Application Release Authentication](euara.md)

Phase 1 focuses primarily on Application security. This is because the encryption methods we have today are really strong when implemented correctly and they are not likely cracked by even large government agencies. A more realistic attack avenue is on the software, infrastructure and the software maintainers. This XKCD comic is most relevant to this.

![XKCD](https://imgs.xkcd.com/comics/security.png)

Assuming we have an encrypted Messenger app that runs on mobile devices(Apple/Android) and as a Web Application, then aside from cracking the encryption, there are only a few ways to get the unencrypted data. This document groups these attacks into three categorizes: Software Attacks, Infrastructure Attacks and Social Engineering.

 * Attacks on Software
   * Embedding hidden backdoors that leak encrypted data.
 * Attacks on Infrastructure
    * Hacking servers to release modified software versions.
    * DNS Hijacking to direct users to another site that leaks their encryption keys.
    * Hacking or coercing Google Play or Itunes to release modified software versions.
 * Social Engineering
   * Forcing/Tricking Users to give up their encryption keys.
   * Forcing Maintainers to implement backdoors into the software.

While these are not *all* the possible attack vectors, these are the ones that will prove fatal to the privacy of the application users. This document focuses on preventing the possibility of these category of attacks.