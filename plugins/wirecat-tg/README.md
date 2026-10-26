# WireCat for Telegram

Read, search and send messages in your own Telegram account through the tg command line tool.

This plugin holds one skill, `tg-cli`: instructions that teach Claude how to use the `tg` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `tg` is not there to run.
- The `tg` command, installed with `npm install -g @wirecat/tg-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-tg@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-tg --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `tg` commands on your computer, as you. `tg` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the tg documentation](https://wirecat.dev/en/docs/tg) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **Telegram's servers**, with the account you sign in with: to read and send your messages.

What the tool downloads stays in its local store on your computer, until you delete it. Neither the plugin nor the tool sends anything to WireCat. Only WireCat Desktop, a separate app, sends a bug report to WireCat, and only when you choose "Report this".

## Where the skill comes from

The skill is a copy of `skills/tg-cli/SKILL.md` from the latest npm release of `@wirecat/tg-cli`
([source](https://github.com/WireCatLabs/tg-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/tg-cli/issues).

## License

Apache-2.0, the same as `@wirecat/tg-cli`.
