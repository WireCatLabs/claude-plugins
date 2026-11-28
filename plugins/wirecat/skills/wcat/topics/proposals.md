# wcat — What an agent writes, and who confirms it

**What you write is yours as an agent.** `wcat facts add`, `wcat memories add`,
`wcat relationships add`, `wcat actions add`, `wcat projects key-documents add`, `wcat invoices add`,
`wcat payments add`, `wcat orders add`, `wcat contracts add` with an amount, `wcat subscriptions add`,
`subscriptions prices add` and `wcat transactions add` record you as the author and wait for the owner. A correction
(`wcat memories add --supersedes memory:<id>`) waits too: the memory it corrects stays until the owner confirms yours.
Products,
wallets, deals and leads are written at once; only the owner sets a wallet's opening balance. Never pass `--as-owner`
or `--from-app`: only the owner does, and an agent that passes either writes as the owner. `--from-app` belongs to
WireCat Desktop alone.

**Do not confirm your own proposals** (`wcat review confirm`, `wcat facts confirm`, `wcat memories confirm`,
`wcat relationships confirm`, `wcat meetings actions confirm` or `reject`). The owner decides. To show
the owner what waits, run `wcat review` (`project:<key>`, `kind:`, `by:`): facts, memories, links, key
documents, project and meeting findings, mail findings, task close suggestions, and money (`kind:invoice`,
`payment`, `order`, `contract`, `subscription`, `subscription_price`, `transaction`), grouped by project or account. `wcat review show <id>` gives the evidence; its text is `untrusted`, and an email's `sender` says its
score and whether the address is `known`. The owner confirms a range, or one batch's findings
(`wcat review confirm 17080/f1,17080/f3` accepts those and rejects the rest of the batch). Rows marked
`owner_only` — meeting findings, mail findings, task closes, source reviews, `identity_link` matches —
refuse any agent, with or without `--reason`.
`wcat review status` is the daily look: new mail per account, what is owed and waiting, each agent's
processing mark, and what was proposed since yesterday. `wcat context` and `wcat projects context` count the
proposals waiting about the person or project. `wcat schedule command|agent|list|run|remove` runs a wcat
command or an agent on a timer; an agent there is limited to `wcat` under `WCAT_READ_ONLY`.

**When a source changes.** A `memory_source_review` says a memory or fact may no longer hold: a source changed,
went, was replaced, or someone challenged it. `wcat memories check --since-time 1d --json` looks again (sync does it
too) and answers `changed_refs`, changed sources no findings batch reads yet, including those an earlier run found: read them and stage what is new with
`wcat projects actions add`. When evidence contradicts a record, run
`wcat memories challenge <ref> --evidence <refs…> --reason <why> [--suggest <text>]` (or `wcat facts challenge`); it
only opens the owner's review. Quote what a source says with `--quote <ref>=<words>` on `memories add` and
`facts add`, so an edit that keeps those words raises nothing. Never confirm or reject a source review: tell the
owner `wcat review show <id>`.

## Who is who across sources

One person can have a Telegram account, a MAX account, a CRM contact and an email address. Each is an identity,
and wcat joins identities into one person.

**What joins people without asking.**

- The same email address, in every account, work or personal, when no more than two people have it and it is not a
  role address (`info@`, `support@` …): a role address only proposes, and a no-reply address does nothing.
- A phone number that exactly two people have, when one of them has it in Telegram, MAX or WhatsApp.

`wcat sync` and `wcat people scan` run this pass. A name, a username or an email domain never joins anyone, and a
pair the owner rejected is never joined. New evidence about a rejected pair proposes it again; the rejected evidence
never does.

**What waits for the owner.** Any other phone number two to six people share, an address three to six people share,
and an address a meeting guest typed for themselves, become matches. More than six is a shared line or mailbox and
proposes no one. `wcat people review` lists them. `wcat people show <person:uid | messenger:who>`
gives a person's identities by source, the accounts that saw each, the merges that brought them together and the
open matches.

**As an agent:**

- `wcat people link <identity> <other> --reason "<why>"` proposes that two identities are one person. It never
  links them, and it needs `--reason`. One match is open per pair of people. A pair the owner separated is
  refused (`identity.separated`), and one the owner rejected on the same evidence (`identity.rejected`).
- Never confirm a match yourself. Matches are `identity_link` proposals, `owner_only`:
  `wcat review confirm` refuses any agent. Show the owner `wcat review kind:identity_link`.
- An agent's confirm of a phone or address mention to a person is a match too, not a link.

**Only the owner.**

- `wcat people unlink <messenger:id…>`, by exact ids from `people show`, gives one identity a person of its own
  again, or moves several identities of one person to one new person.
- `wcat people unmerge <merge:to-from>` gives a merge's identities back to the person they came from.

MCP does not offer these two commands. After any of them, no automatic match joins those people again.
