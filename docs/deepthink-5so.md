# deepthink-5so

`deepthink-5so` is an interactive deep-thinking skill for consequence-chain inference. It uses the 5So method: repeatedly ask "so what?" or "so then what?" about a phenomenon to discover shallow, deep, and deeper results until the chain reaches a useful endpoint.

Use it when the user wants to reason forward from a phenomenon rather than diagnose backward causes.

## Best For

- Exploring where a trend, event, signal, behavior, or policy may lead.
- Finding second-order and third-order consequences.
- Stress-testing a decision by asking what it could cause next.
- Turning vague concern into a structured consequence chain.
- Identifying early indicators and action implications.
- Knowing when to stop inference because the next layer is too low-probability or no longer useful.

## Workflow

1. **Intake**: collect the phenomenon, context, stakeholders, and time horizon.
2. **Starting frame**: define the inference scope and uncertainty.
3. **First So**: infer the most direct result.
4. **Continue the chain**: ask "so what?" step by step from the latest result.
5. **Branch when needed**: split into 2 or 3 paths only when uncertainty is material.
6. **Stop deliberately**: stop at an actionable, terminal, repeated, or low-practical-value layer.
7. **Synthesize**: present the chain, assumptions, probabilities, impact, watchpoints, and next actions.

## Example Invocation

```text
Use $deepthink-5so to explore what this phenomenon could ultimately lead to: our best users are spending less time in the product, but retention has not dropped yet. Background: ...
```

Chinese is also fine:

```text
使用 $deepthink-5so 帮我推演这个现象最终可能导致什么结果：团队开始习惯性推迟重要决策。背景是……
```

## Key Resources

- `skills/deepthink-5so/SKILL.md`: workflow and interaction rules.
- `skills/deepthink-5so/references/methodology.md`: 5So method details and stopping rules.

## Notes

5So is not 5Why. 5Why traces causes backward; 5So traces consequences forward. The skill should keep probability visible and avoid turning a possible endpoint into a prediction.
