# 网页版叫号器 (Web Pager)

[English](#english) | [中文](#中文)

---

## 中文
### 简介
这是一个轻量级的 HTML 叫号器，专门优化了在 iOS 设备（iPhone/iPad）上的全屏显示效果，适合餐厅或排队场景使用。

### 如何在 iOS 上安装为桌面 App
1. 使用 **Safari** 浏览器打开本项目生成的 GitHub Pages 网址。
2. 点击屏幕底部的**“分享”**图标（带上箭头的方块）。
3. 在菜单中向下滚动，选择**“添加到主屏幕”**。
4. 在桌面点击图标即可全屏运行，无浏览器工具栏。

### 核心逻辑说明
* **音频触发**：由于 iOS 安全机制，必须在页面加载后手动点击一次“启动”或“交互”按钮，后续的语音播报才能自动播放。
* **更新维护**：在 GitHub 仓库修改代码后，手机端 App 会在下次打开时自动同步更新。

---

<a name="english"></a>
## English
### Description
A lightweight HTML-based paging system optimized for full-screen display on iOS devices (iPhone/iPad). Ideal for restaurant queuing or service counters.

### Installation (iOS Home Screen App)
1. Open the GitHub Pages URL in **Safari**.
2. Tap the **Share** button (the square icon with an upward arrow).
3. Scroll down and select **"Add to Home Screen"**.
4. Launch the app from your home screen for a standalone, full-screen experience.

### Key Logic
* **Audio Policy**: Due to iOS restrictions, a manual user interaction (e.g., clicking a "Start" button) is required to enable automatic voice/sound announcements.
* **Auto-Update**: Any changes pushed to this GitHub repository will reflect on the web app automatically upon the next launch.
