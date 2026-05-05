# The Froject Plugins

Official Claude Code plugins by **[The Froject](https://www.thefroject.com)** — a free wizard that generates complete Claude Code workspaces for go-to-market teams. This marketplace ships role-specific bundles of skills, commands, and rules you can drop into any Claude Code workspace.

If you want a complete workspace generated end to end (CLAUDE.md, context files, agents, hooks, settings, the lot), use the wizard at **[thefroject.com](https://www.thefroject.com)**. If you already have a workspace and just want a curated bundle for one role, install a plugin from this repo.

## Install

Add this marketplace to Claude Code:

```
/plugin marketplace add bjorn-ingmanson/thefroject-plugins
```

Then install the plugins you want:

```
/plugin install thefroject-marketing
/plugin install thefroject-sales
/plugin install thefroject-software
```

## Available plugins

| Plugin | Skills | Commands | Rules |
|--------|--------|----------|-------|
| [marketing](./marketing) | 149 | 16 | 10 |
| [sales](./sales) | 100 | 15 | 9 |
| [operations](./operations) | 101 | 10 | 10 |
| [customer-success](./customer-success) | 64 | 11 | 9 |
| [people-culture](./people-culture) | 71 | 6 | 10 |
| [finance](./finance) | 74 | 8 | 9 |
| [software](./software) | 80 | 19 | 16 |
| [data-science](./data-science) | 68 | 21 | 14 |
| [product](./product) | 122 | 13 | 10 |
| [research](./research) | 56 | 5 | 9 |

Totals: 885 skills, 124 commands, 106 rules across all plugins. Each plugin also includes role-specific hooks in `settings.json`.

Many templates are tagged for multiple roles, so the same skill may appear in more than one plugin. The Froject's full library counts each template once — see [thefroject.com/templates](https://www.thefroject.com/templates) for the canonical list.

## What each plugin contains

- **Skills** — specialized capabilities Claude loads on demand when the trigger phrasing matches.
- **Commands** — slash commands for daily tasks (`/morning-brief`, `/draft`, `/research`, ...).
- **Rules** — behavioral guardrails (brand voice, tone, review standards) loaded automatically when matching globs apply.
- **Hooks** — automation triggers (session start, tool use, notifications) wired into `settings.json`.

## How this relates to The Froject wizard

The Froject's wizard at [thefroject.com](https://www.thefroject.com) generates a complete workspace tailored to your role and stack — every file, every path, every frontmatter. These plugins are the same templates packaged for the Claude Code plugin system, so you can install them on top of an existing workspace without going through the wizard. Pick whichever entry point fits.

## Role landing pages

If you want to learn what each plugin covers before installing:

- [Marketing](https://www.thefroject.com/marketing)
- [Sales](https://www.thefroject.com/sales)
- [Customer Success](https://www.thefroject.com/customer-success)
- [People & Culture](https://www.thefroject.com/people-culture)
- [Finance](https://www.thefroject.com/finance)
- [Operations](https://www.thefroject.com/operations)

## Other entry points

- [The Froject](https://www.thefroject.com) — the wizard
- [Workspace audit](https://www.thefroject.com/audit) — score and improve an existing workspace
- [GTM repository](https://www.thefroject.com/gtm-repository) — the full GTM-team workspace generator
- [Discord community](https://discord.gg/3ZhD9gjqxR)

## Updating

These plugins are extracted from The Froject's template library. To regenerate after a template update, run from the wizard repo:

```
npx tsx scripts/extract-all-plugins.ts --output <path-to-this-repo>
```

## License

MIT
