# 📱 Fake iOS Update（假 iOS 更新）

一个拟真的 iOS 系统更新界面，带动态进度环。纯 HTML/CSS/JS，零依赖。

▶ **在线演示（littleprank.com）：** https://littleprank.com/en/tools/mobile/fake-ios-update/

![假 iOS 更新界面](demo.gif)

## 效果说明

- 黑色 iOS 风格更新界面，含苹果 logo 与圆形进度环。
- 点击 **Start** 让百分比从 0 动画到 100%。
- **Restart** 重置并重播。
- **Fullscreen** 全屏，更有欺骗感。

## 运行方式

无需构建、无需安装，直接用浏览器打开 `index.html`。

## 核心代码

进度环是一个描边 `<circle>`，通过 `stroke-dashoffset` 跟随百分比推进：

```js
var CIRC = 213.6; // 2 * π * r  (r = 34)
function update() {
  percent = Math.min(100, percent + Math.random() * 2.5);
  arc.style.strokeDashoffset = CIRC * (1 - percent / 100);
  elPercent.textContent = Math.floor(percent) + '%';
}
```

完整可运行版本（含 Start/Restart/Fullscreen）见 **[`index.html`](index.html)**。

## 许可证

MIT。

## 更多 littleprank.com 一键直达

本仓库只展示其中一个效果——以下是 littleprank.com 同分类下的全部工具，每个链接都直达在线版：

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


---

本仓库是 **[littleprank.com](https://littleprank.com)** 的一个小展示 —— 更多好玩（且无恶意）的效果都在那里。
