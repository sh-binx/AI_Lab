# Loading project context within a bounded hook output

Measured October 16, 2026, on one active project.

Long-running agent work needs access to earlier decisions without copying the whole project knowledge base into every session. The current implementation loads a compact index and recent log headings at session start. The agent then opens the pages relevant to the task.

## Observed result

A read-only run of the existing context generator in its Codex mode reported:

```text
codex: 4703 chars · est 1676 tokens · budget 2300 tok
```

This is one snapshot of the current project's generated context. The token count is the script's estimate, not tokenizer output or billed usage. It falls below the configured 2,300-token estimate budget for that run. The implementation is maintained privately; this note is not a runnable package.

## Design choices

- Keep decisions and their history in Markdown pages.
- Load an index and recent headings first; read full pages when the task needs them.
- Keep the current state ahead of older decisions so a resumed agent does not start from a superseded value.
- Use change notices to point an active session at documents edited by another session.

The [public harness case study](https://undefined-labs.dev/process/agent-harness) provides the broader context.

## What the measurement does not establish

A small payload does not prove the agent read it, selected the right page, remembered a constraint, or completed the task correctly. This check did not compare task accuracy before and after compression. The next useful measurement is retrieval correctness on representative tasks, alongside actual task outcomes and context size.
