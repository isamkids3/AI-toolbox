# Prompt snippets

Fill in the `<…>` and paste. They work with any agent, any language.

## Plan
```
Read the brief below. Don't write code yet.
Fill PLAN.md: must-haves vs nice-to-haves, approach with one-line reasons, structure,
interfaces, data, risks. Keep the design as simple as possible.
Then fill TODO.md with one item per must-have, in build order.

BRIEF:
<paste brief or task>
```

## Understand an existing codebase
```
Before changing anything: summarise this codebase's structure, stack, conventions, and how to
build, run and test it. List the files relevant to <task>. Don't edit yet.
```

## Skeleton
```
Set up the project skeleton from the Structure section of PLAN.md, using the language's standard
tooling. Include the test setup and one passing test. Record dependencies with pinned versions.
Run the tests and show the output.
```

## Build one item
```
Implement TODO item: <item>.
Scope: only <files/modules>. Constraints: <rules that matter>.
Write tests for: <happy path>, <failure case>, <edge case>.
Run the tests, show the output, then tick the item in TODO.md.
```

## Fix a failure
```
This fails: <paste output>.
Find the root cause and fix the code, not the test. Explain the cause in one sentence. Re-run the tests.
```

## Review
```
Review the code against AGENTS.md and PLAN.md. List, ranked by severity (don't fix yet):
bugs, security issues, missing validation, missing tests, logic in the wrong layer,
unpinned dependencies, hardcoded secrets.
```

## Docs
```
Feature freeze. Write README.md using only what exists and passes tests; mark anything
unfinished as partial/not done. Run the full test suite and fill TEST_REPORT.md from the real output.
```

## Final check
```
From a clean environment, install dependencies, start the app and run all tests.
Report anything missing or failing.
```
