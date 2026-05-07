# 📢 Order Terminal Pro (V3.8)

[中文说明](#chinese) | [English Description](#english)

---

<a name="chinese"></a>
## 🇨🇳 中文说明 (Chinese)

### 简介
一款专为高频率零售环境设计的高性能网页叫号终端。通过精简的纯前端逻辑，旨在取代昂贵的工业级硬件，提供更灵活、更具容错性的操作体验。

### 核心特性
* **双重持久化运行 (Dual Anti-Sleep)**：集成 Web Wake Lock API 与底层隐藏媒体流保活机制，防止设备在长时间无人操作时自动锁屏。
* **全物理键盘映射 (Hardware Mapping)**：深度适配物理键盘，支持数字键输入、回车键播报（带防连发逻辑）、加减号步进及退格键清除。
* **紧急熔断制动 (Emergency Break)**：允许操作者通过物理按键或 UI 交互瞬间切断播报队列，解决误触发痛点。
* **多维视觉系统 (Visual Feedback)**：包含模拟呼吸灯动效与**实时订单耗时色彩预警逻辑**。
* **本地化运行 (Local & Private)**：100% 纯前端运行，不依赖外部服务器，支持离线使用并保护配置数据。

### 版本更新记录
* **V3.8 (当前稳定版)**：
    * **新增分段式色彩预警**：根据呼叫耗时自动切换字体颜色（5min-黄 / 10min-红 / 30min-灰）。
    * **UI 像素级优化**：显示容器高度锁定为 110px，通过负边距补偿技术在扩大主号字号（110px）的同时，找回了键盘操作空间。
    * **性能固化**：继承并锁定了 V3.7.8 的所有核心熔断与防休眠逻辑。

### 快捷键映射
| 按键 | 功能说明 |
| :--- | :--- |
| **0 - 9** | 输入订单号码 |
| **Enter** | 执行播报并自动步进 (+1) |
| **+ / -** | 手动向上/向下步进号码 |
| **Backspace** | 紧急打断当前播报并清除输入 |

---

<a name="english"></a>
## 🇺🇸 English Description

### Overview
A high-performance web-based order calling terminal designed for high-frequency retail environments.

### Key Features
* **Dual Anti-Sleep Persistence**: Web Wake Lock API & hidden media stream to prevent auto-locking.
* **Hardware Keyboard Mapping**: Numeric input, Enter (with anti-repeat), Plus/Minus stepping, and Backspace clearing.
* **Emergency Break Logic**: Instantly interrupt the announcement queue via physical keys or UI.
* **Multi-dimensional Visual System**: Breathing light animations and **real-time order aging color alerts**.
* **Local & Private Execution**: 100% front-end; offline support; data protected via localStorage.

### Change Log
* **V3.8 (Current Stable)**:
    * **New Segmented Color Alerts**: Font colors change based on elapsed time (5m-Yellow / 10m-Red / 30m-Grey).
    * **UI Optimization**: Adjusted display container to 110px. Used negative margin to reclaim keypad space while increasing main number size.
    * **Logic Solidification**: Inherited all core "Emergency Break" and "Anti-Sleep" logic from V3.7.8.

### Keyboard Shortcuts
| Key | Action |
| :--- | :--- |
| **0 - 9** | Enter Order Number |
| **Enter** | Announce Number & Auto-increment (+1) |
| **+ / -** | Manual Step Up / Down |
| **Backspace** | Emergency Interrupt & Clear Input |

---

### 🛠️ Developer Notes
本项目坚持“低成本、高效率、重逻辑”的开发原则。V3.8 通过对 CSS 盒模型的精确控制，实现了“视觉信息增强”与“物理操作面积”的完美平衡。
> “追求事物的本质，平衡理性逻辑与完美情节。”
