# Skills quick reference

Enter these prompts in Codex chat, not your shell terminal. The `$` prefix
selects a skill; the rest of the prompt describes the task.

## Code quality

```text
$code-quality Review helloWorld.py.
```

```text
$code-quality Review my uncommitted changes.
```

```text
$code-quality Review this project's source for correctness, error handling, and maintainability.
```

```text
$code-quality Review helloWorld.py and suggest meaningful tests. Do not edit files.
```

```text
$code-quality Review my changes, fix confirmed bugs, and run relevant existing checks.
```

Reviews report actionable findings with severity, file and line, impact, and a
suggested fix. Review-only requests leave files unchanged. The skill uses existing
checks when available and reports verification gaps; it does not install tools,
commit, push, or post GitHub reviews on its own.

Instructions: [code-quality/SKILL.md](.agents/skills/code-quality/SKILL.md).

## Discover and create skills

In Codex CLI, run `/skills` or type `$` to select an available skill. In the IDE
extension, type `$` to mention a skill. If a new skill is missing, restart Codex.

```text
$skill-creator Create a repository skill that reviews Python API error handling and reports actionable findings.
```

```text
$skill-creator Update the code-quality skill to check for accidental logging of credentials.
```

Repository skills live in `.agents/skills/<skill-name>/SKILL.md`. Each file begins
with YAML containing `name` and `description`, followed by workflow instructions.
Skills can be selected automatically when their descriptions match a request.

A skill supplies instructions. MCP supplies access to external tools and data.
The local code-quality skill works without GitHub MCP.

Reference: [Official skill documentation](https://learn.chatgpt.com/docs/build-skills).
