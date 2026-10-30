# WireCat for Google Calendar

Read, search and change your Google Calendar events, offline, through the gcal command line tool.

This plugin holds one skill, `gcal-cli`: instructions that teach Claude how to use the `gcal` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `gcal` is not there to run.
- The `gcal` command, installed with `npm install -g @wirecat/gcal-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-gcal@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-gcal --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `gcal` commands on your computer, as you. `gcal` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the gcal documentation](https://wirecat.dev/en/docs/gcal) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where your data goes

The plugin itself sends nothing. When Claude runs the tool, the tool talks only to:

- **Google Calendar**, with the Google account you sign in with: to download the calendars you choose, and to create,
  change or delete an event or answer an invitation when you ask.

What the tool downloads stays in its local store on your computer, until you delete it. Neither the plugin nor the tool sends anything to WireCat. Only WireCat Desktop, a separate app, sends a bug report to WireCat, and only when you choose "Report this".

## Where the skill comes from

The skill is a copy of `skills/gcal-cli/SKILL.md` from the latest npm release of `@wirecat/gcal-cli`
([source](https://github.com/WireCatLabs/gcal-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/gcal-cli/issues).

## License

Apache-2.0, the same as `@wirecat/gcal-cli`.
