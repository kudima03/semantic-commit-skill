# semantic-commit-skill

A Claude Code plugin that analyzes staged changes and creates a semantic commit message following conventional commit standards, as a skill and slash command.

## Contents

| Type | Name | Description |
|---|---|---|
| Skill | `semantic-commit` | Auto-triggered workflow: analyze staged changes, determine commit type, create the commit |
| Command | `/semantic-commit` | Explicitly kick off the semantic commit workflow |

## How it works

The skill runs `git diff --cached`, classifies the change as one of the conventional commit types (`feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `perf`, `ci`, `build`), and commits with a message in the form:

```
<type>: <subject>
```

No scope or body is included. If nothing is staged, the skill reports that and does not commit.

## Prerequisites

- [Claude Code](https://claude.ai/code)
- `git` with staged changes in the target repo

## License

MIT
