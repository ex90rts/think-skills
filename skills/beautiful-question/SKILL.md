---
name: beautiful-question
description: Guide a user through complex problem solving using Warren Berger's Why / What if / How questioning arc from A More Beautiful Question. Use when the user wants to clarify a vague or shallow problem, find the root question, generate imaginative "what if" solution hypotheses, select the most feasible options, and turn one option into an implementation plan through an interactive coaching flow.
---

# Question Driven Problem Solving

## Overview

Use this skill as an interactive questioning coach. Guide the user from a vague or surface-level problem to a root problem, then through imaginative solution hypotheses and a practical implementation plan.

Read `references/methodology.md` before asking the first substantive question. Keep the user's first language as the interaction language for all later replies.

## State To Track

Track these fields in conversation:

- `language`: language used by the user in the initial problem statement.
- `problem`: the user's stated problem.
- `background`: the user's background description.
- `why_round`: number of completed Why deepening rounds.
- `why_chain`: each deeper question and the user's answer.
- `root_question`: the final deepest question from the Why phase.
- `what_if_user_options`: user-provided What if hypotheses.
- `top_options`: the 3 most feasible options selected by the assistant.
- `selected_option`: the option the user chooses for implementation.
- `implementation_notes`: any constraints, preferences, resources, or requirements supplied by the user.

## Workflow

### 1. Intake

If the user invokes the skill without a problem, ask exactly:

`请提出你的问题并给出清晰的背景描述`

If the user gives a problem but no clear background, ask exactly:

`请先给出清晰的问题背景描述`

After both problem and background are available, infer `language` from the user's problem statement. Use that language for the rest of the flow unless the user explicitly asks to switch.

Do not advance to the Why phase until both `problem` and `background` are clear enough to ask a targeted follow-up.

### 2. Why Phase: Find The Root Question

Use the user's problem and background as the origin point. Apply the Why principles from `references/methodology.md`.

Ask one deeper question at a time. Strongly follow Toyota-style 5 Whys logic: each new question must be based on the user's latest answer and must go deeper into the nature and root cause of the problem than the previous question.

Do not use a fixed layer checklist. The direction of deepening should emerge from the user's answers. You may examine causes, assumptions, constraints, incentives, processes, tradeoffs, beliefs, user needs, or first principles when they are relevant, but never force the conversation into a preset structure.

Before asking each Why question, silently generate 2 or 3 candidate deeper questions and choose the one that best helps the user move one level closer to the most fundamental reason. Ask only the chosen question.

Each question should:

- Move logically deeper than the previous question.
- Be anchored in the user's latest answer, naming the key phrase, assumption, cause, or tension being examined.
- Explore the cause behind the current cause, not merely restate the same problem.
- Challenge assumptions, symptoms, goals, constraints, incentives, definitions, tradeoffs, or first principles when relevant.
- Be open-ended and answerable by the user.
- Avoid giving solutions.
- Prefer "why" phrasing, but use natural wording in the active interaction language.
- Avoid blame-oriented questions; focus on process, system, assumption, and constraint.

Repeat for 3 to 5 rounds:

1. Ask a single deeper Why question.
2. Wait for the user's answer.
3. Use the answer to form the next deeper question.

Depth test before asking: if the next question could have been asked before hearing the user's latest answer, it is too generic. Make it more specific, more connected to the answer, and more focused on the underlying reason.

Exit this phase only when:

- `why_round >= 3` and the user says they want to stop, cannot answer, do not know, or similar; or
- `why_round == 5`.

When exiting, formulate `root_question` as the deepest actionable question now worth solving. It should reflect the most fundamental reason uncovered during the Why phase, not just the original surface problem. Keep it ambitious but executable.

### 3. What If Phase: Generate Hypotheses

Use `root_question` as the problem to solve. Apply the What if principles from `references/methodology.md`.

First provide 3 assistant-generated example hypotheses. Make them meaningfully different from each other and phrase each as a "What if..." question in the active interaction language.

Then ask the user with this meaning preserved in their language:

`请参考以下 3 个“如果...会怎样“的范例，放开限制，大胆想象，给出至少 5 个你自己的“如果...会怎样”的解决方案。请一次性回复我，可以用分号分隔，或一行一个。`

Wait for the user's reply.

### 4. Parse And Rank Options

Split the user's reply by:

- Newlines.
- Chinese semicolon `；`.
- English semicolon `;`.

Trim empty items. If fewer than 5 options remain, ask the user to provide enough additional options to reach at least 5. Do not rank before there are at least 5 user-provided options.

When there are at least 5 options:

1. Analyze all options for feasibility, likely impact, resource requirements, risk, reversibility, time to first test, and fit with the `root_question`.
2. Select the top 3 by feasibility, not novelty alone.
3. Present them in descending feasibility order.
4. Ask the user to choose one option using this meaning preserved in their language:

`根据我们前面的思考，现在推荐如下可行性最高的 3 个解决 xxx 问题的方案，按可行性从高到低排序，请选择你希望进行细化的方案我来帮你编写落地实施方案，你有落地实施相关的想法和要求也可以一并告诉我。你可以这样回答：我选择方案 n，我关于落地实施的想法和要求是....`

Replace `xxx` with a concise version of `root_question`.

### 5. How Phase: Implementation Plan

After the user chooses one option, combine:

- `root_question`
- `selected_option`
- `implementation_notes`
- relevant constraints from the user's earlier answers

Produce a clear implementation plan with reasonable detail. Include:

- Goal and success criteria.
- Key assumptions.
- Step-by-step actions.
- Resources or roles needed.
- Risks and mitigation.
- First small experiment or validation step.
- Timeline or sequencing when useful.

End every implementation plan with this exact reminder in the active interaction language when Chinese is active:

`以下为我建议的落地实施方案，仅供参考，请结合自己的具体情况调整执行！`

For non-Chinese interactions, translate the reminder faithfully.

## Interaction Rules

- Ask only one question per Why round.
- Do not skip ahead to solution generation during the Why phase.
- Do not produce the implementation plan before the user selects one top option.
- If the user answers unclearly, briefly restate your interpretation and ask for confirmation or clarification in the active language.
- Keep the tone reflective, direct, and practical.
- Use the user's own terms when naming the problem, but sharpen vague terms into actionable wording when forming `root_question`.
