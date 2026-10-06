# serhan-kit

Claude Code plugin marketplace. Two plugins: `plugins/serhan` (skill `serhan` + 5 tier agents) and `plugins/serhan-progress` (UI mod: progress bar + agents panel).

- Derived from johnnyvizz/claude-kit (MIT). Keep both copyright lines in LICENSE.
- Tier model/effort live in `plugins/serhan/agents/*.md` frontmatter; keep the table in `plugins/serhan/skills/serhan/SKILL.md` section 3 and README.md in sync.
- Parallelism cap is `max_parallel: 3` in SKILL.md section 4.
- Tier names appear in 3 places that must stay in sync: agent files, SKILL.md section 3, and `TIER_COLOR`/`TIER_MODEL`/`COSTUMES`/tool enum in `plugins/serhan-progress/hooks/register.tsx`. The mod only recognizes agents whose type starts with `serhan-`.
- `mcp__serhan-progress__*` tool names derive from the mod's plugin name; renaming the plugin means updating SKILL.md and the agent files.
- The mod conflicts with the original `savvy-progress` (both register `/agents-info`); install only one.
- Validate: `claude plugin validate .` and `claude plugin validate plugins/serhan`, `claude plugin validate plugins/serhan-progress`.
- Files, code and code comments in English (user override of the default Turkish-comments rule). Commit only with user confirmation; never push without being asked.
