# 📱 Fake iOS Update

A realistic iOS system-update screen with an animated progress ring. Pure HTML/CSS/JS, zero dependencies.

▶ **Live demo on littleprank.com:** https://littleprank.com/en/tools/mobile/fake-ios-update/

![fake iOS update screen](demo.gif)

## What it does

- Shows a black iOS-style update screen with an Apple logo and a circular progress ring.
- Click **Start** to animate the percentage 0 → 100%.
- **Restart** resets and replays.
- **Fullscreen** fills the screen for a convincing fake.

## Run it

No build, no install. Just open `index.html` in any browser.

## The core code

The progress ring is a stroked `<circle>` whose `stroke-dashoffset` is driven by the percentage:

```js
var CIRC = 213.6; // 2 * π * r  (r = 34)
function update() {
  percent = Math.min(100, percent + Math.random() * 2.5);
  arc.style.strokeDashoffset = CIRC * (1 - percent / 100);
  elPercent.textContent = Math.floor(percent) + '%';
}
```

The full, runnable version (with Start/Restart/Fullscreen) is in **[`index.html`](index.html)**.

## License

MIT.

---

A tiny showcase of **[littleprank.com](https://littleprank.com)** — more playful (and harmless) effects live there.

## One-click tools from littleprank.com

This repo highlights one effect — but the full littleprank.com **mobile** collection is listed below, with a short description of each. Every link opens the live tool directly:

- [Fake iOS Update](https://littleprank.com/en/tools/mobile/fake-ios-update/) — Simulate iPhone/iPad system update screen
- [Fake Android Update](https://littleprank.com/en/tools/mobile/fake-android-update/) — Simulate Android system update installation screen
- [Fake White Apple](https://littleprank.com/en/tools/mobile/fake-white-apple/) — Simulate iPhone stuck on Apple logo restore
- [Fake Battery Damage](https://littleprank.com/en/tools/mobile/fake-battery-damage/) — Simulate phone battery swelling warnings
- [Fake Fastboot Flash](https://littleprank.com/en/tools/mobile/fake-fastboot/) — Simulate Android fastboot partition flashing
- [Fake System UI Crash](https://littleprank.com/en/tools/mobile/fake-system-ui-crash/) — Simulate Android System UI keeps crashing
- [Fake Phone Overheat](https://littleprank.com/en/tools/mobile/fake-phone-overheat/) — Simulate phone temperature surge and shutdown
- [Fake SMS Bomb](https://littleprank.com/en/tools/mobile/fake-sms-bomb/) — Phone notification bar endless SMS messages popup
- [Fake App Badges](https://littleprank.com/en/tools/mobile/fake-app-badges/) — App icons auto-generating massive unread badge counts
- [Fake Video Call](https://littleprank.com/en/tools/mobile/fake-video-call/) — Simulate FaceTime video call incoming screen with ringtone
- [Fake Fingerprint Unlock](https://littleprank.com/en/tools/mobile/fake-fingerprint/) — Phone unlock interface, recognition failure triggers lockout
- [iPhone Locked](https://littleprank.com/en/tools/mobile/fake-iphone-lock/) — Simulate iPhone disabled interface, customizable lockout time
- [Fake Call](https://littleprank.com/en/tools/mobile/fake-call/) — Simulate phone incoming call screen
- [Fake Notification](https://littleprank.com/en/tools/mobile/fake-notification/) — Generate phone notification popup screenshots
- [Fake Low Battery](https://littleprank.com/en/tools/mobile/fake-battery/) — Simulate phone low battery warning dialog
- [Fake Battery Dead](https://littleprank.com/en/tools/mobile/fake-battery-dead/) — Simulate phone battery drain and auto shutdown, black screen with charging animation
- [Fake iOS Recovery](https://littleprank.com/en/tools/mobile/fake-ios-restore/) — Simulate iPhone recovery mode / restore progress screen
- [Fake Android Flash](https://littleprank.com/en/tools/mobile/fake-android-flash/) — Simulate Android fastboot / recovery flashing progress
