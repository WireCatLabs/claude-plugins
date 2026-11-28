# WireCat Files

Search your notes folders, Obsidian vaults and imported PDF and Word files through the files command line tool.

This plugin holds one skill, `files-cli`: instructions that teach Claude how to use the `files` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `files` is not there to run.
- The `files` command, installed with `npm install -g @wirecat/files-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-files@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-files --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about your notes or documents, Claude runs `files` commands on your computer, as you. `files` reads only
the folders and files you choose and keeps what it reads in a local store on your computer. See
[the files documentation](https://wirecat.dev/en/docs/files) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **The AI model provider you choose**, with your own key, when you turn on search by meaning or reading of scanned
  documents.

What the tool reads stays in its local store on your computer, until you delete it. Neither the plugin nor the tool sends anything to WireCat. Only WireCat Desktop, a separate app, sends a bug report to WireCat, and only when you choose "Report this".

## Where the skill comes from

The skill is a copy of `skills/files-cli/SKILL.md` from the latest npm release of `@wirecat/files-cli`
([source](https://github.com/WireCatLabs/files-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/files-cli/issues).

## License

Apache-2.0, the same as `@wirecat/files-cli`.
