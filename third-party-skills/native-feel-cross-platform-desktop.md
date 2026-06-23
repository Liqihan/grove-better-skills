# native-feel-cross-platform-desktop

来源：<https://github.com/yetone/native-feel-skill>

## 适用场景

用于设计、原型验证或重写跨平台桌面应用，尤其是同时要求 macOS / Windows 多端交付和接近原生体验的产品。

适合问题包括：

- Electron、Tauri、系统 WebView 或原生壳架构怎么选
- 如何让 WebView 包装的桌面应用减少“网页感”
- WKWebView / WebView2 闪烁、隐藏窗口节流、启动白屏等问题
- Rust、Swift、C#、TypeScript 之间的 typed IPC 边界
- 桌面应用启动、内存、窗口、系统材质、快捷键和平台约定审计

## 为什么值得记录

这个 Skill 把 Raycast 2.0 技术拆解、跨平台桌面架构取舍、WebView 生存指南和发布前 native-feel audit 整理成可执行工作流。它的价值不只是“做得更好看”，而是帮助判断哪些原生体验必须交给系统，哪些逻辑可以跨平台共享，以及什么时候应该直接放弃这套架构。

## 与本仓库自研 Skills 的关系

- 与 `skill-recommender` 互补：当用户描述的是桌面架构、WebView、跨平台原生体验或 Raycast 风格应用时，可以作为第三方候选推荐。
- 不替代 `risk-oriented-code-review`：前者偏产品架构和体验审计，后者偏当前代码 diff 的风险 review。

## 安装方式

上游 README 给出的安装命令：

```bash
npx skills add yetone/native-feel-skill -g
```

如果当前环境不支持 `-g`，可按上游 README 的手动安装说明，把仓库克隆到用户级 skills 目录，并确认 `SKILL.md`、`references/` 和 `checklists/` 都存在。

## 记录状态

- `installable: true`
- 已确认来源仓库包含 `SKILL.md`
- 适合作为第三方推荐候选，不放入本仓库 `skills/` 目录
