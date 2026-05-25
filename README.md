# 📟 Queue Caller Terminal (智能叫号分析终端) `v4.9.10`

[![Platform](https://img.shields.io/badge/Platform-iPadOS%20%7C%20iOS%20%7C%20Web-orange.svg)](#)
[![Architecture](https://img.shields.io/badge/Architecture-Pure%20Frontend%20%7C%20Single%20File-green.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](#)

[Simplified Chinese](#简体中文说明文档) | [English](#english-documentation)

---

## 简体中文说明文档

### 🌟 项目愿景与设计哲学
这是一个专为高负载餐饮、零售环境打造的**商用级、纯前端、单文件、零后台依赖**的排队叫号与后厨效率分析终端。

传统商业 POS 叫号系统极度依赖复杂的云端服务器、本地局域网网关及数据库，极易因断网或硬件冲突崩溃。本项目秉承**极客式的“微创重构”与“绝对单机化”**哲学，在不引入任何外部后端语言（如 Node.js, Python）和第三方重型框架（如 React, Vue）的前提下，通过纯原生 JavaScript/CSS 变量，将一整套涵盖键盘盲操、大字看板、语音多音色合成、跨天断电数据补零以及 28 天后厨大数据流的完备商用级系统，完美熔铸于**单个 HTML 文件**中。

---

### 🛠️ 全特性硬核技术拆解

#### 1. ⚡ 零依赖本地工业级持久化 (Zero-Server Durability)
* **内存-闪存双轨同步 Pipeline**：系统核心状态（`callLog`, `orderHistory`, `history7Days`）全部依托经过深度优化的 `localStorage` 读写管道。
* **物理防挂死机制**：针对店面突发断电、iPad 浏览器意外刷新、App 被系统后台杀后台等极端场景，系统可实现 **0 毫秒延迟的数据瞬时继承恢复**，确保柜台营业数据绝不丢失。

#### 2. ⏳ 智能跨天结算与物理时间补零算法 (Cross-Day Auto-Padding)
* **动态多日时间跨度桥接**：店休、假节日或设备长期关机后，系统在首次冷启动时，会通过内部的 `toUTC` 与时间戳差值算法（`gapDays` 计算），自动分析最后活跃日与当前自然日之间的断层。
* **全自动虚拟补零渲染**：自动在后台数据库中按时间顺序追加漏掉的日期并强制平摊补零（`avg: 0`），完美修复了传统统计图表因“数据断流”导致的排版塌陷与环比扭曲。

#### 3. 📊 自适应多端天数分流视窗 (Device-Specific Display Windows)
* **28天（四周）大仓库**：底层存储上限硬核扩容至 28 天（四周循环截断），提供月度级的经营状态追踪。
* **iPhone 移动端（7天精致流）**：当检测到窄屏环境（`window.innerWidth < 768`），代码自动执行 `slice(-7)`，在狭窄的手机屏幕上呈现最紧凑、无溢出的高密度图表。
* **iPad 终端（14天长轴看板）**：在横屏大宽屏环境下，自动执行 `slice(-14)` 并触发弹性盒（Flexbox）的 `space-between` 均匀平摊，用修长、骨感的霓虹能量柱彻底干掉大屏右侧的视觉空白。

#### 4. 📐 非线性视觉级差（平方放大算法）
* **长尾拖拽防护**：放弃了传统易被极端卡单数据（如忘点结算导致某一单高达50分钟）彻底拍扁的线性动态图表，坚持 `CHART_CEIL = 15` 的实战化硬上限截断。
* **高分段敏感度放大**：在 15 分钟阈值内，引入非线性平方公式 `Math.pow(limitedAvg, 2) / Math.pow(15, 2)`。让 3-5 分钟的优秀出餐数据优雅收敛于底部保持整洁，而让 9.6 分钟与 15 分钟的拉胯数据在视觉像素（px）跨度上**暴风式拔高 2.5 倍**，使后厨瓶颈一眼便知。

#### 5. 🖥️ 看板与输入“前后端分离式”大重构 (Kiosk Signage Architecture)
* **一键无损 Kiosk 变形**：在 `SETTINGS` 开启“AUTO/键盘看板模式”后，系统自动解构并彻底隐藏数字键盘，腾出 100% 视窗作为纯挂墙展示屏。
* **盲操点击穿透技术**：大字号码溢出区和主按钮内置 `.pointer-events: none;`，即使顾客或前台误触屏幕，点击也能完美穿透至下层的磁贴与 `DAILY LOG` 日志，极具实战鲁棒性。

#### 6. 🎨 解耦型 CSS 变量主题（Mutation-Free CSS Themes）
* **零 DOM 损耗架构**：通过原生 HTML5 `[data-theme]` 属性动态置换顶层 CSS Variables 标记。
* **极客配色原生集成**：包含经典琥珀橙（AMBER）、科技午夜蓝（SLATE）、深邃石墨灰（GRAPHITE）与热情绯红（CRIMSON），变色过程绝不改动或重绘任何宏观 DOM 结构，彻底杜绝 UI 变形 Bug。

---

### 🚀 部署与使用

1. **直接双击运行**：克隆或下载单文件 `order.html`，在任意 iPad、iPhone 或 PC 上使用现代浏览器（Safari、Chrome、Edge）直接双击即可运行。
2. **渐进式 Web 应用 (PWA) 挂墙配置（强烈推荐）**：
   在同级目录下配置标准的 `manifest.json` 与独立 Service Worker。在 iPad 上通过 Safari 浏览器点击“**添加到主屏幕 (Add to Home Screen)**”，即可完全隐去浏览器地址栏、状态栏及底部白条，化身为纯全屏无边框的苹果原生客户端级别 App。

---

## English Documentation

### 🌟 Project Vision & Design Philosophy
A production-grade, **pure front-end, single-file, zero-backend dependency** queuing terminal and kitchen-throughput analytics cockpit engineered for high-volume hospitality and retail environments.

While legacy commercial Q-systems suffer from network dependencies, database locks, and bulky localized gateway hardware, this project adheres to a geeky **"minimal-invasive refactoring" and "absolute standalone"** philosophy. Expressed purely via Vanilla JS and native CSS variables, it merges mechanical dial pad mapping, wall-mountable kiosk scaling, Web Speech API speech synthesis, cross-day power-loss zero-padding, and a rolling 28-day historical big-data matrix into **one single, ultra-optimized HTML file**.

---

### 🛠️ Core Technical Features & Deep Dive

#### 1. ⚡ Zero-Server Local-First Durability
* **Dual-Track Synchronous Pipeline**: Core application states (`callLog`, `orderHistory`, `history7Days`) leverage low-level `localStorage` read/write hooks.
* **Hardware Anti-Crash Immunity**: In the event of sudden restaurant power failures, manual iPad browser refreshes, or aggressive iOS background thread termination, the system achieves **0ms latency state restoration**, ensuring immediate continuity without data regression.

#### 2. ⏳ Intelligent Cross-Day Auto-Padding Algorithm
* **Multi-Day Gap Bridging**: Upon cold boot after holiday shutdowns or extended device deactivation, the system calculates the time delta (`gapDays`) between the last-recorded timestamp and the current natural clock via an internal `toUTC` pipeline.
* **Deterministic Zero-Filling**: Sequentially injects missing historical rows and forces zero-valued metrics (`avg: 0`). This stabilizes the rendering array, preventing analytical distortion and graphical collapse caused by fragmented timelines.

#### 3. 📊 Adaptive Responsive Data Streaming (Device-Specific Timeline)
* **28-Day Super-Ledger**: Storage thresholds are expanded to a 4-week rolling array, capturing monthly trends directly within the sandboxed DOM.
* **iPhone Viewport (7-Day Compact Layout)**: On portrait smartphone screens (`window.innerWidth < 768`), the system enforces an automated `slice(-7)` filter to maintain tight, crisp, zero-overflow typography.
* **iPad Terminal (14-Day Wide Canvas)**: On widescreen landscape displays, it automatically streams a `slice(-14)` array combined with CSS Flexbox `space-between` styling, perfectly populating empty negative spaces on wider monitors with elegant, neon data bars.

#### 4. 📐 Non-Linear Visualization (Quadratic Scaling Algorithm)
* **Long-Tail Outlier Protection**: Rejects traditional linear scaling that flattens ordinary columns when an outlier occurs (e.g., a ticket accidentally left open for 50 minutes), instead enforcing a rigid operational cap of `CHART_CEIL = 15`.
* **High-Range Sensitivity Scaling**: Within the 15-minute window, it injects a quadratic function: `Math.pow(limitedAvg, 2) / Math.pow(15, 2)`. Healthy throughput times (3–5 mins) remain tightly locked to the baseline, while performance lags (e.g., comparing 9.6 mins against 15 mins) are **exponentially magnified by up to 2.5x in physical pixel heights**, rendering bottlenecks instantly distinct.

#### 5. 🖥️ Kiosk Signage Architecture
* **Mutation-Free Layout Morphing**: Engaging the "AUTO/Kiosk Signage" flag instantly strips the interactive numpad layout, maximizing 100% of the screen asset for customer-facing display.
* **Pointer Event Click-Throughs**: The oversized text canvas overlays integrate native CSS `.pointer-events: none;` tags. Accidentally tapping the display area bypasses the text node, permitting absolute click-through interaction with underlying dashboard data tiles and the `DAILY LOG` buffer.

#### 6. 🎨 Mutation-Free CSS Variable Themes
* **Zero DOM Regression Architecture**: Uses HTML5 `[data-theme]` selectors to dynamically swap root token allocations.
* **Pre-bundled Technical Themes**: Includes AMBER (Signature Orange), SLATE (Cyber Midnight Blue), GRAPHITE (Monochrome Dark), and CRIMSON (Alert Red). Color state manipulation requires zero structural DOM shifts, mitigating structural rendering bugs to absolute zero.

---

### 🚀 Quick Start & Deployment

1. **Standalone Execution**: Clone or grab the solo `order.html` file and double-click it in any modern browser engine (Safari, Chromium, Edge) across iPadOS, iOS, macOS, or Windows environments.
2. **Progressive Web App (PWA) Configuration (Highly Recommended)**:
   Deploy alongside a standard `manifest.json` and a simple Service Worker. Tap "**Add to Home Screen**" via iOS/iPadOS Safari to completely strip out the browser URL address bar, bottom tab navigation, and viewport margins, transforming the script into an immersive, edge-to-edge native apple-app-like experience.
