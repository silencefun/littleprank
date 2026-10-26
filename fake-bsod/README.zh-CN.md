# 💻 Fake BSOD（假蓝屏死机）

模拟 Windows 蓝屏死机。选一个错误类型，点 **Start**，看它“崩溃”并显示进度。纯 HTML/CSS/JS，零依赖——二维码是纯 CSS，无需图片。

▶ **在线演示：** https://&lt;你的用户名&gt;.github.io/fake-bsod/  *(在本仓库开启 GitHub Pages 后可用)*

> 💡 想加动图？录一段约 5 秒录屏存为 `demo.gif` 即可。

## 效果说明

- 选择停止码（CRITICAL_PROCESS_DIED 等），会随机显示一个失败模块。
- **Start** 让百分比从 0 走到 100，然后“重启”并循环。
- **Reset** 回到空闲提示态。
- **Fullscreen** 全屏。

## 运行方式

无需构建、无需安装，直接用浏览器打开 `index.html`。

## 核心代码

“崩溃”循环只是推进一个计数器并更新文案：

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
    } else { clearInterval(bsodInterval); setTimeout(startBsod, 1800); } // “重启”循环
  }, 180);
}
```

完整可运行版本（含错误类型选择、Reset、Fullscreen）见 **[`index.html`](index.html)**。

## 许可证

MIT。

## 更多 littleprank.com 一键直达

本仓库只展示其中一个效果——以下是 littleprank.com 同分类下的全部工具，每个链接都直达在线版：

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


---

本仓库是 **[littleprank.com](https://littleprank.com)** 的一个小展示 —— 更多好玩（且无恶意）的效果都在那里。
