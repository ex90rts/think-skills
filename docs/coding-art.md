# coding-art

`coding-art` is a software engineering judgment skill. It distills principles from *Code Complete 2* and *The Art of UNIX Programming* into a practical checklist for writing, reviewing, refactoring, designing, debugging, and optimizing code.

Use it when the task needs code-quality judgment rather than only syntax help.

## Best For

- Writing new code with clear structure and maintainability.
- Reviewing code for design, complexity, naming, defensive programming, testability, and performance risks.
- Refactoring modules, functions, classes, or interfaces.
- Making architecture tradeoffs.
- Debugging or optimizing with disciplined engineering heuristics.
- Answering programming best-practice questions with explicit principles.

## Agent Use Rules

- Start from the current codebase's goals, constraints, style, tests, and user request.
- Pick only the 3 to 7 principles that matter most for the task.
- For reviews, lead with concrete risks, impact, file/location, principle reference, and an actionable fix.
- For performance, security, concurrency, and reliability claims, prefer evidence from profiling, tests, reproduction paths, threat models, or specific code paths.
- Treat these principles as heuristics. Project conventions, language ecosystems, framework behavior, and business constraints can override a general principle.
- When concrete API behavior or version-specific framework guidance matters, use current project code and official documentation rather than this skill alone.

## Principle Areas

The full reference organizes 66 principles into 10 areas:

| Area | Focus |
| --- | --- |
| Mindset and philosophy | Complexity management, correctness, simplicity, engineering attitude. |
| Design and modularity | Encapsulation, coupling, cohesion, orthogonality, interfaces. |
| Naming and expression | Names, constants, self-documenting code, comments. |
| Function design | Function scope, parameters, abstraction level, return values. |
| Control flow and data | Conditionals, loops, data structure choices. |
| Defensive programming | Error handling, assertions, boundaries, robustness. |
| Interfaces and protocols | Contracts, compatibility, data formats, communication. |
| Concurrency and state | Shared state, synchronization, state minimization. |
| Testing and quality | Testing strategy, debugging, quality feedback loops. |
| Optimization and engineering | Measurement, performance, tools, documentation, craft. |

## Example Invocation

```text
Use $coding-art to review this code for complexity, naming, modularity, and defensive-programming issues.
```

Chinese is also fine:

```text
使用 $coding-art 按编程工艺原则评审这段代码，重点看复杂度、命名、模块边界和防御式编程。
```

## Key Resources

- `skills/coding-art/SKILL.md`: skill overview and application workflow.
- `skills/coding-art/references/principles.md`: full 66-principle reference with explanations, anti-signals, and source attribution.

## Notes

The principles are heuristics, not mechanical rules. When principles conflict, prioritize the context of the actual codebase and the central goal of reducing unnecessary complexity.
