# WireCat

Find what you know about a person or a project across your messages, mail and notes through the wcat command line tool.

This plugin holds one skill, `wcat`: instructions that teach Claude how to use the `wcat` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `wcat` is not there to run.
- The `wcat` command, installed with `npm install -g @wirecat/wirecat`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat@wirecat
```

Or in a Claude Code session: `/plugin install wirecat --marketplace WireCatLabs/claude-plugins`.

Your notes folders and Obsidian vaults are read by the files tool, which has its own plugin, `wirecat-files`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `wcat` commands on your computer, as you. `wcat` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the wcat documentation](https://wirecat.dev/en/docs/wcat) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **The AI model provider you choose**, with your own key, when you turn on search by meaning.
- wcat also reads what the other WireCat tools already stored on your computer (Telegram, MAX, WhatsApp, mail, Zoom,
  Drive, your notes).

What the tool downloads stays in its local store on your computer, until you delete it. Neither the plugin nor the tool sends anything to WireCat. Only WireCat Desktop, a separate app, sends a bug report to WireCat, and only when you choose "Report this".

## Where the skill comes from

The skill is a copy of `skills/wcat/SKILL.md` from the latest npm release of `@wirecat/wirecat`
([source](https://github.com/WireCatLabs/wirecat)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/wirecat/issues).

## License

Apache-2.0, the same as `@wirecat/wirecat`.
