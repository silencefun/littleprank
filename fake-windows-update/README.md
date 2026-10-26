# 🪟 Fake Windows Update

[中文版本 / Chinese version](README.zh-CN.md)

A simulated Windows 10/11 update screen. Pick a version (Win11 blue / Win10 dark), a stage, a speed, hit **Start**, and watch the percentage climb — it even "sticks" at 97% like the real thing. Pure HTML/CSS/JS, zero dependencies.

▶ **Live demo on littleprank.com:** https://littleprank.com/en/tools/system/fake-windows-update/

![Fake Windows update screen](demo.png)

## What it does

- Choose **Windows 11** (blue) or **Windows 10** (dark) style.
- **Start** runs a fake progress 0 → 97%, then occasionally jumps to 100% and "restarts".
- **Fullscreen** fills the screen for a convincing prank.
- No build, no install — just open `index.html`.

## Run it

Open `index.html` in any browser, then click **Start**.

## The core code

The progress loop just walks a counter and updates the label:

```js
let progress = 0;
const speedMap = { slow: 200, normal: 80, fast: 30 };
setInterval(() => {
  if (progress < 97) {
    progress = Math.min(97, progress + Math.random() * 3 + 0.5);
    percentEl.textContent = Math.floor(progress) + '%';
  } else if (Math.random() > 0.95) {
    percentEl.textContent = '100%';
  }
}, speedMap[speed]);
```

The full, runnable version (with version/stage picker and Fullscreen) is in **[`index.html`](index.html)**.

## License

MIT.

---

A tiny showcase of **[littleprank.com](https://littleprank.com)** — more playful (and harmless) effects live there.

## One-click tools from littleprank.com

This repo highlights one effect — but the full littleprank.com collection of **Windows update & login** screens is listed below, with a short description of each. Every link opens the live tool directly:

- [Fake Windows Update](https://littleprank.com/en/tools/system/fake-windows-update/) — Simulate Windows update screen to prank your friends
- [Fake Win11 Login](https://littleprank.com/en/tools/system/fake-win11-login/) — Windows 11 centered login screen with rounded corners
- [Fake Win10 Login](https://littleprank.com/en/tools/system/fake-win10-login/) — Windows 10 login screen with clean modern design
- [Fake Win8/8.1 Login](https://littleprank.com/en/tools/system/fake-win8-login/) — Windows 8/8.1 tile login screen with modern flat design
- [Fake Win7 Login](https://littleprank.com/en/tools/system/fake-win7-login/) — Windows 7 login screen with Aero glass effect
- [Fake WinXP Login](https://littleprank.com/en/tools/system/fake-winxp-login/) — Windows XP welcome screen with classic green taskbar
- [Fake Win98 Login](https://littleprank.com/en/tools/system/fake-win98-login/) — Windows 98 login screen with classic blue sky and white clouds
- [Fake Win95 Login](https://littleprank.com/en/tools/system/fake-win95-login/) — Classic Windows 95 login screen with retro gray style
- [Fake Windows Activation](https://littleprank.com/en/tools/system/fake-windows-activate/) — Simulate Windows not activated watermark and failure dialogs
- [Fake Windows Lock Screen](https://littleprank.com/en/tools/system/fake-windows-lock/) — Simulate Windows lock screen, enter password to unlock
- [Fake Safe Mode Boot](https://littleprank.com/en/tools/system/fake-safe-mode-boot/) — Simulate safe mode startup diagnostic screen
- [Fake Update Stuck](https://littleprank.com/en/tools/system/fake-update-stuck/) — System update stuck at 100% or "1 minute remaining" for half an hour
- [Fake macOS Update](https://littleprank.com/en/tools/system/fake-macos-update/) — Simulate macOS system update installation screen
- [Fake macOS Login](https://littleprank.com/en/tools/system/fake-macos-login/) — Simulate macOS lock screen login with password unlock animation
- [Fake Chrome Update](https://littleprank.com/en/tools/system/fake-chrome-update/) — Simulate Chrome browser update page
- [Fake Android Update](https://littleprank.com/en/tools/mobile/fake-android-update/) — Simulate Android system update installation screen
- [Fake Fastboot Flash](https://littleprank.com/en/tools/mobile/fake-fastboot/) — Simulate Android fastboot partition flashing
- [Fake White Apple](https://littleprank.com/en/tools/mobile/fake-white-apple/) — Simulate iPhone stuck on Apple logo restore

---
