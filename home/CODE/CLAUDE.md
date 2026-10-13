# CODE Directory Conventions

Loaded for every project under `~/CODE`, stacked with the global `~/.claude/CLAUDE.md`
and the project's own `CLAUDE.md`/`AGENTS.md`. Only cross-project rules belong here;
language, toolchain, and build commands live in the project file.

## Commits

- 50 char subject max, imperative mood ("Add feature" not "Added feature")
- No "Co-Authored-By" lines
- No conventional commit prefixes unless the project uses them
- Commit the minimum necessary; do not bundle unrelated changes
- Feature branches off `main`; rebase rather than merge; never force push `main`
- Delete merged branches locally

## Pull Requests

- Short title (<70 chars), details in the body
- `gh pr create --body-file` for multiline bodies (preserves newlines)
- Include a "Manual testing" checklist
- No time estimates

## Scope of Changes

- Fix what's broken; do not refactor adjacent code
- No comments or docstrings on unchanged code
- No style "improvements" in unrelated areas

## Testing

- No mocks unless explicitly requested
- Deterministic: no sleeps, no real network calls
- Prefer integration tests for business logic; test the public interface

## Error Handling

- Never swallow errors (empty catch blocks, bare `rescue`, `|| true` without a reason)
- Log or rethrow, not both
- Include context in error messages

## Secrets

- Never commit secrets, API keys, or credentials; use `op` or environment variables
- Check for accidental secret commits before pushing
