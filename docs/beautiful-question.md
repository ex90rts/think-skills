# beautiful-question

`beautiful-question` is an interactive problem-framing and problem-solving skill based on Warren Berger's Why / What If / How arc from *A More Beautiful Question*, strengthened with Toyota-style 5 Whys.

Use it when the user has a vague, complex, or surface-level problem and needs to discover the deeper question before choosing a solution.

## Best For

- Clarifying a messy or ambiguous problem.
- Moving from symptoms to root causes.
- Generating multiple solution hypotheses before committing to one.
- Turning a selected option into an implementation plan.
- Coaching-style conversations where the assistant asks one question at a time.

## Workflow

1. **Intake**: collect the user's problem and background.
2. **Why phase**: ask 3 to 5 deeper questions, one at a time, using the user's latest answer to move toward the root question.
3. **What If phase**: generate example hypotheses and ask the user to contribute at least 5 possible solutions.
4. **Option ranking**: rank the user's options by feasibility, impact, risk, reversibility, resource needs, and time to first test.
5. **How phase**: turn the selected option into a practical implementation plan.

## Example Invocation

```text
Use $beautiful-question to help me clarify and solve this problem: our team keeps starting projects but struggles to finish them. Background: ...
```

Chinese is also fine:

```text
使用 $beautiful-question 帮我澄清并解决这个问题：我们团队总是启动很多项目，但很难真正完成。背景是……
```

## Key Resources

- `skills/beautiful-question/SKILL.md`: workflow and interaction rules.
- `skills/beautiful-question/references/methodology.md`: method details for the Why / What If / How flow.

## Notes

This skill intentionally delays solution generation until the root question has been explored. It should not jump directly to advice during the Why phase.
