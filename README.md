# 📢 Order Terminal Pro (V3.7.8)

[中文](#chinese) | [English](#english)

---

<a name="chinese"></a>
## 🇨🇳 中文说明 (Chinese)

### 简介
这是一个基于 Web 技术构建的高性能叫号系统终端。专为高频、高负载的零售环境设计，旨在通过纯前端逻辑取代昂贵的工业级叫号硬件。

### 核心特性
*   **持久化运行 (Anti-Sleep)**：结合 Web Wake Lock API 与底层媒体流保活机制，防止移动端设备自动锁屏。
*   **全键盘映射 (Full Mapping)**：深度适配物理键盘，包含回车键播报（带防连发逻辑）、加减号步进及退格键清除。
*   **紧急熔断机制 (Emergency Break)**：允许操作者通过物理按键或 UI 交互瞬间切断当前语音流，确保极高的响应速度。
*   **状态反馈系统 (UI Feedback)**：包含呼吸灯动效与实时播报状态高亮，提供清晰的视觉确认。

### 版本更新记录
*   **V3.7.8 (当前版本)**：新增 `CLR` 熔断制动功能；引入 `breathe` 呼吸灯动画；修复了键盘映射回归错误。
*   **V3.7.7**：引入 1px 隐藏视频保活方案，解决 iOS Safari 自动休眠问题。
*   **V3.7.1**：建立基础播报架构，实现历史记录回滚逻辑与数据持久化存储。

---

<a name="english"></a>
## 🇺🇸 English Description

### Overview
A high-performance order calling terminal built with modern Web technologies. Designed for high-frequency, high-load retail environments, it aims to replace expensive industrial hardware with pure front-end logic.

### Key Features
*   **Always-On Display (Anti-Sleep)**: Integrates Web Wake Lock API and low-level media stream keep-alive mechanisms to prevent mobile devices from auto-locking.
*   **Hardware Keyboard Mapping**: Full support for physical keyboards, including Enter (Announce with anti-repeat logic), Plus/Minus (Step), and Backspace (Clear).
*   **Emergency Break Logic**: Allows operators to instantly cut off the current speech synthesis flow via physical keys or UI interaction for rapid response.
*   **Visual Feedback System**: Features breathing light animations and real-time announcement highlighting for clear operational status.

### Change Log
*   **V3.7.8 (Current)**: Added `CLR` emergency break function; implemented `breathe` animation; fixed keyboard mapping regressions.
*   **V3.7.7**: Introduced 1px hidden video keep-alive solution to fix iOS Safari auto-sleep issues.
*   **V3.7.1**: Established core broadcasting architecture, historical log rollback, and local storage persistence.

### Keyboard Shortcuts
| Key | Action |
| :--- | :--- |
| `0 - 9` | Enter Order Number |
| `Enter` | Announce & Auto-increment (+1) |
| `+` | Manual Step Up |
| `-` | Manual Step Down |
| `Backspace` | Emergency Stop & Clear Input |

---

## 🛠️ Developer Notes
This project adheres to the principles of "Low Cost, High Efficiency, and Robust Logic." Every line of code is optimized for stability in real-world production environments.
