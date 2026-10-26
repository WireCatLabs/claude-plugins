# WireCat for Google Drive

Search and read the Google Drive folders you choose, offline, through the drive command line tool.

This plugin holds one skill, `drive-cli`: instructions that teach Claude how to use the `drive` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `drive` is not there to run.
- The `drive` command, installed with `npm install -g @wirecat/drive-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-drive@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-drive --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `drive` commands on your computer, as you. `drive` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the drive documentation](https://wirecat.dev/en/docs/drive) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **Google Drive**, with the Google account you sign in with: to download the folders you choose.

What the tool downloads stays in its local store on your computer, until you delete it. WireCat runs no server that receives your data.

## Where the skill comes from

The skill is a copy of `skills/drive-cli/SKILL.md` from the latest npm release of `@wirecat/drive-cli`
([source](https://github.com/WireCatLabs/drive-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/drive-cli/issues).

## License

Apache-2.0, the same as `@wirecat/drive-cli`.
