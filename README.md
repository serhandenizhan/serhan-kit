# serhan-kit

A Claude Code plugin with an orchestrated delivery flow. Run `/serhan <task>` (`/serhan:serhan` when installed as a plugin): the session model plans, owns design, delegates implementation to tiered worker subagents (at most 3 in parallel) and reviews what they return.

Derived from [johnnyvizz/claude-kit](https://github.com/johnnyvizz/claude-kit) (`savvy-flow`, MIT). Renamed, retiered for lower usage cost, and with a parallelism cap added.

## Tiers

Start from the lowest tier that can do the job; escalate one tier only if the worker comes back blocked.

| Agent | Model / effort | For |
| --- | --- | --- |
| `serhan-quick` | Sonnet / low | mechanical edits, builds, tests |
| `serhan-standard` | Sonnet / medium | standard feature work |
| `serhan-precise` | Sonnet / high | delicate, well-understood changes |
| `serhan-investigator` | Opus / medium | unfamiliar code, root-cause hunting |
| `serhan-expert` | Opus / high | reserve tier: hardest logic and bugs |

Change a tier's model in `plugins/serhan/agents/<agent>.md` (`model:` and `effort:`) and keep the table in `plugins/serhan/skills/serhan/SKILL.md` section 3 in sync.

## Install

```
/plugin marketplace add serhandenizhan/serhan-kit
/plugin install serhan@serhan-kit
```

Restart the session afterwards.

Optional: `/plugin install serhan-progress@serhan-kit` adds a progress bar above the prompt and a live agents panel (`/agents-info`) that the skill drives. Without it the skill's progress calls are skipped. Do not install it together with the original `savvy-progress`.

## License

MIT, see [LICENSE](LICENSE).
