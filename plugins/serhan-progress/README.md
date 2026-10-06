# serhan-progress

A Claude Code mod: a progress bar above the prompt and a live panel of subagents. Made for the `serhan` skill, and useful with any subagents. Derived from johnnyvizz/claude-kit (`savvy-progress`, MIT).

- **Progress bar**: the flow's title, phase, accepted tasks out of planned, and a button with the crew size that opens the panel. It appears once something reports progress or a `serhan-*` worker starts.
- **Agents panel** (`/agents-info` toggles it): running, finished and planned subagents with model, effort, task progress, context, estimated cost and time. Each tier has its own costume: expert (astronaut), investigator (detective), precise (engineer), standard (chef), quick (racer).

## Tools it adds

- `mcp__serhan-progress__progress`: the orchestrator reports the plan, phase and accepted tasks.
- `mcp__serhan-progress__step`: a worker reports its own steps (`done`, `total`, `note`).

Cost is a rough estimate from token counts and a built-in per-model price table (`PRICES` in `hooks/register.tsx`), not a bill.

## Settings

`language`: `auto` (default), `en`, `ru` or `tr`. `auto` follows Claude Code's `language` setting, then the system locale, and falls back to English.

Do not run it together with the original `savvy-progress` mod: both register `/agents-info`.
