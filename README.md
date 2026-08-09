# Guardrails Fiscal (`grf`)

A focused BMad module for tax, accounting operations, grants, incentives, and live fiscal updates. It checks requirements, deadlines, eligible expenses, and reporting against primary sources.

This is a focused BMad module in the [Guardrails](https://github.com/mlarese/bmad-module-guardrails)
bundle. It keeps the same behavior and shared memory while installing only the figures and
workflows for the fiscal area.

> **Generated.** This repository is produced by `tools/build_modules.py` in the
> [bmad-module-guardrails](https://github.com/mlarese/bmad-module-guardrails) repository.
> Make changes there and regenerate; local changes here will be overwritten.

## Agents

| Agent | Role | Skill | Focus |
| ----- | ---- | ----- | ----- |
| 🧾 Marta | Tax and Incentives Specialist | `grl-agent-fiscal` | Taxes, VAT, grants, incentives, tax credits, and reporting. |

## Skills and workflows

| Skill | Purpose |
| ----- | ------- |
| `grf-profile` | Project profile | Collects the project context shared by every installed figure. |
| `grf-board` | Multidisciplinary review | Convenes the relevant figures on one artifact and returns a review summary or release verdict. |
| `grl-fiscal-updates` | Live fiscal updates | Searches primary sources for tax rules, circulars, grants, incentives, amendments, and deadlines in a defined period. |
| `grl-automation` | Controlled automation | Routes work from read-only checks through dry-run to observable execution, with explicit approvals and rollback. |

## Installation

```
bmad install grf
```

As a first step, run `grf-profile`. It collects the project profile — sector, data,
market, stack, and criticality — so each figure can calibrate its review. Without a profile,
the default remains `normal` and the figures start without context.

## Shared memory

The profile lives in `{project-root}/_bmad/memory/grl-shared/project-profile.md`, together
with `decisions.md` and `accepted-risks.md`. All Guardrails modules use the same path, so two
installed modules still share one profile.

## Using it with the bundle

This module installs skills with **the same names** as the `grl` bundle — `grl-agent-fiscal`
is identical in both. Do not install the full bundle and thematic modules in the same project:
choose the complete bundle, or only the thematic modules you need.

## License

MIT.
