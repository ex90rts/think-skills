# Skill Catalog

This catalog lists the destination thinking skills currently available in this repository. `think-router` must only recommend skills from this catalog and must not recommend itself.

## beautiful-question

- Directory: `skills/beautiful-question`
- Invocation: `$beautiful-question`
- Best for: complex, vague, or surface-level problems where the user needs to find the real question before solving.
- Method: Warren Berger's Why / What If / How arc from *A More Beautiful Question*, strengthened with Toyota-style 5 Whys.
- Interaction style: guided conversation. The assistant asks one deeper question at a time, helps uncover a root question, expands solution hypotheses, ranks feasible options, and turns one chosen option into an implementation plan.
- Use when the user says things like:
  - "I do not know what the real problem is."
  - "Help me clarify this issue."
  - "I want to think more deeply before choosing a solution."
  - "This problem feels vague or shallow."
  - "Guide me from problem definition to an action plan."

## Catalog Maintenance

When a new thinking skill is added under `skills/`, update this catalog with:

- Skill name.
- Directory.
- Invocation.
- Best-fit problem type.
- Method summary.
- Interaction style.
- Example user intents.
