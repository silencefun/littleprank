# 💻 Fake BSOD（假蓝屏死机）

模拟 Windows 蓝屏死机。选一个错误类型，点 **Start**，看它“崩溃”并显示进度。纯 HTML/CSS/JS，零依赖——二维码是纯 CSS，无需图片。

▶ **在线演示（littleprank.com）：** https://littleprank.com/en/tools/system/fake-bsod/

![假蓝屏界面](demo.png)

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

本仓库展示一个效果，但 littleprank.com 上完整的**系统类**工具如下，每条附一句话说明，点击即可直达在线工具：

- [假 Windows 更新](https://littleprank.com/en/tools/system/fake-windows-update/) — 模拟 Windows 系统更新界面，整蛊你的朋友
- [假蓝屏死机](https://littleprank.com/en/tools/system/fake-bsod/) — 模拟 Windows 蓝屏错误界面
- [假黑客终端](https://littleprank.com/en/tools/system/fake-hacker-terminal/) — 模拟黑客攻击终端界面
- [假病毒扫描](https://littleprank.com/en/tools/system/fake-virus-scan/) — 模拟杀毒软件扫描界面
- [假加载界面](https://littleprank.com/en/tools/system/fake-loading/) — 模拟各种加载进度条
- [假 macOS 更新](https://littleprank.com/en/tools/system/fake-macos-update/) — 模拟 macOS 系统更新安装界面
- [假 Chrome 更新](https://littleprank.com/en/tools/system/fake-chrome-update/) — 模拟 Chrome 浏览器更新页面
- [假关机画面](https://littleprank.com/en/tools/system/fake-shutdown/) — 模拟系统关机动画
- [假系统错误](https://littleprank.com/en/tools/system/fake-system-error/) — 模拟系统错误弹窗
- [假系统格式化](https://littleprank.com/en/tools/system/fake-format/) — 模拟磁盘格式化界面
- [假 BIOS 界面](https://littleprank.com/en/tools/system/fake-bios/) — 模拟电脑开机 BIOS POST 自检界面
- [假 Windows 激活失效](https://littleprank.com/en/tools/system/fake-windows-activate/) — 模拟 Windows 未激活水印和激活失败弹窗
- [假权限不足弹窗](https://littleprank.com/en/tools/system/fake-permission-denied/) — 批量弹出管理员权限不足提示框
- [假系统冻结](https://littleprank.com/en/tools/system/fake-system-freeze/) — 模拟电脑完全卡死无响应
- [假注册表修复](https://littleprank.com/en/tools/system/fake-registry-repair/) — 模拟开机注册表自动修复进度
- [假 MBR 引导损坏](https://littleprank.com/en/tools/system/fake-mbr-error/) — 模拟磁盘引导失败黑屏界面
- [假内核恐慌](https://littleprank.com/en/tools/system/fake-kernel-panic/) — 模拟 macOS Kernel Panic 黑屏
- [假 CMD 报错刷屏](https://littleprank.com/en/tools/system/fake-cmd-error/) — 模拟命令行无限刷红色报错代码
- [假 Git Clone](https://littleprank.com/en/tools/system/fake-git-clone/) — 模拟终端疯狂克隆仓库永远不结束
- [假编译中](https://littleprank.com/en/tools/system/fake-compiling/) — 模拟代码编译进度永远卡在 99%
- [假 sudo 密码校验](https://littleprank.com/en/tools/system/fake-sudo-password/) — 模拟 Linux 终端密码永远错误
- [假浏览器崩溃](https://littleprank.com/en/tools/system/fake-browser-crash/) — 模拟 Chrome Aw Snap 崩溃页面
- [假浏览器内存爆满](https://littleprank.com/en/tools/system/fake-browser-memory/) — 模拟浏览器内存占用过高崩溃
- [假创意 404 页面](https://littleprank.com/en/tools/system/fake-404-page/) — 多款风格化 404 丢失页面
- [假 PowerShell 高危执行](https://littleprank.com/en/tools/system/fake-powershell/) — 模拟执行格式化硬盘等高危命令，滚动大量日志
- [假远程入侵监控](https://littleprank.com/en/tools/system/fake-remote-intrusion/) — 显示正在抓取屏幕读取摄像头的日志流
- [假 WiFi 破解终端](https://littleprank.com/en/tools/system/fake-wifi-crack/) — 模拟破解附近 WiFi 密码，逐条列出虚拟密码列表
- [假系统日志上传](https://littleprank.com/en/tools/system/fake-log-upload/) — 崩溃后收集错误日志回传服务器，多行滚动日志
- [无限弹窗炸弹](https://littleprank.com/en/tools/system/fake-popup-bomb/) — 点击后无休止弹出错误警告弹窗，位置随机散落
- [窗口拖拽锁定](https://littleprank.com/en/tools/system/fake-window-drag/) — 弹窗拖拽时自动吸附鼠标甩不掉，关闭按钮失效
- [熊猫烧香病毒](https://littleprank.com/en/tools/system/fake-xiongmao-shaoxiang/) — 一比一还原2006年Windows熊猫烧香病毒感染效果：熊猫举香图标替换、海量系统错误弹窗、CMD黑窗命令风暴
- [假驱动自动安装](https://littleprank.com/en/tools/system/fake-driver-install/) — 批量安装声卡显卡网卡驱动，逐个进度条加载
- [假数据备份还原](https://littleprank.com/en/tools/system/fake-data-backup/) — 模拟系统数据备份还原进度，文件打包动态图标
- [假磁盘占用爆满](https://littleprank.com/en/tools/system/fake-disk-full/) — C 盘空间已满弹窗反复弹出，窗口无法关闭
- [假任务管理器卡死](https://littleprank.com/en/tools/system/fake-task-manager/) — 进程疯狂乱跳，CPU 内存拉满，点击结束无响应
- [假资源管理器崩溃](https://littleprank.com/en/tools/system/fake-explorer-crash/) — 文件夹窗口不停自动新建，窗口乱飞图标错乱
- [假显卡崩溃花屏](https://littleprank.com/en/tools/system/fake-gpu-crash/) — 全屏彩色花屏，色块撕裂，画面扭曲抖动
- [假 CPU 过热警报](https://littleprank.com/en/tools/system/fake-cpu-temp/) — 悬浮温度仪表盘飙升，弹窗警报，屏幕红光闪烁
- [假硬盘坏道检测](https://littleprank.com/en/tools/system/fake-disk-badblocks/) — 扫描网格色块，红色标记大量虚拟坏道
- [假服务器宕机面板](https://littleprank.com/en/tools/system/fake-server-down/) — 仿运维后台服务器掉线，端口被占用，服务崩溃
- [假开发者工具入侵](https://littleprank.com/en/tools/system/fake-devtools-intrusion/) — F12 控制台铺满红色报错，恶意代码日志
- [假 Steam 文件验证](https://littleprank.com/en/tools/system/fake-steam-verify/) — 复刻 Steam 游戏完整性校验进度条
- [假游戏崩溃窗口](https://littleprank.com/en/tools/system/fake-game-crash/) — 还原 UE4 Unity 引擎游戏崩溃报错弹窗
- [假 Excel 卡死](https://littleprank.com/en/tools/system/fake-excel-freeze/) — Excel 窗口提示程序无响应，计算进度卡在 0%
- [假 Word 文档恢复](https://littleprank.com/en/tools/system/fake-word-recovery/) — 软件崩溃重启后文档自动恢复加载界面
- [假断网页面](https://littleprank.com/en/tools/system/fake-offline-page/) — 复刻 Chrome 离线恐龙页面，DNS 解析失败报错
- [假 VPN 连接界面](https://littleprank.com/en/tools/system/fake-vpn-connect/) — 模拟 VPN 拨号连接流程，频繁断开重连失败
- [假网站维护](https://littleprank.com/en/tools/system/fake-maintenance/) — 全屏维护遮罩，网站正在升级中
- [假 Cloudflare 验证](https://littleprank.com/en/tools/system/fake-cloudflare-challenge/) — CF 人机验证卡住不动，永远验证不完
- [假 502 错误](https://littleprank.com/en/tools/system/fake-502-error/) — 模拟 500/502 网关错误页面
- [假网站关停](https://littleprank.com/en/tools/system/fake-site-shutdown/) — "网站已永久关闭"公告，怀旧告别页
- [假验证码](https://littleprank.com/en/tools/system/fake-captcha/) — 模拟越来越魔幻的"我不是机器人"验证，讽刺现代互联网
- [假Win95登录](https://littleprank.com/en/tools/system/fake-win95-login/) — 经典Windows 95登录界面，复古灰色风格
- [假Win98登录](https://littleprank.com/en/tools/system/fake-win98-login/) — Windows 98登录界面，经典蓝天白云
- [假WinXP登录](https://littleprank.com/en/tools/system/fake-winxp-login/) — Windows XP欢迎界面，经典绿色任务栏
- [假Win7登录](https://littleprank.com/en/tools/system/fake-win7-login/) — Windows 7登录界面，Aero玻璃效果
- [假Win8/8.1登录](https://littleprank.com/en/tools/system/fake-win8-login/) — Windows 8/8.1磁贴登录界面，现代扁平风格
- [假Win10登录](https://littleprank.com/en/tools/system/fake-win10-login/) — Windows 10登录界面，简洁现代设计
- [假Win11登录](https://littleprank.com/en/tools/system/fake-win11-login/) — Windows 11居中登录界面，圆角设计
- [假系统更新卡死](https://littleprank.com/en/tools/system/fake-update-stuck/) — 系统更新卡在100%不动，或"还剩1分钟"持续半小时
- [假 macOS 登录](https://littleprank.com/en/tools/system/fake-macos-login/) — 模拟 macOS 锁屏登录界面，输入密码解锁动画
- [假 Linux 登录](https://littleprank.com/en/tools/system/fake-linux-login/) — 模拟 Linux 终端登录界面，输入用户名与密码
- [假 Windows 锁屏](https://littleprank.com/en/tools/system/fake-windows-lock/) — 模拟 Windows 锁屏界面，输入密码解锁
- [假系统还原](https://littleprank.com/en/tools/system/fake-ghost-recovery/) — 模拟系统还原/恢复模式进度界面
- [假安全模式启动](https://littleprank.com/en/tools/system/fake-safe-mode-boot/) — 模拟系统安全模式启动诊断界面
- [假 rm -rf 报错](https://littleprank.com/en/tools/system/fake-rm-rf-error/) — 模拟终端疯狂刷 rm -rf 报错代码
