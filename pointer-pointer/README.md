# 🖱️ Pointer Pointer

Move your mouse and **pause** — emojis fly in from the screen edges and **point at your cursor**. A tiny, delightful prank effect. Zero dependencies, pure HTML/CSS/JS.

▶ **Live demo:** https://&lt;your-username&gt;.github.io/pointer-pointer/  *(enable GitHub Pages on this repo, then this URL works)*

> 💡 Want a GIF in this README? Record a ~5s screen capture of the effect and drop it as `demo.gif` — it'll show right here.

## What it does

- Detects when the mouse stays still for ~300 ms.
- Spawns a random emoji at a random screen edge.
- The emoji flies in and rotates to **point at** the cursor position.
- Lives ~2 s, then fades out. Max 5 at a time.
- Supports touch + fullscreen.

## Run it

No build, no install. Just open `index.html` in any browser.

## The core code

The whole effect is one self-contained file (`index.html`). Here is the heart of it — the spawn + point-at-cursor logic:

```js
var EMOJIS = ['👆','👇','👈','👉','🐱','🐶','🦊','🐼','🐸','🦉','🐵','🐰','👀','🤔','😎','🥳','👋','🫵','🤙','🙌','✌️','🤞'];
var MAX = 5, PAUSE = 300, LIFE = 2000, active = [];

function pointAngle(ex, ey, mx, my) {
  return Math.atan2(my - ey, mx - ex) * 180 / Math.PI;
}

function spawn(mx, my) {
  if (active.length >= MAX || fsCooldown) return;
  var rect = stage.getBoundingClientRect();
  var sw = rect.width, sh = rect.height;
  if (sw < 2 || sh < 2) return;
  var size = 40 + Math.random() * 40;
  var tx = mx + (Math.random() - 0.5) * 100;
  var ty = my + (Math.random() - 0.5) * 100;
  var edge = (Math.random() * 4) | 0, sx, sy;
  if (edge === 0) { sx = Math.random() * sw; sy = -size; }
  else if (edge === 1) { sx = sw + size; sy = Math.random() * sh; }
  else if (edge === 2) { sx = Math.random() * sw; sy = sh + size; }
  else { sx = -size; sy = Math.random() * sh; }
  var el = document.createElement('span');
  el.textContent = EMOJIS[(Math.random() * EMOJIS.length) | 0];
  el.style.fontSize = size + 'px';
  el.style.transform = 'translate(' + sx + 'px,' + sy + 'px) rotate(' + (Math.random()*360-180) + 'deg) scale(0.2)';
  stage.appendChild(el);
  requestAnimationFrame(function () { requestAnimationFrame(function () {
    el.style.transition = 'transform .55s cubic-bezier(.2,.9,.3,1.3), opacity .3s';
    el.style.opacity = '1';
    el.style.transform = 'translate(' + tx + 'px,' + ty + 'px) rotate(' + pointAngle(tx, ty, mx, my) + 'deg) scale(1)';
  }); });
  var rec = { el: el };
  active.push(rec);
  rec.timer = setTimeout(function () { fadeOut(rec); }, LIFE);
}
```

The full, runnable version (with fade-out, clear, fullscreen, touch) is in **[`index.html`](index.html)**.

## License

MIT — do whatever you want with it.

## One-click tools from littleprank.com

This repo highlights one effect — but the full littleprank.com collection in this category is listed below. Every link opens the live tool directly:

- [Fake Cert Warning](https://littleprank.com/en/tools/prank/fake-cert-warning/)
- [Fake Bitlocker](https://littleprank.com/en/tools/prank/fake-bitlocker/)
- [Fake Clipboard Hijack](https://littleprank.com/en/tools/prank/fake-clipboard-hijack/)
- [Fake Password Input](https://littleprank.com/en/tools/prank/fake-password-input/)
- [Fake Fbi Warning](https://littleprank.com/en/tools/prank/fake-fbi-warning/)
- [Fake Japanese Fbi Warning](https://littleprank.com/en/tools/prank/fake-japanese-fbi-warning/)
- [Fake Ransomware](https://littleprank.com/en/tools/prank/fake-ransomware/)
- [Fake Camera Recording](https://littleprank.com/en/tools/prank/fake-camera-recording/)
- [Fake Achievement](https://littleprank.com/en/tools/prank/fake-achievement/)
- [Fake Gacha](https://littleprank.com/en/tools/prank/fake-gacha/)
- [Fake Attendance Fail](https://littleprank.com/en/tools/prank/fake-attendance-fail/)
- [Fake Git Merge Conflict](https://littleprank.com/en/tools/prank/fake-git-merge-conflict/)
- [Fake Meeting Fullscreen](https://littleprank.com/en/tools/prank/fake-meeting-fullscreen/)
- [Fake Stock Surge](https://littleprank.com/en/tools/prank/fake-stock-surge/)
- [Fake Sneaker Drop](https://littleprank.com/en/tools/prank/fake-sneaker-drop/)
- [Fake Nft Mint](https://littleprank.com/en/tools/prank/fake-nft-mint/)
- [Fake Wallet Connect](https://littleprank.com/en/tools/prank/fake-wallet-connect/)
- [Fake Airdrop](https://littleprank.com/en/tools/prank/fake-airdrop/)
- [Fake Ddos Warning](https://littleprank.com/en/tools/prank/fake-ddos-warning/)
- [Boss Key](https://littleprank.com/en/tools/prank/boss-key/)
- [Fake Progress Gen](https://littleprank.com/en/tools/prank/fake-progress-gen/)
- [Fake Notification Bomb](https://littleprank.com/en/tools/prank/fake-notification-bomb/)
- [Surveillance Prank](https://littleprank.com/en/tools/prank/surveillance-prank/)
- [Fake Mouse Action](https://littleprank.com/en/tools/prank/fake-mouse-action/)
- [Fake Saas Dashboard](https://littleprank.com/en/tools/prank/fake-saas-dashboard/)
- [Fake Ai Chat](https://littleprank.com/en/tools/prank/fake-ai-chat/)
- [Fake Vscode](https://littleprank.com/en/tools/prank/fake-vscode/)
- [Fake Wechat Redpack](https://littleprank.com/en/tools/prank/fake-wechat-redpack/)
- [Random Picker](https://littleprank.com/en/tools/prank/random-picker/)
- [Soundboard](https://littleprank.com/en/tools/prank/soundboard/)
- [Jump Scare Prank](https://littleprank.com/en/tools/prank/jump-scare-prank/)
- [Useless Buttons](https://littleprank.com/en/tools/prank/useless-buttons/)
- [Pointer Pointer](https://littleprank.com/en/tools/prank/pointer-pointer/)
- [Fake Weather Forecast](https://littleprank.com/en/tools/prank/fake-weather-forecast/)
- [Fake Earthquake Alert](https://littleprank.com/en/tools/prank/fake-earthquake-alert/)
- [Wooden Fish](https://littleprank.com/en/tools/prank/wooden-fish/)
- [Incense Burner](https://littleprank.com/en/tools/prank/incense-burner/)
- [Prayer Beads](https://littleprank.com/en/tools/prank/prayer-beads/)
- [Time Waster](https://littleprank.com/en/tools/prank/time-waster/)

---


---

Built as a small showcase of **[littleprank.com](https://littleprank.com)** — more playful (and harmless) effects live there.
