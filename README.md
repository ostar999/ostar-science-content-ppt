<div align="center">

# ostar-science-content-ppt

> *将科普内容文本转换为可视化PPT风格网页的 AI 工作流 Skill*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-Demo-orange)](assets/templates/)

<br>

**基于 [Unclecheng-li/AI-Animation-Skill](https://github.com/Unclecheng-li/AI-Animation-Skill) 改进而来。**

<br>

在原作基础上新增**总览预览**功能（按 `N` 键一键查看所有页面缩略图）、
**全屏演示**功能（按 `F` 键进入全屏），
并优化了多模板对比生成的流程。

[快速开始](#快速开始) · [键盘快捷键](#键盘快捷键) · [新增功能](#新增功能) · [模板总览](#模板总览) · [更新日志](CHANGELOG.md)

</div>

---

## 致谢

本项目基于 **[Unclecheng-li/AI-Animation-Skill](https://github.com/Unclecheng-li/AI-Animation-Skill)** 的出色工作。

感谢原作者 **Unclecheng** 创建了完整的 AI 动画生成工作流、26 个 PPT Level2 模板、14 个 Animation 模板，以及详尽的模板选择指南。本项目继承了原作的核心理念和模板体系，并在此基础上增加了实用功能。

---

## 新增功能

### 🆕 全屏演示（Fullscreen）

| 模式 | 触发方式 | 说明 |
|------|---------|------|
| 所有模式 | 按 `F` 键 | 浏览器 Fullscreen API，隐藏所有工具栏和边框 |
| 所有模式 | 按 `ESC` 键 | 退出全屏（浏览器原生行为） |

### 🆕 总览预览（Overview Panel）

| 模式 | 触发方式 | 说明 |
|------|---------|------|
| 模式一 Step 2（原始版） | 导航栏 `⊞` 按钮 或 按 `N` 键 | 保留可见按钮 + 键盘快捷键 |
| 模式一 Step 3（模板重构版） | 按 `N` 键 | 页面保持干净无 UI 元素，纯键盘操作 |
| 模式二（单页流程图） | 按 `N` 键 | 整页缩放为鸟瞰 mini-map |

**总览面板特性：**
- 🖼️ 多页模式：全屏网格展示所有页面 25% 缩略图
- 🗺️ 单页模式：整页缩放为鸟瞰 mini-map
- 📄 每张卡片标注页码和页面标题
- 👆 点击卡片/页面直接跳转或退出
- ⌨️ 再次按 `N` 键退出总览
- 🧹 缩略图中自动冻结动画、隐藏装饰元素，保证清晰度

### 🆕 多模板对比生成

支持同时使用多个 PPT 模板生成不同风格版本，方便对比选择最佳视觉效果。

---

## 触发方式

在 Claude Code 对话中，以下任一方式可触发此 Skill：

| 触发方式 | 示例 |
|---------|------|
| 斜杠命令 | `/ostar-science-content-ppt @科普文档.md` |
| 触发词 | "生成PPT"、"生成演示网页"、"生成流程图" |
| 直接提供内容 | 在对话中贴入科普文本，Skill 自动识别并启动 |

## 它能做什么

输入一段科普文本，AI 自动完成全流程：

```
模式一（默认，3 步自动执行）：
  科普文本 → Step 1 生成提示词 → Step 2 生成原始轮播 HTML → Step 3 模板重构 → 3 个 HTML 输出

模式二（用户说「生成流程图」后触发）：
  已生成的 HTML → Animation 模板重构 → 单页流程图
```

**适用场景：** B 站视频素材、课堂教学、技术分享、小红书图文等。

### 完整工作流

| 步骤 | 做什么 | 输出文件 | 说明 |
|------|--------|----------|------|
| Step 1 | 将用户文本转为 PPT 提示词 | 无（对话中） | 自动应用模板约束 |
| Step 2 | 生成原始轮播 HTML | `AI_Animation.html` | Font Awesome 图标 · 可见导航按钮 · 永不覆盖 |
| Step 3 | 用 PPT Level2 模板重构 | `AI_Animation_level2.html` | Lucide 图标 · 纯键盘操作 · 新文件 |
| 模式二 | 用 Animation 模板重构为流程图 | `AI_Animation_flow.html` | Canvas 粒子 · 单页全景 · 新文件 |

> **🚫 核心规则：每一步生成新文件，禁止覆盖已有文件。** 3 个 HTML 各自独立，方便对比不同版本效果。

### 文件命名规则

```
项目目录/
├── AI_Animation.html          ← Step 2 原始轮播版（可见按钮 + 圆点导航）
├── AI_Animation_level2.html   ← Step 3 模板重构版（纯键盘，无可见 UI）
└── AI_Animation_flow.html     ← 模式二 单页流程图版（鸟瞰总览）
```

---

## 快速开始

### 环境要求

- **Claude Code**（CLI 或 IDE 插件版）
- 现代浏览器（Chrome / Firefox / Safari / Edge）
- 无需 Node.js、Python 等额外依赖

### 安装

**方式一：Plugin Marketplace 安装（推荐，一键安装）**

```bash
# 1. 添加本仓库为 marketplace
claude plugin marketplace add ostar999/ostar-science-content-ppt

# 2. 在 Claude Code 对话中安装
/plugin install ostar-science-content-ppt@ostar-science-content-ppt
```

**方式二：Git Clone（可自动更新）**

```bash
cd ~/.claude/skills/
git clone https://github.com/ostar999/ostar-science-content-ppt.git
```

**方式三：手动下载**

```bash
# 下载 ZIP → 解压 → 复制到 skills 目录
cp -r ~/Downloads/ostar-science-content-ppt ~/.claude/skills/
```

安装完成后，`/ostar-science-content-ppt` 命令即可用。

### 基本使用

**模式一（PPT 演示，默认）：**

```
1. 准备科普内容的 .md 文件（或直接在对话中贴入文本）
2. 输入 /ostar-science-content-ppt @你的科普.md
3. Skill 自动完成 Step 1→2→3，生成 2 个 HTML 文件
4. 在浏览器中打开 HTML，用 ← → 切换页面，F 全屏，N 总览
```

**模式二（流程图）：**

```
1. 先完成模式一
2. 说「生成流程图」
3. Skill 自动选择 Animation 模板，生成单页全景流程图
4. 用 F 全屏演示，N 打开鸟瞰 mini-map
```

**模板替换：**

```
「以 6-2.html 为模板重构」  → 指定特定 PPT Level2 模板
「用 RNN-4 模板生成流程图」 → 指定特定 Animation 模板
```

### AI 自动选模板机制

生成时，AI 会根据科普内容的类型自动选择最佳模板（无需用户指定）：

| 内容类型 | PPT Level2（Step 3） | Animation（模式二） |
|---------|---------------------|-------------------|
| 对比/辩论 | 8-1（12组VS）、8-3（30组VS） | — |
| 步骤/流程 | 3-2（SVG流程图）、6-1/6-3 | RNN-4（22种动画） |
| 概念/定义 | 1、2（13种动画）、3-1 | RNN-3（默认） |
| 案例/实验 | 4-2、4-3（代码雨动画） | — |
| 警示/危险 | 5-4（15种动画）、7-3 | RNN-6（explode动画） |
| 架构/多模块 | 6-2（红绿对比） | Comprehension（连线动画） |
| 轻量/快速 | 3-3（331行）、4-1、9-3 | GPU（570行） |

### 键盘快捷键

| 按键 | 功能 | 适用模式 |
|------|------|----------|
| `←` `→` | 切换页面（也支持滚轮、触屏滑动、点击左右半屏） | 模式一（多页轮播） |
| `F` | 全屏切换 | **所有模式** |
| `N` | 总览面板（多页=缩略图网格，单页=鸟瞰 mini-map） | **所有模式** |
| `ESC` | 退出全屏（浏览器原生） | **所有模式** |

> 💡 快捷键是隐藏功能，页面上不会显示操作提示。用户可以自行探索发现。

---

## 项目结构

```
ostar-science-content-ppt/
├── SKILL.md                              # Skill 主文件（工作流定义）
├── README.md                             # 本文件
├── LICENSE                               # MIT 开源协议
├── CHANGELOG.md                          # 更新日志
└── assets/
    └── templates/
        ├── PPT Template-level2/          # ⭐ PPT 高级模板（优先选用，26 个）
        │   ├── SUMMARY.md                #   AI 选模板参考文档
        │   ├── 1.html ~ 9-3.html         #   9 个系列 26 个模板
        ├── PPT/                          # PPT 基础模板（回退选用）
        │   ├── PPT-Generate-1.html ~ PPT-Generate-7.html
        ├── Animation/                    # 流程图模板（14 个）
        │   ├── SUMMARY.md                #   AI 选模板参考文档
        │   ├── RNN-2.html ~ RNN-7.html
        │   ├── LSTM-1.html
        │   └── ...
        ├── interaction-examples/         # 🆕 交互参考模板（3 个，仅用于参考 F/N/总览 的 JS 实现）
        │   ├── AI_Animation.html         #   模式一 Step 2 交互参考 · 导航栏+dots+N总览
        │   ├── AI_Animation_level2.html  #   模式一 Step 3 交互参考 · 纯键盘+N总览+进度条
        │   └── AI_Animation_flow.html    #   模式二 交互参考 · F全屏+N鸟瞰总览
        └── images/                       # README 示例图片
```

---

## 模板总览

> **两种模板，用途不同：**
> - **内容布局模板**（PPT Level2 / PPT / Animation）→ 决定页面视觉风格
> - **交互参考模板**（interaction-examples）→ 决定 F/N/总览/翻页的 JS 实现
>
> 两者独立选择，互不绑定。详细区分见 [SKILL.md](SKILL.md)「模板文件」章节。

### 内容布局模板：PPT Level2（26 个，优先选用）

| 系列 | 模板数 | 适用场景 | 亮点 |
|------|--------|---------|------|
| **1** | 1 | 概念引入、对比 | VS 对比卡片 + SVG 流程图 |
| **2** | 1 | 概念定义、层级结构 | 13 种动画，最多元化 |
| **3** | 3 | 轻量/步骤/极简 | 3-3 仅 331 行最轻量 |
| **4** | 3 | 案例/实验/代码 | 代码雨动画 |
| **5** | 4 | 警示/失败/危险 | 5-4 达 15 种动画 + 13 页 |
| **6** | 4 | 护栏/架构/反馈 | 6-2 红绿 VS 对比（15 种动画） |
| **7** | 4 | 追踪/上下文/Doom Loop | 7-2 达 17 种动画 |
| **8** | 3 | 辩论/对比/融合 | 8-3 达 30 组 VS 对比 |
| **9** | 3 | 总结/共识/精炼 | 9-3 仅 5 页最精炼 |

### 内容布局模板：Animation 流程图（14 个）

| 模板 | 特点 | 适用场景 |
|------|------|---------|
| **RNN-3** | 分层卡片 | 通用推荐（默认） |
| RNN-4 | 标准化流程 | 22 种动画，最密 |
| RNN-6 | 梯度爆炸警示 | explode 动画 |
| LSTM-1 | 三阶段门控 | LSTM 展示 |
| word2vec-1 | 语义身份证 | 词向量 |
| Comprehension | 理解架构 | 认知类 |
| GPU | 计算节点 | 硬件展示 |

### 交互参考模板（3 个）

不决定视觉风格，仅用于参考交互功能的 JS 实现代码：

| 模板 | 适用模式 | 参考内容 |
|------|----------|----------|
| `AI_Animation.html` | 模式一 Step 2 | 导航栏按钮 + page-dots + N 缩略图总览 + cloneNode 动画重置 |
| `AI_Animation_level2.html` | 模式一 Step 3 | 纯键盘翻页 + N 缩略图总览 + cloneNode 动画重置 + 进度条 |
| `AI_Animation_flow.html` | 模式二 | F 全屏 + N 鸟瞰 mini-map 总览 |

---

## 效果示例

### PPT 风格（Level2 模板重构后）

<img src="assets/images/ppt-demo-1.png" width="2560" height="1440" alt="PPT演示效果1" />
<img src="assets/images/ppt-demo-2.png" width="2560" height="1440" alt="PPT演示效果2" />

<img src="assets/images/ppt-demo-3.png" width="2560" height="1440" alt="PPT演示效果3" />

### 流程图风格（Animation 模板重构后）

<img src="assets/images/flow-demo-1.png" width="2560" height="1440" alt="流程图效果1" />
<img src="assets/images/flow-demo-2.png" width="2560" height="1440" alt="流程图效果2" />

---

## 交互实现细节

### 两种模板的区别

| 类型 | 用途 | 位置 |
|------|------|------|
| **内容布局模板** | 决定页面的视觉风格（配色、排版、动画、卡片样式） | `PPT Template-level2/` · `PPT/` · `Animation/` |
| **交互参考模板** | 决定交互行为的 JS 实现（F 全屏、N 总览、动画重置） | `interaction-examples/` |

> ⚠️ 内容布局模板和交互参考模板**独立选择，互不绑定**。生成时 AI 会同时参考两者：视觉效果来自内容模板，交互代码来自交互参考模板。

### 各模式交互差异

| 特性 | Step 2 原始版 | Step 3 重构版 | 模式二 流程图 |
|------|:---:|:---:|:---:|
| 可见导航按钮 | ✅ ← → ⊞ | 🚫 无 | 🚫 无 |
| 页面圆点 | ✅ | 🚫 无 | 🚫 无 |
| 页码指示器 | ✅ "3/15" | 🚫 无 | 🚫 无 |
| 键盘翻页 | ← → Home End | ← → Home End PageUp PageDown 空格 | 🚫 单页无需 |
| 总览面板 | N 键 · 缩略图网格 | N 键 · 缩略图网格 | N 键 · 鸟瞰 mini-map |
| 全屏 | F 键 | F 键 | F 键 |
| 键盘提示条 | 🚫 禁止 | 🚫 禁止 | 🚫 禁止 |

> 💡 快捷键是**隐藏功能**，页面上不会显示任何操作提示。用户自行探索发现。

### 总览面板（N 键）实现原理

- **多页模式：** 每页 cloneNode → 缩放到 25% → 冻结所有动画 → 隐藏粒子/装饰 → 网格展示
- **单页模式：** 克隆整个内容区 → 计算适配视口的缩放比例 → 鸟瞰 mini-map
- **退出：** 再次按 N 键或点击关闭按钮

---

## 已知问题与解决方案

### Q1: 切换页面后动画不重触发

**原因：** CSS `animation-fill-mode: forwards` 使动画只执行一次，`display:none` 也无法重置。

**解决：** 切换页面时 `cloneNode(true)` + `replaceChild` 强制浏览器重新渲染。这是跨浏览器最可靠的方案。

### Q2: AI 直接生成的 HTML 代码量不足

模型有时只生成 200-400 行，内容单薄。提示词中要求"代码 1000 行以上"可有效解决。

### Q3: 流程图模式不生成新内容

模式二**不生成新内容**，仅将已有的 PPT 版内容按 Animation 模板样式重新视觉呈现。需先完成模式一。

---

## 技术栈

- **前端**：HTML5 + CSS3 + JavaScript（原生，无框架依赖）
- **动画**：CSS Animation / Keyframes / 3D Transform / Canvas 粒子
- **图标**：Font Awesome / Lucide / RemixIcon（按模板选择）
- **兼容性**：现代浏览器（Chrome、Firefox、Safari、Edge）

---

## 更新日志

详见 [CHANGELOG.md](CHANGELOG.md)

---

## 开源协议

本项目基于 [Unclecheng-li/AI-Animation-Skill](https://github.com/Unclecheng-li/AI-Animation-Skill)，继承其 [MIT License](LICENSE)。

```
MIT License

Copyright (c) 2026 Unclecheng (original author)
Copyright (c) 2026 ostar999

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

---

<div align="center">

**如果对你有帮助，欢迎 Star ⭐**

**感谢 [Unclecheng](https://github.com/Unclecheng-li) 的原创工作 🎉**

</div>
