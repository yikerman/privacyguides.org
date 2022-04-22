---
title: Android Overview
icon: material/cellphone-check
---
Android is a secure operating system that has strong [app sandboxing](https://source.android.com/security/app-sandbox), [Verified Boot](https://source.android.com/security/verifiedboot), and a robust [permission](https://developer.android.com/guide/topics/permissions/overview) control system.

The main privacy concern with most Android devices is that they usually include [Google Play Services](https://developers.google.com/android/guides/overview). This component is proprietary (closed source), has a privileged role on your phone, and may collect private user information. It is neither a part of the [AOSP](https://source.android.com/) nor is it included with the below derivatives.

## Avoid Root

[Rooting](https://en.wikipedia.org/wiki/Rooting_(Android)) Android phones can decrease security significantly as it weakens the complete [Android security model](https://en.wikipedia.org/wiki/Android_(operating_system)#Security_and_privacy). This can decrease privacy should there be an exploit that is assisted by the decreased security. Common rooting methods involve directly tampering with the boot partition, making it impossible to perform successful Verified Boot. Apps that require root will also modify the system partition meaning that Verified Boot would have to remain disabled. Having root exposed directly in the user interface also increases the [attack surface](https://en.wikipedia.org/wiki/Attack_surface) of your device and may assist in [privilege escalation](https://en.wikipedia.org/wiki/Privilege_escalation) vulnerabilities and [SELinux](https://en.wikipedia.org/wiki/Security-Enhanced_Linux) policy bypasses.

Adblockers which modify the [hosts file](https://en.wikipedia.org/wiki/Hosts_(file)) (AdAway) and firewalls (AFWall+) which require root access persistently are dangerous and should not be used. They are also not the correct way to solve their intended purposes. For Adblocking we suggest encrypted [DNS](../dns.md) or [VPN](../vpn.md) server blocking solutions instead. RethinkDNS, TrackerControl and AdAway in non-root mode will take up the VPN slot (by using a local loopback VPN) preventing you from using privacy enhancing services such as Orbot or a real VPN server.

AFWall+ works based on the [packet filtering](https://en.wikipedia.org/wiki/Firewall_(computing)#Packet_filter) approach and may be bypassable in some situations.

We do not believe that the security sacrifices made by rooting a phone are worth the questionable privacy benefits of those apps.

## Firmware Updates

Firmware updates are critical for maintaining security and without them your device cannot be secure. OEMs have support agreements with their partners to provide the closed source components for a limited support period. These are detailed in the monthly [Android Security Bulletins](https://source.android.com/security/bulletin).

As the components of the phone such as the processor and radio technologies rely on closed source components, the updates must be provided by the respective manufacturers. Therefore it is important that you purchase a device within an active support cycle. [Qualcomm](https://www.qualcomm.com/news/releases/2020/12/16/qualcomm-and-google-announce-collaboration-extend-android-os-support-and) and [Samsung](https://news.samsung.com/us/samsung-galaxy-security-extending-updates-knox/) support their devices for 4 years while cheaper products often have shorter support. With the introduction of the [Pixel 6](https://support.google.com/pixelphone/answer/4457705), Google now makes their own system on chip (SoC) and they will provide 5 years of support.

Devices that have reached their end-of-life (EoL) and are no longer supported by the SoC manufacturer, cannot receive firmware updates from OEM vendors or after market Android distributors. This means that security issues with those devices will remain unfixed.

## Android Versions

It's important to not use an [end-of-life](https://endoflife.date/android) version of Android. Newer versions of Android not only receive security updates for the operating system but also important privacy enhancing updates too. For example, [prior to Android 10](https://developer.android.com/about/versions/10/privacy/changes), any user apps with the [`READ_PHONE_STATE`](https://developer.android.com/reference/android/Manifest.permission#READ_PHONE_STATE) permission could access sensitive and unique serial numbers of your phone such as [IMEI](https://en.wikipedia.org/wiki/International_Mobile_Equipment_Identity), [MEID](https://en.wikipedia.org/wiki/Mobile_equipment_identifier), your SIM card's [IMSI](https://en.wikipedia.org/wiki/International_mobile_subscriber_identity), whereas now they must be system apps to do so. System apps are only provided by the OEM or Android distribution.

## Android Permissions

[Permissions on Android](https://developer.android.com/guide/topics/permissions/overview) grant users control over what apps are allowed to access. Google regularly makes [improvements](https://developer.android.com/about/versions/11/privacy/permissions) on the permission system in each successive version. All user installed apps are strictly [sandboxed](https://source.android.com/security/app-sandbox), therefore there is no need to install any antivirus apps. The savings you make from not purchasing or subscribing to security apps is better spent on paying for a supported device in the future.

Should you want to run an app that you're unsure about, consider using a user or work [profile](android/#android-security-privacy).