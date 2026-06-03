# 更新日志

所有重要变更均记录在此文件中。格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/)。

---

## v2.2.0 — 2026-06-03

**新增：F 键全屏 + 总览交互优化**

### 新增

- 🆕 **F 键全屏切换**：所有模式均支持按 `F` 进入/退出浏览器全屏（Fullscreen API），隐藏浏览器工具栏和边框
- 🆕 **快捷键速查表**：SKILL.md 新增完整的键盘快捷键参考

### 变更

- 🔄 **总览统一用 N 键**：ESC 退出全屏是浏览器安全机制无法拦截，总览退出统一改为再按 `N` 键
- 🔄 **总览提示优化**：提示文字从 fixed 定位改为 flex 流式横幅，不再与预览卡片重叠
- 🔄 **移除自定义全屏 toast**：浏览器原生已有退出全屏提示，去掉重复的自定义 toast

### 修复

- 🐛 修复全屏 + 总览同时打开时 ESC 冲突问题
- 🐛 修复总览提示与预览卡片重叠问题

---

## v2.1.0 — 2026-06-03

**新增：总览预览功能 + Skill 重命名**

### 新增

- 🆕 **总览预览面板（Overview Panel）**：模式一和模式二均支持按 `N` 键打开全屏总览，网格展示所有页面 25% 缩略图
  - 每张卡片标注页码和页面标题，点击直接跳转
  - `N` / `ESC` 键切换总览面板
  - 缩略图自动隐藏装饰元素（粒子、光晕），动画冻结在可见状态
- 🆕 **模式二隐藏 UI**：模板重构版页面默认无任何可见按钮，通过键盘快捷键操作，画面更干净

### 变更

- 🔄 **Skill 重命名**：`science-content-ppt` → `ostar-science-content-ppt`
- 🔄 **仓库迁移**：从 [Unclecheng-li/AI-Animation-Skill](https://github.com/Unclecheng-li/AI-Animation-Skill) fork，推送至独立仓库
- 🔄 **README 更新**：新增致谢原作者的章节，说明继承关系和新增功能

---

## v2.0.0 — 2025-04-15

**重大重构：模板体系升级 + 工作流优化**

### 新增

- 🆕 **PPT Level2 模板**：新增 26 个高质量模板（`assets/templates/PPT Template-level2/`），按主题分 9 个系列，覆盖对比/步骤/概念/案例/警示/辩论等场景
- 🆕 **SUMMARY.md 选择指南**：Level2 和 Animation 各自新增 AI 选模板参考文档，模型可根据科普内容类型自动匹配最佳模板
- 🆕 **已知问题 FAQ**：SKILL.md 新增 Q1~Q3 实操踩坑总结（动画不重触发、代码量不足、流程图模式说明）
- 🆕 **参数说明表**：SKILL.md 新增清晰的参数默认值和说明

### 变更

- 📁 **目录重构**：`templates/` → `assets/templates/`，结构更规范
  - `templates/PPT-Template/` → `assets/templates/PPT/`（基础模板，回退选用）
  - `templates/RNN-Template/` → `assets/templates/Animation/`（更准确的命名）
- 🔄 **Skill 重命名**：`AI-Animation` → `science-content-ppt`，更准确描述能力边界
- 🔄 **工作流精简**：原三步流程优化为两步模式（PPT 模式 + 流程图模式），Level2 模板替代原 Step 2
- 🔄 **模板优先级调整**：PPT Level2 模板优先，基础 PPT 模板回退
- 🔄 **emoji → UI 图标**：Step 2 强制将 emoji 替换为 Font Awesome / Lucide 图标库
- 🔄 **动画重置修复**：新增 cloneNode 动画重置 JS，解决切换页面后动画不复发的 bug

### 删除

- ❌ `references/workflow.md`（工作流内容已整合进 SKILL.md）
- ❌ PPT-Generate-5/6/7.html（被 Level2 模板替代）

---

## v1.0.0 — 2025-03-XX

**初始发布**

- 基础 PPT 模板（PPT-Generate-1~7）
- RNN 系列 Animation 模板
- 三步工作流：文本 → 基础 HTML → PPT 模板重构 → 流程图重构
- Skill 定义文件 SKILL.md
