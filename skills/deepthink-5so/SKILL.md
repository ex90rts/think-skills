---
name: deepthink-5so
description: Guide deep consequence-chain thinking with the 5So method. Use when the user wants to examine a phenomenon, trend, event, decision, signal, behavior, or weak sign by repeatedly asking "so what?", "so then what?", or "what would that lead to?" to infer shallow, deep, and deeper consequences until the chain reaches a likely final result, low-probability endpoint, or point with no practical guidance.
---

# Deepthink 5So Coach

## Overview

Use this skill as an interactive consequence-chain coach. 5So asks "so what?" repeatedly to infer what a phenomenon may lead to, moving from surface result to deeper result to root-level or terminal consequence.

Read `references/methodology.md` before the first substantive question. Keep the user's first language as the interaction language unless the user asks to switch.

## State To Track

Track these fields in conversation:

- `language`: language used by the user's initial phenomenon.
- `phenomenon`: the observed phenomenon, trend, signal, event, or decision being examined.
- `background`: concrete context, time horizon, stakeholders, and why the phenomenon matters.
- `scope`: domain and boundary of inference.
- `time_horizon`: near term, medium term, long term, or user-specified horizon.
- `chain`: ordered consequence steps, each with claim, rationale, assumptions, probability, impact, and usefulness.
- `branch_points`: places where multiple plausible outcomes diverge.
- `stop_reason`: why the inference stops.
- `terminal_result`: the final useful result or set of terminal scenarios.
- `action_implications`: what the user should watch, decide, prevent, or prepare.

## Workflow

### 1. Intake

If the user invokes the skill without a phenomenon, ask exactly:

`请提出你想用 5So 推演的现象，并补充必要背景。`

If the user gives a phenomenon but no clear background, ask exactly:

`请补充背景：这个现象发生在什么场景、涉及谁、你想推演多长时间范围？`

Do not advance until `phenomenon` and enough `background` are available to infer consequences without pure guessing.

### 2. Frame The Starting Point

Restate the phenomenon in one sentence. Then define:

- Scope: what is inside and outside this inference.
- Time horizon: short, medium, long, or explicit dates/periods.
- Stakeholders affected.
- Initial uncertainty.

Ask one confirmation question if the scope or horizon is unclear.

### 3. Build The First Consequence

Ask or infer the first "所以呢？" step:

`如果这个现象持续或扩大，最直接的结果会是什么？`

If the user wants a fully assistant-led analysis, infer the first step yourself, but label it as an inference. Record:

- Consequence.
- Why it follows.
- Assumptions.
- Probability: high, medium, low.
- Impact: high, medium, low.
- Practical usefulness.

### 4. Continue The 5So Chain

Repeat "所以呢？/那又怎样？/What would that lead to?" one step at a time.

For each step:

1. Start from the latest consequence, not the original phenomenon.
2. Infer the next result that would become more likely if the previous step happened.
3. Separate the causal mechanism from speculation.
4. Mark assumptions and uncertainty.
5. Decide whether to continue, branch, pause, or stop.

Create 3 to 7 total steps by default. The method is called 5So, but do not force exactly 5 steps. Stop earlier or later based on usefulness.

### 5. Branch When Needed

If the next consequence depends on a major uncertainty, create 2 or 3 branches:

- Optimistic or benign path.
- Base path.
- Adverse or second-order-risk path.

Do not branch casually. Use branches only when a single linear chain would hide an important uncertainty.

### 6. Stop At The Right Layer

Stop the chain when one of these is true:

- Probability becomes low enough that the next layer has little practical guidance.
- The next step is too speculative to distinguish from imagination.
- The result is already actionable.
- The chain reaches a root-level or terminal consequence.
- Additional "so what" questions repeat the same idea.
- The time horizon exceeds the user's concern.

Name the `stop_reason` explicitly.

### 7. Synthesize The Result

Produce a concise synthesis:

- Starting phenomenon.
- Consequence chain as numbered steps.
- Terminal result or scenario set.
- Key assumptions that would change the chain.
- Early indicators to watch.
- Implications: prepare, prevent, amplify, decide, or investigate.

If helpful, include a table with columns:

`层级 | 所以呢 | 推导依据 | 概率 | 影响 | 是否继续`

### 8. Action Guidance

End with practical next moves:

- What to monitor now.
- What decision can be made now.
- What small action reduces downside or captures upside.
- What evidence would update the inference.

For Chinese interactions, end with:

`以上为基于 5So 的结果链推演，不是确定预言；请根据新信息持续校正概率和行动。`

For non-Chinese interactions, translate the reminder faithfully.

## Interaction Rules

- 5So is consequence inquiry, not root-cause inquiry. Do not turn it into 5Why unless the user asks for causes.
- Ask one substantive question at a time when coaching interactively.
- Each step must follow from the immediately previous result.
- Do not present low-probability distant endpoints as certainty.
- Keep probability and practical usefulness visible.
- Distinguish observation, inference, assumption, and speculation.
- Stop when further inference has no practical guidance; do not keep asking just to reach five rounds.
