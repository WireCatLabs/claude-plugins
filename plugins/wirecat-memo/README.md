# WireCat Memo

Find what you know about a person or a project across your messages, mail and notes through the memo command line tool.

This plugin holds one skill, `cli-memo`: instructions that teach Claude how to use the `memo` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `memo` is not there to run.
- The `memo` command, installed with `npm install -g @wirecat/cli-memo`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-memo@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-memo --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `memo` commands on your computer, as you. `memo` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the memo documentation](https://wirecat.dev/en/docs/memo) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **Gmail**, with the Google account you connect: to sync your mail.
- memo also reads what the other WireCat tools already stored on your computer (Telegram, MAX, WhatsApp, Zoom, Drive).

What the tool downloads stays in its local store on your computer, until you delete it. WireCat runs no server that receives your data.

## Where the skill comes from

The skill is a copy of `skills/cli-memo/SKILL.md` from the latest npm release of `@wirecat/cli-memo`
([source](https://github.com/WireCatLabs/cli-memo)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/cli-memo/issues).

## License

Apache-2.0, the same as `@wirecat/cli-memo`.
