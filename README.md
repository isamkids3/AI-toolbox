# Agent Toolbox

General-purpose rules and templates that make any AI coding agent (CodeFuse, Codex, Cursor,
Claude Code, Copilot, Gemini…) work in a disciplined way on any project:
**understand → plan → small step → verify → record.**

## Use it
From the root of your project (new or existing):
```bash
git clone https://github.com/isamkids3/AI-toolbox .toolbox
cp .toolbox/AGENTS.md AGENTS.md
cp -n .toolbox/AGENTS.md agents.md 2>/dev/null   # some agents read lowercase; skipped on macOS
cp .toolbox/AGENTS.md CLAUDE.md                   # Claude Code reads CLAUDE.md
cp -n .toolbox/templates/*.md .
echo ".toolbox/" >> .gitignore
```
Then ask the agent to fill `PLAN.md` (see `prompts/PROMPTS.md`). If you skip the copy step,
just tell the agent: "Follow .toolbox/AGENTS.md".

## Contents
```
AGENTS.md              the rules (copied to the project root)
templates/
  PLAN.md              goal, requirements, approach, structure, milestones
  TODO.md              human-owned task board
  TEST_REPORT.md       test results mapped to requirements
prompts/PROMPTS.md     reusable prompts for each phase
```

## Principles
1. Plan before code.
2. One small, scoped step at a time.
3. Tests prove it, or it isn't done.
4. Docs only claim what exists.
5. Freeze features early enough to finish docs and verification.
