# ssi-site Agent Instructions
SSI public site checkout.
## Operating rules

- Inspect current branch, dirty status, relevant files, and issue/PR context before editing.
- When asked for implementation, inspect just enough to target the work, then edit, run, verify, and report. Do not replace execution with another broad plan.
- When asked for planning, produce a concrete plan with acceptance criteria, evidence gates, risks, and the next executable action.
- When asked for a prompt, produce a self-contained prompt artifact that terminates in execution, not another prompt-generation cycle.
- If corrected angrily: state the specific failure in one sentence, state the corrected behavior in one sentence, then execute or produce the corrected artifact.
- Preserve scorecards, ledgers, blockers, and acceptance criteria; compress known context instead of deleting it.
- Keep changes focused. Existing code is not a toilet: do not refactor unrelated code or rewrite adjacent systems because they look messy.
- For small UI/copy/layout/progress/formatting/user-reported defect fixes, default to small-patch mode: max 80 product LOC, max 3 product files, no new production files, no new abstractions, and no new dependencies unless approved.
- Do not edit generated, build, vendor, dist, cache, model, audio, local-secret, or ignored runtime-output files unless the task explicitly targets them.
- Do not expose secrets, private prompts, raw transcripts, raw audio, raw logs, private JSON, screenshots, casts, local paths, or credentials.
- Claims require command output, artifact paths, metrics, screenshots/snapshots, or explicit blockers.
- Compile/tests are evidence for compile/test behavior only; runtime, UI, package, privacy, and release claims need matching evidence.
- Do not stage, commit, push, open PRs, or change remotes unless the user explicitly asks.

## Local `.plan` logging contract

- `.plan/` is local-only and must stay ignored by tracked repo policy.
- Preserve `.plan/CURRENT.plan.md` as the current local operating log for active agent work.
- Keep `.plan/daily/` for daily summaries and `.plan/sweeps/` for recurring audit or automation outputs.
- Use `.plan/GOAL.md` only when this repo has durable project-level planning work or an active long-running goal.
- Freshness rule: `.plan/CURRENT.plan.md` is fresh when its mtime is within the last 7 calendar days; older than 7 calendar days is stale unless this guide declares an explicit exception.
- Automation may create or refresh local `.plan` files and may update tracked policy files that define this contract for active repos.
- Do not print raw `.plan` contents in public/user-facing output; report paths, sizes, counts, and status summaries instead.

## Backlog and planning truth

- Prefer the repo's declared backlog or plan anchors when present.
- If no repo-local backlog anchor exists, treat the current user request and open issue/PR context as the active planning source.
- Do not invent missing backlog files just to satisfy a checklist.

## Completion expectations

- Before handoff, compare changed files and `git diff --stat` to the exact request.
- If scope expands beyond logging/policy or the requested implementation slice, stop and report `SCOPE EXPLOSION`.
- Report commands run, pass/fail status, skipped evidence, blockers, changed files, and next executable action.
## Site boundaries

- Treat this as a public-facing site repo. Do not publish private prompts, `.plan` content, review receipts, local paths, screenshots/casts, secrets, or internal planning artifacts.
- Keep site content/runtime behavior unchanged unless the task explicitly asks for a site change.
- Verify any public-facing copy, build, deploy, DNS, or hosting claim with the matching command or platform evidence.
- Deployment, hosting, and domain changes require explicit user approval.
