# 📱 Fake iOS Update

A realistic iOS system-update screen with an animated progress ring. Pure HTML/CSS/JS, zero dependencies.

▶ **Live demo:** https://&lt;your-username&gt;.github.io/fake-ios-update/  *(enable GitHub Pages on this repo)*

> 💡 Want a GIF here? Record a ~5s screen capture and save it as `demo.gif`.

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

This repo highlights one effect — but the full littleprank.com collection in this category is listed below. Every link opens the live tool directly:

- [Fake Ios Update](https://littleprank.com/en/tools/mobile/fake-ios-update/)
- [Fake Android Update](https://littleprank.com/en/tools/mobile/fake-android-update/)
- [Fake White Apple](https://littleprank.com/en/tools/mobile/fake-white-apple/)
- [Fake Battery Damage](https://littleprank.com/en/tools/mobile/fake-battery-damage/)
- [Fake Fastboot](https://littleprank.com/en/tools/mobile/fake-fastboot/)
- [Fake System Ui Crash](https://littleprank.com/en/tools/mobile/fake-system-ui-crash/)
- [Fake Phone Overheat](https://littleprank.com/en/tools/mobile/fake-phone-overheat/)
- [Fake Sms Bomb](https://littleprank.com/en/tools/mobile/fake-sms-bomb/)
- [Fake App Badges](https://littleprank.com/en/tools/mobile/fake-app-badges/)
- [Fake Video Call](https://littleprank.com/en/tools/mobile/fake-video-call/)
- [Fake Fingerprint](https://littleprank.com/en/tools/mobile/fake-fingerprint/)
- [Fake Iphone Lock](https://littleprank.com/en/tools/mobile/fake-iphone-lock/)
- [Fake Call](https://littleprank.com/en/tools/mobile/fake-call/)
- [Fake Notification](https://littleprank.com/en/tools/mobile/fake-notification/)
- [Fake Battery](https://littleprank.com/en/tools/mobile/fake-battery/)
- [Fake Battery Dead](https://littleprank.com/en/tools/mobile/fake-battery-dead/)
- [Fake Ios Restore](https://littleprank.com/en/tools/mobile/fake-ios-restore/)
- [Fake Android Flash](https://littleprank.com/en/tools/mobile/fake-android-flash/)

---

