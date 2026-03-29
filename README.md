# BBS Reloaded

**BetterBatteryStats — Reloaded** is a clean rewrite of [BetterBatteryStats](https://github.com/asksven/BetterBatteryStats) for Android 14+ (API 34+).

It shows you what's draining your battery between charges — kernel wakelocks, partial wakelocks, alarms, sensors, network usage, processes, and per-app power consumption — so you can identify and fix the culprits.

## Download

Download the latest APK from the [Releases](https://github.com/asksven/bbs_reloaded-releases/releases) page.

No GitHub account is required to download.

## Installation

BBS Reloaded is distributed as a signed APK. Install it via ADB:

```bash
adb install bbs-reloaded-v*.apk
```

### Grant Required Permissions

BBS Reloaded needs four system-level permissions that must be granted via ADB (they cannot be granted through the normal Android dialog). Connect your device via USB and run:

```bash
adb shell pm grant com.asksven.bbsreloaded android.permission.BATTERY_STATS
adb shell pm grant com.asksven.bbsreloaded android.permission.DUMP
adb shell pm grant com.asksven.bbsreloaded android.permission.PACKAGE_USAGE_STATS
adb shell pm grant com.asksven.bbsreloaded android.permission.INTERACT_ACROSS_USERS
```

Or as a one-liner:

```bash
for perm in BATTERY_STATS DUMP PACKAGE_USAGE_STATS INTERACT_ACROSS_USERS; do
  adb shell pm grant com.asksven.bbsreloaded android.permission.$perm
done
```

> **Note:** Permissions persist across app updates — you only need to grant them once per device. They are reset if the app is uninstalled and reinstalled.

## Automatic Updates with Obtainium

[Obtainium](https://github.com/ImranR98/Obtainium) can check for new releases and notify you when an update is available.

1. Install [Obtainium](https://github.com/ImranR98/Obtainium) on your device
2. Add this URL as an app source: `https://github.com/asksven/bbs_reloaded-releases`
3. Obtainium will automatically detect new releases and offer to install updates

## Requirements

- Android 14 or later (API 34+)
- ADB access to grant system permissions (see above)

## Upgrading from BetterBatteryStats

BBS Reloaded uses a new package name (`com.asksven.bbsreloaded`). There is no automatic upgrade path from the old BetterBatteryStats app. You must:

1. Uninstall the old BetterBatteryStats edition
2. Install BBS Reloaded
3. Grant the ADB permissions listed above

## Bug Reports & Feedback

Please use [GitHub Issues](https://github.com/asksven/bbs_reloaded-releases/issues) to report bugs or request features.

When reporting a bug, include:
- Device model and Android version
- Steps to reproduce
- Screenshots if applicable

## Support

BBS Reloaded is free and all features are available to everyone. If you find the app useful, you can support its development:

[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-GitHub%20Sponsors-ea4aaa?logo=githubsponsors)](https://github.com/sponsors/asksven)
[![Ko-fi](https://img.shields.io/badge/Support-Ko--fi-ff5e5b?logo=kofi)](https://ko-fi.com/asksven)

You can also find donation links in the app under **Settings → Support the developer**.

## License

BBS Reloaded is closed-source software. The APKs published here are free to use.
