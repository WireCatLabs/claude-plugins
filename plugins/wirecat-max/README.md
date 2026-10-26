# WireCat for MAX

Read, search and send messages in your own MAX Messenger account and from your MAX bots through the max command line tool.

This plugin holds one skill, `max-cli`: instructions that teach Claude how to use the `max` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `max` is not there to run.
- The `max` command, installed with `npm install -g @wirecat/max-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-max@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-max --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `max` commands on your computer, as you. `max` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the max documentation](https://wirecat.dev/en/docs/max) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where the skill comes from

The skill is a copy of `skills/max-cli/SKILL.md` from the latest npm release of `@wirecat/max-cli`
([source](https://github.com/WireCatLabs/max-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/max-cli/issues).

## License

Apache-2.0, the same as `@wirecat/max-cli`.
