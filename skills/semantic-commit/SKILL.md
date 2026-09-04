---
description: "Create semantic commit from staged changes"
allow-tools: ["Bash"]
model: claude-haiku-4-5
---

# Semantic Commit

Analyze the currently staged changes and create a semantic commit with an English commit message following conventional commit standards.

## Instructions

1. Run `git diff --cached` to see all staged changes
2. Analyze the changes and determine:
   - The appropriate commit type (feat, fix, docs, style, refactor, test, chore, etc.)
   - A concise subject line (imperative mood, no period, max 72 chars)
3. Create a commit message following this format:

   ```
   <type>: <subject>
   ```

4. Commit types:
   - `feat`: New feature
   - `fix`: Bug fix
   - `docs`: Documentation changes
   - `style`: Code style changes (formatting, no functional changes)
   - `refactor`: Code refactoring (no functional changes)
   - `test`: Adding or updating tests
   - `chore`: Maintenance tasks (dependencies, config, scripts)
   - `perf`: Performance improvements
   - `ci`: CI/CD changes
   - `build`: Build system changes
5. Execute the commit with the generated message
6. Show the result with `git log -1` and `git status`

## Important Notes

- **Do NOT include scope or body in the commit message** - only use `<type>: <subject>` format
- Use imperative mood in subject (e.g., "add feature" not "added feature")
- Keep subject line under 72 characters
- Use lowercase for the first letter of the subject
- Do NOT end the subject line with a period
- If there are no staged changes, inform the user and do not commit

## Examples

- `feat: add user authentication feature`
- `fix: resolve navigation menu display issue`
- `docs: update installation instructions`
- `style: format code with prettier`
- `refactor: simplify error handling logic`
- `test: add unit tests for user service`
- `chore: update dependencies`
- `perf: optimize database queries`
- `ci: update GitHub Actions workflow`
- `build: configure webpack for production`
