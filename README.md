# Privacy & Security Guide for Beginners

A practical, beginner-friendly guide to improving privacy and security on the internet by switching tools and adopting better habits — **for free**, without excessive technical complexity.

---

## Disclaimer

This guide is **not intended for hardcore privacy enthusiasts**, journalists under state-level surveillance, activists in hostile regimes, or users with extreme threat models.

Instead, this guide aims to:
- Significantly improve privacy and security for **average users**
- Reduce exposure to common attacks (phishing, account takeovers, tracking)
- Use **free tools whenever possible**
- Avoid unnecessary complexity
- Work well across **Windows, macOS, Linux, iOS, and Android**

Following even most of this guide will already place you far ahead of the average internet user in terms of security and privacy.

---

## What This Guide Helps Protect Against

- Password reuse and credential stuffing attacks
- Phishing and fake login pages
- Mass data breaches
- Opportunistic identity theft
- Ad tracking and behavioral profiling
- Snooping on public or shared networks

This guide does **not** attempt to guarantee anonymity or protect against advanced forensic or government-level adversaries.
---
# Credential Management

This is the most important section in the entire guide.If you only implement one section, make it this one.
---

## Password Managers

A password manager securely stores your credentials and generates strong, unique passwords for every website.

Why password managers are essential:
- Humans cannot safely remember dozens of unique passwords
- Password reuse is the leading cause of account compromise
- Auto-fill protects against phishing by matching the correct website domain

### Recommended Free Options

- [Proton Pass](https://proton.me/pass)
- [Bitwarden](https://bitwarden.com/)

Both offer:
  - Open-source
  - Free tier includes unlimited devices
  - Available on desktop, mobile, and browsers

Additional Password Managers that are local-first (not recommended for beginners as these don't backup credentials by default):
- [2FAS Pass](https://2fas.com/pass/)
- [KeyPassXC](https://keepassxc.org)

Also open source, free, and cross-platform.

### Apple Passwords App
If you only use Apple devices, the [Passwords app](https://apps.apple.com/us/app/passwords/id6473799789) is a solid choice. Avoid it entirely if you use non-Apple devices.

### Setup Recommendations
- Use a long master password (preferably 4–5 random words)
- Enable 2FA for your password manager
- Let the manager generate passwords (16–20 characters)
- Never reuse your master password anywhere else
---

## Authenticator Apps

Authenticator apps generate TOTP codes for two-factor authentication.

Recommended free options:
- [Aegis Authenticator](https://getaegis.app/) (Android)
- [2FAS](https://2fas.com/) (iOS and Android)
- [Ente Auth](https://ente.io/auth/) (cross-platform)

Recommendations:
- Maintain your TOTP codes on a separate device (a phone) versus on all your devices
- DO NOT put TOTP codes in your password manager, even if it offers that option
- Enable encrypted backups if supported
- Avoid relying solely on one device without backups
- Never screenshot QR codes or store them unencrypted

**DO NOT USE YOUR BROWSER AS A PASSWORD MANAGER**

---

## YubiKeys and Passkeys

### Passkeys

Passkeys are passwordless login credentials built into modern operating systems and devices. They rely on biometrics or device authentication.
However, how they work depends on your operating system and setup. A Passkey could be a Yubikey, a device, or even data stored on a password manager.

#### Windows
On Windows, Passkeys are stored locally on your device (via Windows Hello on your TPM), which means if you lose your device, all your passkeys are lost with it.
It is only recommended you use passkeys on Windows if you have another backup method to access your account. 
This is particularly relevant for password managers that let you log in with passkeys, since losing, or having your device break, will lose all your access.
However, local passkeys offer a very strong level of security since they basically cannot be hacked, or lost in a data breach.

#### macOS, iPadOS, & iOS
On Apple devices, passkeys are stored in your keychain/passwords app and automatically synced across devices. 
This has the added benefit that as long as you have access to your apple account, your passkeys are backed up.
However, it introduces an additional risk of having your account hacked or breached, which would grant attackers all your passkeys.

#### Android
On Android, by default, passkeys are stored on the device's secure element (similar to Windows), but can be integrated with password managers.

#### Linux
Linux has multiple ways of storing passkeys, but no system-wide implementation like other operating systems. There are apps that let you
store passkeys similar to Windows Hello.

#### Browsers & Password Managers
These are cross platform, and work in all the above devices. Its pretty common for Browsers and Password Managers to let you store passkeys.
It's the easiest cross-platform solution, that works on all the above operating systems. However, since passkeys are much more secure when they 
are hardware based (via a device or Yubikey), storing them in your browser or password manager introduces a larger attack surface.

#### Benefits of Passkeys
They are:
- Resistant to phishing
- Easier to use than passwords
- Increasingly supported by major platforms

Whether you should use passkeys (or only a specific kind of passkey) depends on your threat model. I recommend sticking with hardware-based passkeys.

### Security Keys (YubiKeys)
Security keys CAN be used as passkeys. To register them, usually when prompted to register a device, click on "Another Device" and then on "Security Key".
They are one of the strongest forms of passkeys, and they can be used in multiple devices across all platforms.
They are a good option for securing your main accounts (such as Password Managers, Email accounts, 2FA accounts, Apple, Google, and Microsoft accounts, etc).

However, you should buy multiple (I recommend at least 3 if you are ONLY going to rely on security keys, or at least 2 if you will have an additional recovery method, such as Backup Codes or 2FA TOTP codes).

In terms of the brand, [Yubico Yubikeys](https://www.amazon.com/Security-Key-NFC-Yubico-authentication/dp/B0BVNRXFHT/ref=sr_1_4) are the best, although there are many other brands.

They are optional but offer the highest level of account protection.

---

## Recovery Codes

Recovery codes allow you to regain access to accounts if you lose your authenticator device or security key.
These are almost always offered by all online accounts when activating 2FA.

Best practices:
- Save recovery codes immediately
- Store them offline (a printed paper) or in an encrypted password manager (not your main vault! Use a separate account with a different password when using a password manager!)
- Never keep them only on the device used for authentication

Without recovery codes, account recovery may be impossible.
---

# File Storage, Backup, and Sharing

Secure storage is about both **encryption** and **availability**, and for performing backups. In this list I will only suggest E2EE options for storing your data.
This means no one, not even the cloud storage provider, can access your data, unless you explicitly share it with other users. All the options below are cross-platform.

Free services that offer E2EE storage by default (with additional paid options):
- [Mega](https://mega.nz/) - Offers 20GB of free storage (open source clients)
- [Ente Photos](https://ente.io/) - Offers 10GB of free storage for photos & videos (fully open source)
- [Ente Locker](https://ente.io/locker/) - Offers 100 items (100 files) worth of storage for free - useful for documents and such.
- [Proton Drive](https://proton.me/drive) - Offers 5GB of free storage, part of Proton ecosystem (open source clients). It is also a great replacement for the Google docs ecosytem (although it is not as fully featured). It offers collaborative [Docs](https://proton.me/drive/docs) and [Sheets](https://proton.me/drive/sheets) with E2EE by default, fully online and synced across devices.

### Simple Backup Rule

At minimum I recommend:
- One local copy
- One cloud copy

Ideally:
- One additional external or offline copy (3-2-1 rule)

## Additional Cloud Storage Options

For more tech-savvy users, or if you need more storage and want something that costs less than the paid plans above, there are two additional options:
- [Setup a NAS](https://massive.io/how-to/how-to-set-up-a-nas/), which is a local hardware device that lets you insert hard drives into it. No subscription fees, but the device can be expensive.
- Use any Cloud Storage provider together with [Cryptomator](http://cryptomator.org/). This also involves some tech setup, but Cryptomator lets you encrypt files before they are uploaded, with your own password. This lets you securely store files even on Google Drive or other big tech accounts. I personally suggest using something like [pCloud](https://www.pcloud.com/) or [Koofr](https://koofr.eu/), which have lifetime deals, so you pay once, and don't have to worry about recurring subscription fees. (pCloud goes on sale for $279 for 2TB of lifetime storage, and Koofr goes on sale for $139 for 1TB of lifetime storage).
---

# Browsers

Your browser is one of the largest privacy attack surfaces. With cookies, ads, trackers, and fingerprinting, incognito mode and VPNs hardly work on their own without a privacy-respecting browser.
I recommend immediately ditching any big-tech browsers, such as Google Chrome, Microsoft Edge, Samsung Browser, Opera, etc.

Instead, you can use one of the two big privacy browsers:
- [Brave](https://brave.com/) - Blocks ads, trackers, and fingerprinting by default, no additional configuration needed. Chromium-based, so it works with all Google Chrome extensions and feels very similar.
- [Mozilla Firefox](http://firefox.com/) - Only major web browser that uses a non-big-tech engine ([Gecko](https://en.wikipedia.org/wiki/Gecko_(software))). Requires additional configuration for better privacy. If you're interested in Firefox, I recommend downloading [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) (blocks trackers and ads). Replace your search engine with one of the ones in the following section (by default they use Google), and also replace your user.js file with [Betterfox](https://github.com/yokoffing/Betterfox/tree/main) which are just settings that improve your privacy.

Aside from those, there are multiple privacy-centric browsers that are based on Gecko or Chromium, but aren't as widely used. Among them are:
- [DuckDuckGo Browser](https://duckduckgo.com/) - Privacy-centric browser with privacy search by default, tracker blocking, and fully-incognito mode with ability to delete browsing data at any point (does not allow extensions)
- [Mullvad Browser](https://mullvad.net/en/browser) - Privacy-hardened browser, which blocks trackers, cookies, and fingerprinting (Firefox/Gecko based) by default. It does not allow syncing or extensions.
- [LibreWolf](https://librewolf.net/) - A hardened version of Firefox by default. If you want to skip the setup for hardening Firefox, you can download LibreWolf and use it as-is. Supports, syncing, profiles, and extensions.
- [Tor Browser](https://www.torproject.org/download/) - a unique browser that lets you connect through the [Tor network](https://en.wikipedia.org/wiki/Tor_(network)) to any website.
- [Zen Browser](https://zen-browser.app/) - A Firefox-based privacy focused browser that has additional customization and productivity tools.
- [Ungoogled Chromium](https://ungoogled-software.github.io/ungoogled-chromium-binaries/) - Basically the Chromium browser, with all the Google services and telemetry removed. This is the closest you can get to Google Chrome without any Google dependencies.
In some cases, these might be better for privacy, although for most users Brave and Firefox (hardened) should be enough

## Safari Disclaimer
As with the Passwords app, Safari is a solid choice for Apple users. However, if you use other devices, avoid.

## Final recommendations
- Avoid installing unnecessary or unknown extensions, as they increase attack surface.
- Be mindful of the websites you visit and files you download
- If it feels like a scam, it is a scam.

**DO NOT USE YOUR BROWSER AS A PASSWORD MANAGER**
---

# Search Engines
If you are using Google (which you most likely are), switch it immediately as it is one of the single points where Google can collect most of your personal information.
Please note that there is a tradeoff with the accuracy and depth of results when switching search engines, however the difference is not that large.
In my particular experience, Brave has the best results of privacy browsers, followed by Startpage.

Instead try these privacy-respecting alternatives to Google:
- [Brave Search](https://search.brave.com/) - Independent search engine that uses its own index. Comes bundled with Brave browser by default.
- [DuckDuckGo](https://duckduckgo.com/) - One of the first privacy focused search engines. Uses anonimized Bing results.
- [Startpage](https://www.startpage.com/en/) - Anonimizes Google search results.
- Ecosia
- Qwant
- SearXNG

Using Google occasionally is OK, but do not use it logged in.

---

# Email

Email is a high-value target for attackers.

Recommended free option:
- **:contentReference[oaicite:10]{index=10}**

Benefits:
- No ad scanning
- Built-in encryption
- Strong account security defaults

You can forward email from existing providers rather than migrating everything at once.

---

# Operating Systems

Security starts at the device level.

### Desktop
- Windows: Enable BitLocker
- macOS: Enable FileVault
- Linux: Enable full-disk encryption during installation

### Mobile
- iOS: Use Face ID or Touch ID with a strong passcode
- Android: Device encryption is usually enabled by default

A locked and encrypted device matters more than most software tools.

---

# VPNs

Use a VPN when:
- On public Wi-Fi
- Traveling
- You want to reduce ISP-level tracking

Recommended free option:
- **:contentReference[oaicite:11]{index=11}** (free tier, no logs)

Avoid unknown or ad-supported VPNs.

---

# Messaging Apps

Recommended secure messaging:
- **:contentReference[oaicite:12]{index=12}**
- WhatsApp (acceptable for most users due to E2EE)

Avoid SMS for sensitive conversations.

Be aware that some messaging apps only enable encryption in specific modes.

---

# Final Notes

Privacy and security are about **risk reduction**, not perfection.

You do not need to eliminate all tracking or metadata to gain meaningful benefits. Consistency, good defaults, and avoiding common mistakes provide most of the value.

This guide prioritizes:
- High impact
- Low complexity
- Zero or minimal cost

You can always go further later — but this is a strong foundation.
