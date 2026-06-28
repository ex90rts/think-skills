# think-skills

[中文](README.CN.md)

`think-skills` is a collection of thinking-training skills for AI agents. The goal is not just to explain thinking models, but to let an AI agent guide users through repeated practice with real problems: asking sharper questions, widening options, testing assumptions, and turning thinking into action.

We often learn frameworks such as systems thinking, expansive thinking, dialectical thinking, first-principles thinking, and question-driven thinking. These ideas only become real capability through long-term use. Each skill in this repository represents one thinking method. You can install one skill at a time or install the full set.

## Skills

| Skill                | Best For                                                                                 | Method                                                                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `think-router`       | When you are unsure which thinking tool fits your problem                                | Routes your problem to one of the other skills in this repository based on goal, thinking stage, and type of uncertainty.                                 |
| `beautiful-question` | Complex, vague, or surface-level problems where you need to find the real question first | Uses Warren Berger's Why / What If / How arc, strengthened with 5 Whys, to uncover a root question, generate options, and produce an implementation plan. |

## Installation

Install all skills into the generic Agent skills directory:

```bash
scripts/install.sh
```

Install into Codex:

```bash
scripts/install.sh --target codex
```

Install into Claude Code:

```bash
scripts/install.sh --target claude
```

Install one skill only:

```bash
scripts/install.sh --target codex --skill beautiful-question
```

Install into a custom directory:

```bash
scripts/install.sh --dest /path/to/skills --all
```

If a skill already exists in the destination, the installer skips it by default. Add `--force` to replace existing skill directories:

```bash
scripts/install.sh --target codex --force
```

Preview actions without copying files:

```bash
scripts/install.sh --target codex --dry-run
```

Default destinations:

| Target   | Directory          |
| -------- | ------------------ |
| `agents` | `~/.agents/skills` |
| `codex`  | `~/.codex/skills`  |
| `claude` | `~/.claude/skills` |

## Usage

If you are not sure which thinking tool to use, start with the router:

```text
Use $think-router to help me choose the right thinking skill for my problem: ...
```

If you already know you want the Beautiful Question flow:

```text
Use $beautiful-question to help me clarify and solve this problem: ...
```

Chinese usage is also fine:

```text
使用 $think-router 帮我判断这个问题适合用哪个思维训练 skill：...
```

## Adding a New Skill

Recommended structure:

```text
skills/
  your-skill-name/
    SKILL.md
    references/
    agents/
      openai.yaml
```

After adding a skill, update:

- `skills/think-router/references/skill-catalog.md`
- `README.md`
- `README.zh-CN.md`

This keeps `think-router` aligned with the actual skills available in the repository.
