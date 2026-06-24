# ponytail

来源：<https://github.com/DietrichGebert/ponytail>

## 适用场景

用于约束 Agent 少写代码、少引依赖、少造抽象，优先复用项目已有实现、标准库和平台原生能力。

适合问题包括：

- 需求可能被过度实现，需要先判断是否真的要做
- 当前 diff 看起来能跑，但可能引入了不必要的层、依赖、配置或样板代码
- 想 review “哪些代码可以删掉”
- 想做全仓库的 over-engineering audit
- 想让 Agent 在保持安全、校验和可访问性底线的前提下走最短实现路径

## 为什么值得记录

`ponytail` 的价值在于把“少写代码”变成一个明确的工程判断顺序：先判断是否需要存在，再看项目内已有实现、标准库、平台原生能力和已安装依赖，最后才写最小可工作的代码。它同时提供 review/audit 类 skill，用于识别可删除的抽象、依赖和重复实现。

## 相关 Skills / 命令

- `ponytail`：主 skill，约束实现走 YAGNI、复用和最小正确 diff。
- `ponytail-review`：针对当前 diff 检查过度工程，输出可删除或可简化项。
- `ponytail-audit`：针对整个仓库检查过度工程。
- `ponytail-debt`：整理已延期的 `ponytail:` 简化标记。
- `ponytail-gain`：查看 benchmark / impact 信息。
- `ponytail-help`：查看命令帮助。

## 与本仓库自研 Skills 的关系

- 与 `skill-recommender` 互补：当用户场景是“少写代码”“避免过度设计”“review 能不能删代码”时，可以作为第三方候选推荐。
- 与 `risk-oriented-code-review` 互补：`ponytail` 关注复杂度和过度工程，`risk-oriented-code-review` 关注隐藏副作用、兼容性、边界、性能、安全和维护风险。

## 安装方式

Codex 插件安装方式：

```bash
codex plugin marketplace add DietrichGebert/ponytail
```

然后在 Codex 中打开 `/plugins`，选择 Ponytail marketplace 并安装 Ponytail。上游 README 还提供 Claude Code、GitHub Copilot CLI、Gemini CLI、OpenCode、OpenClaw 等环境的安装方式。

## 记录状态

- `installable: true`
- 已确认来源仓库包含 `skills/ponytail/SKILL.md`
- 已确认仓库同时包含 `ponytail-review`、`ponytail-audit` 等辅助 skill
- 适合作为第三方推荐候选，不放入本仓库 `skills/` 目录
