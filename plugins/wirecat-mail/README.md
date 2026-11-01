# WireCat for Mail

Sync your mailbox over IMAP into a local store, read-only, through the mail command line tool.

This plugin holds one skill, `mail-cli`: instructions that teach Claude how to use the `mail` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `mail` is not there to run.
- The `mail` command, installed with `npm install -g @wirecat/mail-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-mail@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-mail --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `mail` commands on your computer, as you. `mail` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the mail documentation](https://github.com/WireCatLabs/mail-cli#readme) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **Your mail provider's IMAP server**, with the account you add and its app password, which stays in your
  computer's keyring: to read the folders and messages you sync. It never sends, moves or deletes mail.

What the tool downloads stays in its local store on your computer, until you delete it. Neither the plugin nor the tool sends anything to WireCat. Only WireCat Desktop, a separate app, sends a bug report to WireCat, and only when you choose "Report this".

## Where the skill comes from

The skill is a copy of `skills/mail-cli/SKILL.md` from the latest npm release of `@wirecat/mail-cli`
([source](https://github.com/WireCatLabs/mail-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/mail-cli/issues).

## License

Apache-2.0, the same as `@wirecat/mail-cli`.
