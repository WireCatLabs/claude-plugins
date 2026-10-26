# WireCat for Zoom

Archive your Zoom cloud recordings and search their transcripts and summaries through the zm command line tool.

This plugin holds one skill, `zoom-cli`: instructions that teach Claude how to use the `zm` command. It holds no
code, no MCP server and no hooks. It sends nothing anywhere by itself.

## What you need

- [Claude Code](https://code.claude.com/docs), or another Claude app that can run commands on your own computer.
  In claude.ai chat the skill loads, but `zm` is not there to run.
- The `zm` command, installed with `npm install -g @wirecat/zoom-cli`. The [installation guide](https://wirecat.dev/en/docs/installation)
  covers the other ways to install it.

## Install

In your shell:

```sh
claude plugin marketplace add WireCatLabs/claude-plugins
claude plugin install wirecat-zoom@wirecat
```

Or in a Claude Code session: `/plugin install wirecat-zoom --marketplace WireCatLabs/claude-plugins`.

## What the skill makes Claude do

When you ask about the things above, Claude runs `zm` commands on your computer, as you. `zm` keeps its data in
a local store on your computer and talks only to the services you connect it to, with the accounts you sign in with. See [the zm documentation](https://wirecat.dev/en/docs/zoom) and the [privacy policy](https://wirecat.dev/en/privacy).

## Where the skill comes from

The skill is a copy of `skills/zoom-cli/SKILL.md` from the latest npm release of `@wirecat/zoom-cli`
([source](https://github.com/WireCatLabs/zoom-cli)). The plugin's `version` is that release. Report problems with the
skill in [that repository's issues](https://github.com/WireCatLabs/zoom-cli/issues).

## License

Apache-2.0, the same as `@wirecat/zoom-cli`.
