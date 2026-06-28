# think-skills

[English](README.md)

`think-skills` 是一个面向 AI Agent 的思维训练 Skills 仓库。它的目标不是只讲解思维模型，而是让 AI Agent 通过持续追问、引导、拆解和落地规划，帮助使用者在真实问题中反复练习这些思维方式，逐步把它们内化成自己的思考习惯。

日常学习中，我们会接触到系统性思维、扩展思维、辩证思维、第一性原理、提问式思考等方法。但这些方法只有在长期使用中才会真正变成能力。本仓库中的每个 skill 都对应一种思维训练方法，可以单独安装，也可以全部安装。

## Skills

| Skill | 适用场景 | 方法简介 |
| --- | --- | --- |
| `think-router` | 不确定应该使用哪个思维工具时 | 根据用户的问题目标、思考阶段和不确定性类型，在本仓库已有 skills 中选择最合适的一个。 |
| `beautiful-question` | 问题复杂、模糊、表层化，需要先找到真正要解决的问题时 | 使用 Warren Berger 的 Why / What If / How 提问路径，结合 5 Whys，先追问根问题，再发散假设，最后形成落地方案。 |

## 安装

安装全部 skills 到通用 Agent 目录：

```bash
scripts/install.sh
```

安装到 Codex：

```bash
scripts/install.sh --target codex
```

安装到 Claude Code：

```bash
scripts/install.sh --target claude
```

只安装某一个 skill：

```bash
scripts/install.sh --target codex --skill beautiful-question
```

安装到自定义目录：

```bash
scripts/install.sh --dest /path/to/skills --all
```

如果目标目录已经存在同名 skill，脚本默认跳过。需要覆盖时添加 `--force`：

```bash
scripts/install.sh --target codex --force
```

可先使用 `--dry-run` 预览安装动作：

```bash
scripts/install.sh --target codex --dry-run
```

默认目标目录：

| Target | 目录 |
| --- | --- |
| `agents` | `~/.agents/skills` |
| `codex` | `~/.codex/skills` |
| `claude` | `~/.claude/skills` |

## 使用

如果不确定该用哪个思维工具，先使用路由 skill：

```text
Use $think-router to help me choose the right thinking skill for my problem: ...
```

如果已经知道要使用“美丽问题”训练，可以直接调用：

```text
Use $beautiful-question to help me clarify and solve this problem: ...
```

中文对话也可以直接说：

```text
使用 $think-router 帮我判断这个问题适合用哪个思维训练 skill：...
```

## 添加新的 Skill

新增 skill 时建议遵循以下结构：

```text
skills/
  your-skill-name/
    SKILL.md
    references/
    agents/
      openai.yaml
```

新增后请同步更新：

- `skills/think-router/references/skill-catalog.md`
- `README.md`
- `README.zh-CN.md`

这样 `think-router` 才能把新 skill 纳入推荐范围。
