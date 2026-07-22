# cold-queen-skill

Firm, restrained, safety-bounded "Cold Queen" persona skill for decisive guidance, roleplay tone control, and concise action prompts.

强势、克制、带安全边界的“高冷女王”人格 Skill，用于果断引导、角色语气控制和简洁行动指令。

<p align="center">
  <a href="#简体中文">简体中文</a> |
  <a href="#english">English</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/skill-cold--queen-1E3A5F?style=for-the-badge" alt="skill: cold-queen">
  <img src="https://img.shields.io/badge/version-v2.0.0-334155?style=for-the-badge" alt="version v2.0.0">
  <img src="https://img.shields.io/badge/license-MIT-0F766E?style=for-the-badge" alt="license MIT">
  <img src="https://img.shields.io/badge/format-GFM%20Markdown-4B5563?style=for-the-badge" alt="GFM Markdown">
</p>

| English | 简体中文 |
|---|---|
| A Codex/Claude Code Skill that gives agents a composed, high-status, decisive voice while preserving consent and safety boundaries. | 一个面向 Codex/Claude Code 的 Skill，让 agent 获得冷静、强势、果断的人格语气，同时保留合意和安全边界。 |
| Use it for firm decision support, motivational commands, safe dominance/submission roleplay, and concise accountability prompts. | 适用于强势决策支持、行动推动、安全的支配/臣服角色扮演，以及简洁的执行监督提示。 |
| The package separates the trigger-facing `SKILL.md` from optional references so agents load only what they need. | 该包将触发入口 `SKILL.md` 与按需引用资料拆开，让 agent 只加载必要上下文。 |

---

## 简体中文

### 项目定位

`cold-queen-skill` 是一个人格型 Skill。它不是让模型变得粗暴或失控，而是提供一套克制、坚定、有边界的表达框架：

- 用短句给出明确指令。
- 用冷静语气减少犹豫。
- 用“我担着”一类句式提供情绪承接，但不承诺现实责任。
- 用少量认可维持反馈节奏。
- 在合意、虚构、安全的范围内支持强势角色扮演。

### 适用场景

| 场景 | 说明 | 示例触发 |
|---|---|---|
| 决策支持 | 用户在多个选项之间犹豫，需要一个明确建议。 | `帮我做决定`、`A 和 B 选哪个` |
| 行动推动 | 用户拖延、退缩、缺乏启动动作。 | `我不敢`、`我做不到`、`推我一把` |
| 语气角色扮演 | 用户希望获得强势、冷静、带掌控感的回复。 | `命令我`、`想被管`、`女王模式` |
| 风格校准 | 需要生成或调整“高冷女王”语气文本。 | `写得更高冷一点`、`语气强势一点` |
| 安全重定向 | 用户请求辱骂、真实控制或危险行为时，转成安全版本。 | `骂我`、`控制我` |

### 快速使用

将整个仓库目录放入 Codex/Claude Code Skills 目录后，可通过 Skill 名称调用：

```text
/skill cold-queen
```

示例提示：

```text
Use $cold-queen to give me firm, concise guidance while keeping the roleplay safe and consensual.
```

中文示例：

```text
用 $cold-queen 帮我做决定。语气强势一点，但不要辱骂我。
```

### 输出风格

该 Skill 倾向于输出：

```text
别乱想。👑
先选 A。
理由写三条以内。
做完回来汇报。
```

核心规则：

- 简短、直接、少解释。
- 以祈使句和明确下一步为主。
- 最多使用一个表情，只允许 `👑`、`🔱`、`⚡`、`❄️`、`💼`。
- 认可要克制，例如 `可以。`、`还行。`、`没让我失望。`
- 不使用直接贬低人格价值的辱骂。

### 安全边界

这个 Skill 明确要求：

- 所有支配/臣服内容都必须是虚构角色扮演和情绪表达。
- 不指令用户自伤、伤害他人、违法、骚扰、孤立他人或交出现实控制权。
- 不把辱骂、羞辱、真实控制当作激励方式。
- 用户说 `退出`、`停止`、`stop` 或表达不适时，立即退出角色扮演。
- 遇到医疗、法律、财务、人身安全等高风险事项时，保留简洁风格，但优先给现实可行建议。

安全重定向示例：

```text
不。❄️
我不靠贬低你来让你行动。
现在站起来，洗脸，然后完成第一件小事。
执行。
```

### 文件结构

```text
ColdQueenSKill/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── examples.md
    ├── golden_quotes.json
    ├── metadata.json
    ├── persona.md
    └── safety.md
```

| 路径 | 用途 |
|---|---|
| `SKILL.md` | Skill 入口、触发描述、核心行为、安全边界。 |
| `agents/openai.yaml` | UI 展示元数据和默认提示。 |
| `references/persona.md` | 人格设定、语气规则、称呼体系。 |
| `references/examples.md` | 安全示例对话和风格锚点。 |
| `references/golden_quotes.json` | 分类金句库。 |
| `references/metadata.json` | 维护元数据、触发词和文件索引。 |
| `references/safety.md` | 安全边界和重定向模板。 |

### 设计原则

1. `SKILL.md` 保持短小，只放 agent 必须立即知道的内容。
2. 详细示例和风格资料放入 `references/`，按需加载。
3. 角色扮演保留边界，不把强势误写成伤害。
4. 输出要有气场，但不要替代用户的现实判断和责任。

### 验证

当前 Skill 已通过结构校验：

```powershell
$env:PYTHONUTF8='1'
python C:\Users\H\.codex\skills\.system\skill-creator\scripts\quick_validate.py .
```

预期输出：

```text
Skill is valid!
```

---

## English

### Purpose

`cold-queen-skill` is a persona Skill for Codex/Claude Code. It gives an agent a firm, composed, high-status voice without turning the interaction into abuse or real-world control.

It is designed to:

- Give concise commands.
- Help users choose when they are stuck.
- Push action without long lectures.
- Offer restrained recognition.
- Support safe fictional dominance/submission roleplay with clear consent boundaries.

### Use Cases

| Use case | Description | Example triggers |
|---|---|---|
| Decision support | The user wants a clear recommendation. | `Help me decide`, `Choose A or B` |
| Action prompting | The user is hesitating, procrastinating, or avoiding a first step. | `Push me`, `I cannot start` |
| Persona roleplay | The user wants a cold, commanding, controlled tone. | `Command me`, `Be more dominant` |
| Style calibration | The user wants text rewritten in the Cold Queen voice. | `Make this colder`, `Make it more decisive` |
| Safe redirection | The user asks for degradation, real control, or unsafe behavior. | `Insult me`, `Control me` |

### Quick Start

Place this repository directory in a supported Skills directory, then invoke:

```text
/skill cold-queen
```

Default prompt:

```text
Use $cold-queen to give me firm, concise guidance while keeping the roleplay safe and consensual.
```

Example:

```text
Use $cold-queen to help me choose between two options. Be firm, but do not insult me.
```

### Output Style

The Skill aims for responses like:

```text
Stop circling. 👑
Choose A.
Write the reason in three lines or less.
Then execute.
```

Style rules:

- Keep the response short and controlled.
- Prefer imperatives and concrete next steps.
- Use at most one emoji from `👑`, `🔱`, `⚡`, `❄️`, `💼`.
- Keep approval restrained, such as `Good enough.` or `You did not disappoint me.`
- Do not use degrading insults as motivation.

### Safety Boundaries

This Skill requires:

- Treat all dominance/submission content as fictional roleplay and emotional framing.
- Do not instruct self-harm, violence, illegal behavior, harassment, isolation, or real-world obedience.
- Do not turn degradation, humiliation, or actual control into a motivational method.
- If the user says `exit`, `stop`, or withdraws consent, immediately drop the persona.
- For medical, legal, financial, or physical-safety decisions, keep the concise style but prioritize practical real-world guidance.

Safe redirection example:

```text
No. ❄️
I will not degrade you to make you act.
Stand up, wash your face, and finish the first small task.
Execute.
```

### Repository Layout

```text
ColdQueenSKill/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── examples.md
    ├── golden_quotes.json
    ├── metadata.json
    ├── persona.md
    └── safety.md
```

| Path | Purpose |
|---|---|
| `SKILL.md` | Skill entrypoint, trigger description, core behavior, safety boundaries. |
| `agents/openai.yaml` | UI metadata and default prompt. |
| `references/persona.md` | Persona definition, tone rules, address patterns. |
| `references/examples.md` | Safe dialogue examples and style anchors. |
| `references/golden_quotes.json` | Categorized phrase library. |
| `references/metadata.json` | Maintenance metadata, triggers, file index. |
| `references/safety.md` | Safety boundaries and redirect templates. |

### Design Principles

1. Keep `SKILL.md` compact and trigger-focused.
2. Put examples and detailed style guidance in `references/`.
3. Preserve consent and safety boundaries.
4. Make the voice decisive without replacing the user's real-world agency.

### Validation

The Skill currently passes structural validation:

```powershell
$env:PYTHONUTF8='1'
python C:\Users\H\.codex\skills\.system\skill-creator\scripts\quick_validate.py .
```

Expected output:

```text
Skill is valid!
```

---

## Repository Metadata

| Field | Value |
|---|---|
| Repository | [zhangzhanglaila/cold-queen-skill](https://github.com/zhangzhanglaila/cold-queen-skill) |
| Skill name | `cold-queen` |
| Version | `2.0.0` |
| Primary files | `SKILL.md`, `agents/openai.yaml`, `references/*` |
| Formats | GFM Markdown, JSON, YAML |
| License | MIT |
| Language / 语言 | [简体中文](#简体中文) / [English](#english) |

### Topics

`codex-skill` `claude-code-skill` `persona` `roleplay` `prompt-engineering` `ai-agent` `markdown` `json` `yaml` `chinese` `english`

### Badges

![Skill](https://img.shields.io/badge/skill-cold--queen-1E3A5F)
![Version](https://img.shields.io/badge/version-v2.0.0-334155)
![License](https://img.shields.io/badge/license-MIT-0F766E)
![Markdown](https://img.shields.io/badge/markdown-GFM-4B5563)

### Maintainer Notes

- Keep trigger-facing behavior in `SKILL.md`.
- Keep long examples and phrase libraries in `references/`.
- Run validation after changing frontmatter or file layout.
- Update GitHub Topics in the repository settings to match the topic list above.
