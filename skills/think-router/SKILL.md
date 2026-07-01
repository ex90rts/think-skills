---
name: think-router
description: Route a user's problem to the most suitable skill in this repository when the user is unsure which tool to use. Use when the user asks which skill, method, or workflow fits their situation, or when they describe a problem and explicitly want help choosing among this repo's skills.
---

# Think Router

## Overview

Use this skill as a repository skill router. Help the user choose the best skill from the other skills in this repository, then tell them how to invoke it.

Read `references/skill-catalog.md` before making a routing recommendation. Keep the user's first language as the response language unless the user asks to switch.

## Scope

Only recommend skills that are listed in `references/skill-catalog.md`.

Do not recommend `think-router` itself as a destination skill. Do not invent external skills or thinking frameworks that are not present in the catalog.

## Routing Workflow

### 1. Intake

If the user has not described their problem or goal clearly enough to route, ask one concise clarification question.

Prefer asking about the user's immediate intent:

- Are they trying to define the real problem?
- Generate possibilities?
- Make a decision?
- Diagnose a failure?
- Review, refactor, or design code?
- Build an implementation plan?
- Reflect on a learning or life question?

Ask only what is needed to route. Do not start coaching with another method before selecting a skill.

### 2. Match

Compare the user's problem with each catalog entry using:

- The user's desired outcome.
- The stage of thinking they are in.
- The type of uncertainty they face.
- The interaction style they need.
- Any explicit constraints, such as time, depth, or language.

If one skill clearly fits, recommend one primary skill.

If two or three skills plausibly fit, show a short ranked list and explain the tradeoff. Still pick one default recommendation.

If no listed skill fits well, say that the current repository does not yet include a strong fit and recommend the nearest available skill only if it would still be useful.

### 3. Output Format

Respond in this structure:

1. `推荐 Skill`: the selected skill name.
2. `为什么`: 2 or 3 concise reasons tied to the user's situation.
3. `如何使用`: a ready-to-copy invocation sentence, such as `Use $beautiful-question to ...`.
4. `如果你的真实目标是...`: optional, only when an alternative skill or no strong fit should be mentioned.

For English interactions, translate the labels naturally:

1. `Recommended Skill`
2. `Why`
3. `How to Use`
4. `If your real goal is...`

## Interaction Rules

- Keep routing answers short and practical.
- Recommend skills by exact directory and frontmatter name.
- Do not route to this skill itself.
- Do not run the destination skill's full workflow unless the user explicitly asks to start it.
- When the user asks to start the recommended skill, continue with that skill's workflow if it is available in the active environment.
