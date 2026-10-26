# 💻 Fake BSOD

A simulated Windows Blue Screen of Death. Pick an error type, hit **Start**, and watch it "crash" with a progress counter. Pure HTML/CSS/JS, zero dependencies — the QR code is pure CSS, no images.

▶ **Live demo:** https://&lt;your-username&gt;.github.io/fake-bsod/  *(enable GitHub Pages on this repo)*

> 💡 Want a GIF here? Record a ~5s screen capture and save it as `demo.gif`.

## What it does

- Choose a stop-code (CRITICAL_PROCESS_DIED, etc.); a random failing module is shown.
- **Start** animates the percentage 0 → 100, then "restarts" and loops.
- **Reset** returns to the idle hint state.
- **Fullscreen** fills the screen.

## Run it

No build, no install. Just open `index.html` in any browser.

## The core code

The "crash" loop just walks a counter and updates the label:

```js
var failedModules = ['ntoskrnl.exe','win32k.sys','nvlddmkm.sys','ndis.sys'];
function startBsod() {
  stopCodeEl.textContent = document.getElementById('bsod-error-type').value;
  failedModuleEl.textContent = failedModules[Math.floor(Math.random()*failedModules.length)];
  bsodProgress = 0;
  bsodInterval = setInterval(function() {
    if (bsodProgress < 100) {
      bsodProgress = Math.min(100, bsodProgress + Math.random()*4 + 1);
      percentEl.textContent = Math.floor(bsodProgress) + '%';
    } else { clearInterval(bsodInterval); setTimeout(startBsod, 1800); } // "restart" loop
  }, 180);
}
```

The full, runnable version (with error-type picker, Reset, Fullscreen) is in **[`index.html`](index.html)**.

## License

MIT.

---

A tiny showcase of **[littleprank.com](https://littleprank.com)** — more playful (and harmless) effects live there.

## One-click tools from littleprank.com

This repo highlights one effect — but the full littleprank.com collection in this category is listed below. Every link opens the live tool directly:

- [Fake Windows Update](https://littleprank.com/en/tools/system/fake-windows-update/)
- [Fake Bsod](https://littleprank.com/en/tools/system/fake-bsod/)
- [Fake Hacker Terminal](https://littleprank.com/en/tools/system/fake-hacker-terminal/)
- [Fake Virus Scan](https://littleprank.com/en/tools/system/fake-virus-scan/)
- [Fake Loading](https://littleprank.com/en/tools/system/fake-loading/)
- [Fake Macos Update](https://littleprank.com/en/tools/system/fake-macos-update/)
- [Fake Chrome Update](https://littleprank.com/en/tools/system/fake-chrome-update/)
- [Fake Shutdown](https://littleprank.com/en/tools/system/fake-shutdown/)
- [Fake System Error](https://littleprank.com/en/tools/system/fake-system-error/)
- [Fake Format](https://littleprank.com/en/tools/system/fake-format/)
- [Fake Bios](https://littleprank.com/en/tools/system/fake-bios/)
- [Fake Windows Activate](https://littleprank.com/en/tools/system/fake-windows-activate/)
- [Fake Permission Denied](https://littleprank.com/en/tools/system/fake-permission-denied/)
- [Fake System Freeze](https://littleprank.com/en/tools/system/fake-system-freeze/)
- [Fake Registry Repair](https://littleprank.com/en/tools/system/fake-registry-repair/)
- [Fake Mbr Error](https://littleprank.com/en/tools/system/fake-mbr-error/)
- [Fake Kernel Panic](https://littleprank.com/en/tools/system/fake-kernel-panic/)
- [Fake Cmd Error](https://littleprank.com/en/tools/system/fake-cmd-error/)
- [Fake Git Clone](https://littleprank.com/en/tools/system/fake-git-clone/)
- [Fake Compiling](https://littleprank.com/en/tools/system/fake-compiling/)
- [Fake Sudo Password](https://littleprank.com/en/tools/system/fake-sudo-password/)
- [Fake Browser Crash](https://littleprank.com/en/tools/system/fake-browser-crash/)
- [Fake Browser Memory](https://littleprank.com/en/tools/system/fake-browser-memory/)
- [Fake 404 Page](https://littleprank.com/en/tools/system/fake-404-page/)
- [Fake Powershell](https://littleprank.com/en/tools/system/fake-powershell/)
- [Fake Remote Intrusion](https://littleprank.com/en/tools/system/fake-remote-intrusion/)
- [Fake Wifi Crack](https://littleprank.com/en/tools/system/fake-wifi-crack/)
- [Fake Log Upload](https://littleprank.com/en/tools/system/fake-log-upload/)
- [Fake Popup Bomb](https://littleprank.com/en/tools/system/fake-popup-bomb/)
- [Fake Window Drag](https://littleprank.com/en/tools/system/fake-window-drag/)
- [Fake Xiongmao Shaoxiang](https://littleprank.com/en/tools/system/fake-xiongmao-shaoxiang/)
- [Fake Driver Install](https://littleprank.com/en/tools/system/fake-driver-install/)
- [Fake Data Backup](https://littleprank.com/en/tools/system/fake-data-backup/)
- [Fake Disk Full](https://littleprank.com/en/tools/system/fake-disk-full/)
- [Fake Task Manager](https://littleprank.com/en/tools/system/fake-task-manager/)
- [Fake Explorer Crash](https://littleprank.com/en/tools/system/fake-explorer-crash/)
- [Fake Gpu Crash](https://littleprank.com/en/tools/system/fake-gpu-crash/)
- [Fake Cpu Temp](https://littleprank.com/en/tools/system/fake-cpu-temp/)
- [Fake Disk Badblocks](https://littleprank.com/en/tools/system/fake-disk-badblocks/)
- [Fake Server Down](https://littleprank.com/en/tools/system/fake-server-down/)
- [Fake Devtools Intrusion](https://littleprank.com/en/tools/system/fake-devtools-intrusion/)
- [Fake Steam Verify](https://littleprank.com/en/tools/system/fake-steam-verify/)
- [Fake Game Crash](https://littleprank.com/en/tools/system/fake-game-crash/)
- [Fake Excel Freeze](https://littleprank.com/en/tools/system/fake-excel-freeze/)
- [Fake Word Recovery](https://littleprank.com/en/tools/system/fake-word-recovery/)
- [Fake Offline Page](https://littleprank.com/en/tools/system/fake-offline-page/)
- [Fake Vpn Connect](https://littleprank.com/en/tools/system/fake-vpn-connect/)
- [Fake Maintenance](https://littleprank.com/en/tools/system/fake-maintenance/)
- [Fake Cloudflare Challenge](https://littleprank.com/en/tools/system/fake-cloudflare-challenge/)
- [Fake 502 Error](https://littleprank.com/en/tools/system/fake-502-error/)
- [Fake Site Shutdown](https://littleprank.com/en/tools/system/fake-site-shutdown/)
- [Fake Captcha](https://littleprank.com/en/tools/system/fake-captcha/)
- [Fake Win95 Login](https://littleprank.com/en/tools/system/fake-win95-login/)
- [Fake Win98 Login](https://littleprank.com/en/tools/system/fake-win98-login/)
- [Fake Winxp Login](https://littleprank.com/en/tools/system/fake-winxp-login/)
- [Fake Win7 Login](https://littleprank.com/en/tools/system/fake-win7-login/)
- [Fake Win8 Login](https://littleprank.com/en/tools/system/fake-win8-login/)
- [Fake Win10 Login](https://littleprank.com/en/tools/system/fake-win10-login/)
- [Fake Win11 Login](https://littleprank.com/en/tools/system/fake-win11-login/)
- [Fake Update Stuck](https://littleprank.com/en/tools/system/fake-update-stuck/)
- [Fake Macos Login](https://littleprank.com/en/tools/system/fake-macos-login/)
- [Fake Linux Login](https://littleprank.com/en/tools/system/fake-linux-login/)
- [Fake Windows Lock](https://littleprank.com/en/tools/system/fake-windows-lock/)
- [Fake Ghost Recovery](https://littleprank.com/en/tools/system/fake-ghost-recovery/)
- [Fake Safe Mode Boot](https://littleprank.com/en/tools/system/fake-safe-mode-boot/)
- [Fake Rm Rf Error](https://littleprank.com/en/tools/system/fake-rm-rf-error/)

---

