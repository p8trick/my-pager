# 📢 Order Terminal Pro (V3.7.8)

[中文说明](#chinese) | [English Description](#english)

---

<a name="chinese"></a>
## 🇨🇳 中文说明 (Chinese)

### 简介
一款专为高频率零售环境设计的高性能网页叫号终端。通过精简的纯前端逻辑，旨在取代昂贵的工业级硬件，提供更灵活、更具容错性的操作体验。

### 核心特性
*   **双重持久化运行 (Dual Anti-Sleep)**：集成 Web Wake Lock API 与底层隐藏媒体流保活机制，防止移动端设备在长时间无人操作时自动锁屏[span_0](start_span)[span_0](end_span)。
*   **全物理键盘映射 (Hardware Mapping)**：深度适配物理键盘，支持数字键输入、回车键播报（带防连发逻辑）、加减号步进及退格键清除。
*   **紧急熔断制动 (Emergency Break)**：允许操作者通过物理按键或 UI 交互瞬间切断 `window.speechSynthesis` 播报队列，解决误触发痛点。
*   **视觉反馈系统 (Visual Feedback)**：包含模拟呼吸灯动效与实时播报状态高亮反馈，确保设备运行状态一目了然。
*   **本地化运行 (Local & Private)**：100% 纯前端运行，不依赖外部服务器，支持离线使用并利用 `localStorage` 保护配置数据。

### 版本更新记录
*   **V3.7.8 (当前版本)**：
    *   新增 `CLR` / `Backspace` 语音熔断功能。
    *   引入显示区域 `breathe` 呼吸灯动画。
    *   修复并回归了 3.7.1 中的物理键盘监听与防连发逻辑。
*   **V3.7.7**：
    *   引入 1px 隐藏视频保活方案，解决 iOS Safari 自动休眠问题[span_1](start_span)[span_1](end_span)。
    *   优化语音引擎预热，降低 Ding 声后的播报延迟。
*   **V3.7.1**：
    *   建立核心播报架构，支持自定义语速、次数及声线选择。
    *   实现历史记录回滚：重播历史号码后自动恢复当前输入序列。
    *   集成本地存储功能，实现用户设置持久化。

### 快捷键映射
| 按键 | 功能说明 |
| :--- | :--- |
| **0 - 9** | 输入订单号码 |
| **Enter** | 执行播报并自动步进 (+1) |
| **+ / -** | 手动向上/向下步进号码 |
| **Backspace** | 紧急打断当前播报并清除输入 |

### 🛠️ 开发者说明
本项目坚持“低成本、高效率、重逻辑”的开发原则。每一行代码都经过优化，旨在真实生产环境中提供极致的稳定性。
> “追求事物的本质，平衡理性逻辑与完美情节。”

---

<a name="english"></a>
## 🇺🇸 English Description

### Overview
A high-performance web-based order calling terminal designed for high-frequency retail environments. It replaces expensive industrial hardware with streamlined front-end logic, offering a more flexible and fault-tolerant user experience.

### Key Features
*   **Dual Anti-Sleep Persistence**: Integrates Web Wake Lock API and low-level hidden media stream mechanisms to prevent mobile devices from auto-locking during inactivity[span_2](start_span)[span_2](end_span).
*   **Hardware Keyboard Mapping**: Full physical keyboard support, including numeric input, Enter key announcement (with anti-repeat logic), Plus/Minus stepping, and Backspace clearing.
*   **Emergency Break Logic**: Allows operators to instantly interrupt the `window.speechSynthesis` queue via physical keys or UI interaction, addressing the pain point of accidental triggers.
*   **Visual Feedback System**: Features breathing light animations and real-time announcement highlighting to ensure the operational status is clear at a glance.
*   **Local & Private Execution**: 100% front-end execution with no server dependency; supports offline use and protects configuration data via `localStorage`.

### Change Log
*   **V3.7.8 (Current Version)**:
    *   Added voice "Emergency Break" function via `CLR` / `Backspace`.
    *   Implemented `breathe` animation for the display area.
    *   Restored and optimized the physical keyboard listener and anti-repeat logic from V3.7.1.
*   **V3.7.7**:
    *   Introduced 1px hidden video keep-alive solution to fix iOS Safari auto-sleep issues[span_3](start_span)[span_3](end_span).
    *   Optimized speech engine warm-up to reduce latency after the notification tone.
*   **V3.7.1**:
    *   Established core broadcasting architecture with customizable speed, repeats, and voice selection.
    *   Implemented Historical Log Rollback: Automatically restores the current input sequence after replaying history.
    *   Integrated local storage functionality for user preference persistence.

### Keyboard Shortcuts
| Key | Action |
| :--- | :--- |
| **0 - 9** | Enter Order Number |
| **Enter** | Announce Number & Auto-increment (+1) |
| **+ / -** | Manual Step Up / Down |
| **Backspace** | Emergency Interrupt & Clear Input |

### 🛠️ Developer Notes
This project adheres to the principles of "Low Cost, High Efficiency, and Robust Logic." Every line of code is optimized for stability in real-world production environments.
> "Pursue the essence of things, balancing rational logic with a touch of perfectionism."
