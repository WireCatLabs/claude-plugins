# WireCat plugins for Claude Code

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) with one plugin per WireCat
tool. Each plugin holds only the tool's skill: instructions that teach Claude to use the tool's command on your
computer. No plugin holds code, an MCP server or hooks; you install the command line tool itself from npm.

## Install

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-tg@wirecat
```

| Plugin | Tool | Command |
| --- | --- | --- |
| `wirecat-tg` | [Telegram](https://wirecat.dev/en/docs/tg) | `tg` |
| `wirecat-max` | [MAX](https://wirecat.dev/en/docs/max) | `max` |
| `wirecat-whatsapp` | [WhatsApp](https://wirecat.dev/en/docs/wa) | `wa` |
| `wirecat-zoom` | [Zoom](https://wirecat.dev/en/docs/zoom) | `zm` |
| `wirecat-drive` | [Google Drive](https://wirecat.dev/en/docs/drive) | `drive` |
| `wirecat-memo` | [Memo](https://wirecat.dev/en/docs/memo) | `memo` |

## Where the skills come from

Each tool's repository owns its skill. `bin/sync-skills` copies `skills/<name>/` from the latest npm release of
the package named in the plugin's `plugin.json` (`metadata.source`), and sets the plugin's `version` to that release
when the skill changed. The [Sync skills](.github/workflows/sync.yml) workflow runs it daily and opens a pull
request. Don't edit a `SKILL.md` here; change it in the tool's repository and release.

`bin/validate` runs `claude plugin validate --strict` on the marketplace and, with `--profile directory`, on each
plugin. CI runs it on every push and pull request.

## License

Apache-2.0, the same as the tools.
