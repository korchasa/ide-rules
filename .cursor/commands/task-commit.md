# Commit Workflow

## Overview
Guided flow to prepare, commit, and publish changes following Conventional Commits (strict) and repository rules.

## Steps
1. **Pre-flight checks**
   - Run `./run check` if project wasn’t checked since last modification
   - Import and plan documentation update steps from `@task-update-docs.md`

2. **Change review**
   - Study all changes since the last commit (use `GIT_PAGER=cat`)
   - Ensure package updates (add/update) are in a separate commit

3. **Commit creation**
   - Compose message per Conventional Commits 1.0.0 (Strict Profile)
   - Verify type, scope, header length, body wrapping, and footers

4. **Publish**
   - Push the commit to GitHub
   - If the current branch is not the `main`: Create a pull request via `gh pr create` and share PR link to user

## Checklist
- [ ] Project checked with `./run check`
- [ ] Docs update steps planned (from `@task-update-docs.mdc`)
- [ ] Changes reviewed using `GIT_PAGER=cat`
- [ ] Dependency changes isolated in dedicated commit
- [ ] Commit complies with Conventional Commits (strict)
- [ ] PR created and link shared (if the current branch is not the `main`)

## Conventional Commits (Strict) Quick Reference
- Structure: `<type>(<scope>)!: <description>`; body and footers separated by blank lines
- Allowed types: `feat` `fix` `perf` `refactor` `docs` `style` `test` `build` `ci` `chore` `revert` `prompts`
- Header ≤100 chars; body lines ≤72; UTF-8; LF; no trailing spaces
- Breaking: `!` in header or `BREAKING CHANGE:` footer (with migration notes)
- Footers: `Token: Value` (`Closes`/`Fixes`/`Refs`/`Co-authored-by`/`Signed-off-by`/`Reviewed-by`/`BREAKING CHANGE`/`X-*`)
- `revert` must include `Reverts: <sha>` in body
