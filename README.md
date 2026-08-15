<div align="center">

# 🔩 dumb-pipe

**Execute the task exactly as requested. Return only the result.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Format: Agent Skills](https://img.shields.io/badge/format-Agent%20Skills-blue)](https://agentskills.io)

</div>

---

## What it does

`dumb-pipe` is an [Agent Skills](https://agentskills.io) skill for literal, narrowly scoped execution.

It performs only the requested task and returns only the requested result - with no explanations, suggestions, follow-up questions, or added scope.

It can also be assigned to a subagent as a bounded execution-only worker.

The full behavior is defined in [`dumb-pipe/SKILL.md`](dumb-pipe/SKILL.md).

## Install

Install the [`dumb-pipe`](dumb-pipe) directory using your harness's skill manager, or copy it into the directory where your agent loads skills.

For GitHub-capable skill managers:

```text
Install the skill from https://github.com/Makon324/dumb-pipe-skill/tree/main/dumb-pipe
```

Invocation syntax depends on the harness. Where slash-style skill invocation is supported:

```text
/dumb-pipe <task>
```

## Examples

### File conversion

```text
/dumb-pipe Take the Word file in the directory and create an LLM-friendly .md file.
```

### Bounded subagent

```text
Spawn a subagent. Use /dumb-pipe to extract the headings from report.docx into headings.md.
```

## Behavior

`dumb-pipe`:

- executes explicit instructions literally and narrowly
- performs only the actions needed to produce the requested result
- does not infer additional goals or improve adjacent material
- resolves concrete references from observable context when unambiguous
- does not explain, summarize, suggest alternatives, or offer next steps
- returns only the requested output
- remains subject to higher-priority instructions, safety rules, and authorization requirements

## Compatibility

Works with agents and harnesses that support the [Agent Skills](https://agentskills.io) format.

## Directory layout

```text
dumb-pipe/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## Contributing

Keep changes minimal and consistent with the skill's execution-only purpose. Include a concrete example showing why a behavioral change is needed.

For eval cases, use realistic prompts and describe expected behavior in neutral, specific, verifiable terms. Avoid promotional claims, superlatives, and vague quality statements.

## License

[MIT](LICENSE)
