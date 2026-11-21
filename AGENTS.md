# Agent rules

These rules apply to any project, language or framework. Respond in English. Be concise.

## 1. Workflow: understand → plan → small step → verify → record
1. **Understand.** Read `PLAN.md` and `TODO.md` before every task. In an existing codebase,
   read the relevant code first and follow its conventions, structure and tooling.
2. **Plan.** If `PLAN.md` or `TODO.md` is missing, create them from the templates
   (`.toolbox/templates/` if present) before writing code. No code until the plan exists.
3. **One step at a time.** Work on ONE `TODO.md` item. Don't add features, files or
   dependencies that item doesn't need. If something else needs doing, add it to `TODO.md`.
4. **Verify.** After every change, run the tests (and the build/linter if the project has one)
   and report the real output.
5. **Record.** Tick the item in `TODO.md` only after its tests pass. Suggest a short commit
   message (`feat: …`, `fix: …`, `test: …`, `docs: …`).
6. **Version control.** If the project isn't a git repo, run `git init` and add a `.gitignore` for the
   language (dependencies, build output, local databases, caches, `.toolbox/`) before the first
   commit. Commit after each TODO item.
7. **Checkpoint.** After finishing each TODO item (tests passing, item ticked), stop and give
   a 2-line summary before starting the next one.

## 2. Code
- Prefer the simplest design that meets the requirement. Small functions, clear module boundaries.
- Keep business logic separate from I/O layers (HTTP handlers, CLI, UI, database access).
- Match the existing style. For a new project, use the language's standard tooling and layout.
- Handle errors explicitly; don't silently swallow them.
- Config and secrets come from environment variables or config files, never hardcoded.

## 3. Tests
- Every feature gets automated tests in the project's test framework (or the language's
  standard one): the happy path AND failure/edge cases.
- Never claim something works unless a test or a command you ran proves it.
- Never delete, skip or weaken a failing test to make it pass. Fix the code, or explain why
  the test is wrong.

## 4. Security
- Use well-known libraries for crypto, auth and parsing. Never write custom crypto.
- Hash passwords with a slow hash (argon2/bcrypt/scrypt). Never log secrets or personal data.
- Validate all external input. Use parameterised queries / an ORM. Least privilege everywhere.
- Return generic error messages to users; keep details in logs.

## 5. Dependencies
- Only add a dependency when it clearly saves effort. Record every one in the project's
  manifest with a pinned version (requirements.txt, package.json + lockfile, go.mod, pom.xml…).

## 6. Docs
- `README.md`: what it is, how to set up and run, how to test, architecture, key decisions,
  security and performance notes, known limitations.
- `TEST_REPORT.md` (when required): fill it from the template using real test output.
- Docs describe only what exists and is tested. Mark anything unfinished as partial or not done.

## 7. When unsure
- If the request is ambiguous, state your assumption in one line and continue.
- If blocked or a decision is hard to undo, stop and ask.
