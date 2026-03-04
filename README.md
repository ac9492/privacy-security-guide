# Privacy & Security Guide for Beginners

A practical, beginner-friendly guide to improving privacy and security on the internet by switching tools and adopting better habits — **for free**, without excessive technical complexity.

[![GitHub Stars](https://img.shields.io/github/stars/fynks/email-aliasing-comparison?style=for-the-badge&logo=github&label=Star%20on%20GitHub)](https://github.com/ac9492/Complete-Privacy-and-Security-Guide)
[![Last Commit](https://img.shields.io/github/last-commit/fynks/email-aliasing-comparison?style=for-the-badge&logo=github&label=Last%20Update)](https://github.com/ac9492/Complete-Privacy-and-Security-Guide/commits/main/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

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

I personally only recommend these 4 if you want to use a free password manager. Only look at other alternatives if you are willing to pay, because their free tier limitations are significant. Furthermore, I would not use 2FAS Pass or KeyPassXC unless you are comfortable setting up your own backup and syncing methods and distrust a cloud based password manager. 

| Password Manager | Unlimited Passwords | Open-source | Cross platform | Cloud-based |
|:----------:|:----------:|:----------:|:----------:|:----------:|
| [Bitwarden](https://bitwarden.com/) | Yes | Yes | Yes | Yes |
| [Proton Pass](https://proton.me/pass) | Yes | Yes | Yes | Yes |
| [2FAS Pass](https://2fas.com/pass/) | Yes | Yes | Partial | No |
| [KeyPassXC](https://keepassxc.org) | Yes | Yes | Partial | No |

### Other Popular Paid Options

Note, the comparison only takes into account the free tiers of each password manager. If a password manager puts any sort of limit on multi-device access, the cross-platform table will be marked as "No".

| Password Manager | Unlimited Passwords | Open-source | Cross platform | Cloud-based |
|:----------:|:----------:|:----------:|:----------:|:----------:|
| [NordPass](https://nordpass.com/) | Yes | No | No | Yes |
| [Keeper](https://www.keepersecurity.com/personal.html) | No | No | No | Yes |
| [RoboForm](https://www.roboform.com/) | Yes | No | No | No |
| [1Password](https://1password.com/) | No free tier | No | No free tier | No free tier |
| [LastPass](https://www.lastpass.com/) | Yes | No | No | Yes |
| [Dashlane](https://www.dashlane.com/) | No free tier | No | No free tier | No free tier |

If you're currently using a paid password manager, and want to migrate to a free one, it is quite doable, you just need to export your passwords as a file, and reimport them into your new password manager. All password managers allow import/export of your vault.

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
- [2FAS](https://2fas.com/) (iOS and Android + browser extension)
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
- [Proton Drive](https://proton.me/drive) - Offers 5GB of free storage, part of Proton ecosystem (open source clients). It is also a great replacement for the Google docs ecosytem (although it is not as fully featured). It offers collaborative [Docs](https://proton.me/drive/docs) and [Sheets](https://proton.me/drive/sheets) with E2EE by default, fully online and synced across devices. No targeted ads, no AI training with your documents, etc.

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

- [Vivaldi](https://vivaldi.com/) - Another Chromium-based privacy browser packed with features for power users. However, it is not fully open-source.
- [DuckDuckGo Browser](https://duckduckgo.com/) - Privacy-centric browser with privacy search by default, tracker blocking, and fully-incognito mode with ability to delete browsing data at any point (does not allow extensions)
- [Mullvad Browser](https://mullvad.net/en/browser) - Privacy-hardened browser, which blocks trackers, cookies, and fingerprinting (Firefox/Gecko based) by default. It does not allow syncing or extensions.
- [LibreWolf](https://librewolf.net/) - A hardened version of Firefox by default. If you want to skip the setup for hardening Firefox, you can download LibreWolf and use it as-is. Supports, syncing, profiles, and extensions.
- [Tor Browser](https://www.torproject.org/download/) - a unique browser that lets you connect through the [Tor network](https://en.wikipedia.org/wiki/Tor_(network)) to any website.
- [Zen Browser](https://zen-browser.app/) - A Firefox-based privacy focused browser that has additional customization and productivity tools.
- [Ungoogled Chromium](https://ungoogled-software.github.io/ungoogled-chromium-binaries/) - Basically the Chromium browser, with all the Google services and telemetry removed. This is the closest you can get to Google Chrome without any Google dependencies.

In some cases, these might be better for privacy, although for most users Brave and Firefox (hardened) should be enough.

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
- [Startpage](https://www.startpage.com/en/) - Anonimizes Google search results. It is not as rich as Google due to the lack of contextual and personal data.
- [Ecosia](https://www.ecosia.org/) - Plants trees with revenue from ads shown in searches. Bing-based and anonimized searches.
- [Qwant](https://www.qwant.com/) - Independent and privacy search engine with some reliance on Bing results.
- [SearXNG](https://searx.space/) - Open-source self-hosted search engine. You need to choose an instance in the link to use.

---

# Email

Benefits:
- No email scanning, AI training, etc
- No ads
- Built-in encryption (with support for E2EE)
- Strong account security defaults

**Note:** Using encrypted mail with external email clients (such as [Thunderbird](https://www.thunderbird.net/en-US/)) is usually very difficult, or in some cases impossible. Proton requires a paid plan and additional setup, and Tuta does not support external clients at all. You can however use them across devices with their website and apps.

---

Popular privacy-focused free email providers
- [Proton Mail](https://proton.me/mail) - Free 1GB of storage for emails, calendar, and integrates with Proton ecosystem (Docs, SimpleLogin, etc). E2EE encrypted at rest and across PGP providers. Also supports password-protected emails.
- [Tuta Mail](https://tuta.com/) - Free 1GB of storage for emails, calendar, and uses 100% renewable energy across. Supports E2EE between Tuta accounts. Emails are also E2EE encrypted at rest. Supports password-protected emails.

---

Additional privacy-focused email providers:
- Posteo
- Fastmail
- Mailfence
- StartMail
- Mailbox.org
- 
---


You can forward email from existing providers, and slowly migrate your email accounts.

## Email Aliasing
Email aliasing (or masking/relaying) is the practice of hiding your email when signing up to different websites. The way it works is that a provider lets you create (or generate) a specific email address that is anonymous and forwards mail to your main inbox.

For example, if your main email is:
`john.doe@gmail.com`

You might create an alias for Netflix:
`7ash7sdvnbe.netflix@mozmail.com` which automatically forwards to --> `john.doe@gmail.com` without ever exposing your real email to Netflix.

This has multiple benefits: 
- The first one is security. By having a unique alias for each service that you sign up, an attacker trying to gain access would need to both have your specific alias that you use for that service + your password (almost like having two passwords).
- Secondly, even if you trust where you're signing up, this protects your email from being exposed in data breaches of your provider. This provides strong anonimity in cases of your information being leaked to the dark web.
- Thirdly, if you start receiving spam email from one of your aliases that you never signed up for, you know exactly which service leaked or sold your email.
- Finally, you can disable any alias whenever you want (e.g. a service you signed up for starts spamming you without consent).
- Some of them also remove trackers from email depending on your tier (Trackers let the sender know when and if you opened an email, what your IP is, and other system information).

The best free email aliasing services are:
- [DuckDuckGo Email Protection](https://duckduckgo.com/email/) - This one is truly the only free and unlimited email aliasing tool out there. DuckDuckGo is well known in the privacy world, so it is trustworthy. They let you create a custom @duck.com address that forwards to your real address, plus unlimited randomly-generated aliases for your different accounts. You need their browser and/or extension to generate aliases (although it is also possible to do it inside Bitwarden). Removes trackers by default.
- [Addy.io](https://addy.io/) - Another free service that lets you create unlimited aliases. However, it caps your usage at 10MB of monthly bandwidth (which should be enough for most users). Also has a pretty generous $1/mo tier.

Additional email aliasing services:
Note that these also have free tiers, but they limit the amount of aliases you can create, making them better as paid subscriptions:
- [Firefox Relay](https://relay.firefox.com/) - Allows the creation of 5 email aliases for free, plus unlimited aliases for $0.99/mo, and phone protection for $3.99/mo
- [Simple Login](https://simplelogin.io/) - Allows the creation of 10 email aliases for free, plus unlimited access for $4/mo (also included in the Proton Unlimited subscription, and integrates really well with Proton Pass)
- [Apple Hide My Email](https://support.apple.com/en-us/105078) - Recommended if you only use Apple devices. Requires a $0.99/mo iCloud subscription. It also has a free tier when using the "Sign up with Apple" option.
- [AdGuard Mail](https://adguard-mail.com/en/welcome.html) - Free limited tier with $2.99/mo pricing for premium

You can get more information on different providers [here](https://github.com/fynks/email-aliasing-comparison). 


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
