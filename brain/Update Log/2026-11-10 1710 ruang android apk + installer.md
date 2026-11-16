---
date: 2026-11-10
project: ruang
tags: [update-log, ruang, tauri, android, nsis]
publish: true
---

# ruang v1.2.0: signed Android APK + Windows installer

Asked: "fix the limits, and continue next".

## Shipped
- Release v1.2.0: https://github.com/juw12/ruang/releases/tag/v1.2.0
  - `Ruang-1.2.0-android.apk` (18,000,607 bytes): Tauri 2 mobile, arm64 + armv7 + x86_64, minSdk 24 (Android 7.0), versionCode 1002000, signed with a stable release key (APK v2 + v3 signatures).
  - `Ruang-1.2.0-windows-x64-setup.exe` (1,654,700 bytes): NSIS installer, per-user, Start-menu entry + uninstaller.
  - `Ruang-1.2.0-windows-x64.exe` (4,016,128 bytes): portable exe.
  - `SHA256SUMS.txt` covering all three.
- Code: app logic moved to `desktop/src/lib.rs` (`mobile_entry_point`), desktop-only window options behind `#[cfg(desktop)]`, WebView2 args behind `#[cfg(windows)]`; `desktop/package.json` with the local Tauri CLI (Gradle calls `npm run tauri`).
- APK signing certificate SHA-256: `38:7F:69:3C:F8:17:AE:58:E7:F3:F0:CC:35:D3:1F:6B:CA:0F:C9:EB:8A:63:D1:75:6C:77:52:CB:A5:7C:18:E9`. Key kept in repo secrets plus an offline backup outside the repo.
- CI (`.github/workflows/desktop.yml`): windows, android, android-smoke and release jobs; a release is only published when every check passes.

## Verified
- Local web gates: ALL PASS in 302.9 s (G1 54/54, i18n, G2a-G2g, G6 390 px).
- Windows CI: WebView2 window smoke test; silent install found ruang.exe, uninstall.exe and a Start-menu shortcut, and silent uninstall removed the exe.
- Android CI on an Android 14 emulator: installs, app process running, no FATAL EXCEPTION, screenshot shows the app UI (region dialog, view tabs, step bar). One WebGL GL_INVALID_OPERATION log line from the emulator's software GPU.
- `apksigner verify`: the signing certificate digest matches the local key.
- All 4 release files download from GitHub.

## Not done / limits
- Windows files are still not code-signed (SmartScreen warning). Needs a certificate: SignPath Foundation (free for OSS, needs an application), Azure Trusted Signing or an OV certificate.
- No native iPhone app: needs an Apple Developer account (US$99/yr) and a Mac build. The Safari "Add to Home Screen" PWA remains.
- The APK is not on Google Play (needs a Play Console account, one-time US$25 fee). The CI could build an AAB for it.
- The APK has not been tested on a physical phone, and camera/photo picking has not been tested inside the Android WebView.
