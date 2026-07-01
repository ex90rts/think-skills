# think-router

`think-router` is the entry skill for choosing among the skills in this repository.

Use it when the user has a problem or task but is unsure which installed skill should handle it. The router reads `skills/think-router/references/skill-catalog.md`, compares the user's goal with the catalog, and recommends one primary skill with a ready-to-copy invocation.

## Best For

- Choosing a skill before starting a deeper workflow.
- Clarifying whether the user needs problem framing, engineering principles, code review, or another repository skill.
- Keeping recommendations limited to skills that actually exist in this repository.

## Not For

- Running the destination skill's full workflow immediately.
- Recommending external methods or skills not listed in the catalog.
- Recommending `think-router` itself as the destination.

## How It Works

The router evaluates:

- The user's desired outcome.
- The stage of thinking or work they are in.
- The type of uncertainty they face.
- The interaction style they need.
- Constraints such as depth, time, and language.

It then returns a short recommendation with:

- The selected skill.
- Why it fits.
- A ready-to-copy prompt.
- Optional alternatives when another skill might fit a different underlying goal.

## Example Invocation

```text
Use $think-router to help me choose the right skill for my problem: I need to review a large refactor but I am not sure whether to focus on architecture, code quality, or debugging.
```

Chinese is also fine:

```text
使用 $think-router 帮我判断这个问题适合用哪个 skill：我想评审一次比较大的重构，但不确定应该从架构、代码质量还是调试风险入手。
```

## Maintenance

When a new repository skill should be discoverable through the router, update:

- `skills/think-router/references/skill-catalog.md`
- `README.md`
- `README.CN.md`
- `docs/<skill-name>.md`
