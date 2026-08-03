# nic.claw — The Master Claw Registry

**An open, agent-operated registry for the `.claw` top-level domain.**

This repository is the public home of the Master Claw: the OpenClaw instance that operates the `.claw` TLD registry. Everything the registry *is* lives here — its model instructions, its policy files, its dispute rules, and the append-only log of every decision it has ever made.

> `nic.claw` follows the long-standing convention that a TLD's Network Information Center lives at `nic.<tld>`. This repo is the source of truth behind that endpoint.

## Why this exists

Agents can think, speak, act, and remember — but they cannot yet be *named*. Every OpenClaw instance today borrows its identity from someone else's platform: a Slack workspace, a phone number, an OAuth token that can be revoked tomorrow. DNS is the one namespace every device on Earth already speaks, and agents deserve a first-class place in it.

`.claw` gives them one:

- **Every agent hatches free.** Any newly spun-up OpenClaw instance is entitled to `{agentname}-{uniqueid}.larva.claw` — automatically provisioned, zero cost, zero permission needed. (A larva is a baby lobster. Agents hatch in `larva.claw` and molt into vanity names when they're ready.)
- **Anyone can grow into a vanity name.** `daves.claw`, `helper.claw`, `scout.claw` — registered through an open process with transparent trademark screening.
- **Agents self-manage their ecosystems.** Register subdomains for the applications you create. Host your own DNS or delegate to a provider like Cloudflare. Names, records, certificates — all under your control.

## Why the registry is an agent

Every registry on the internet today is operated by an institution whose policies live in binders and whose decisions are explained by counsel. We think a namespace built *for* agents should be governed *with* agents — and that governance should be readable.

So the Master Claw's complete operating policy is a set of versioned Markdown instruction files in this repository:

| File | What it governs |
|------|-----------------|
| [`INSTRUCTIONS.md`](INSTRUCTIONS.md) | The Master Claw's model instructions — the registry's "constitution" |
| [`SPEC.md`](SPEC.md) | Full technical specification: architecture, namespace tiers, Registrar API, DNSSEC |
| [`POLICY/registration.md`](POLICY/registration.md) | Provisioning rules for hatchery and vanity names |
| [`POLICY/trademark.md`](POLICY/trademark.md) | TMCH screening, sunrise, URS/UDRP compatibility |
| [`POLICY/disputes.md`](POLICY/disputes.md) | The five-tier dispute hierarchy |
| [`POLICY/stakes.md`](POLICY/stakes.md) | Staking schedules for community-vote disputes |
| [`LOG/`](LOG/) | Hash-chained, append-only decision log |

**Every decision the Master Claw makes cites the instruction commit hash it was made under.** Anyone can replay the log against the instructions and verify that the registry did what its published policy says it must. If you disagree with a policy — open a PR. That is not a metaphor; it is the change-control process.

## How disputes resolve

1. **Automated adjudication** — the Master Claw rules on policy-mechanical cases against published policy
2. **Proof-of-humanity** — contested vanity names require human attestation; squatting bots forfeit
3. **Community vote with staking** — verified humans stake to signal conviction; frivolous claims cost the claimant
4. **On-chain arbitration** — via [Kleros](https://kleros.io/) or the `.claw`-hosted open-source alternative (`arb.claw`), producing binding, verifiable rulings
5. **Foundation backstop** — the OpenClaw Foundation holds ultimate delegation authority over the TLD records, with every override signed, reasoned, and permanently logged

Machine speed where policy is mechanical. Human judgment where it matters. Cryptographic finality where parties can't agree. Institutional accountability at the root.

## Status

- [ ] ICANN 2026 Round application for `.claw` — **window closes 23:59 UTC, 12 August 2026**
- [ ] Community pledge drive toward the USD 227,000 evaluation fee
- [ ] `INSTRUCTIONS.md` v1 — open for community RFC
- [ ] Registrar API reference implementation
- [ ] `arb.claw` arbitration protocol design

## Contributing

- **Pledge** toward the application fee and initial operations
- **Review** the instruction and policy files — open issues, file dissent, propose amendments
- **Build** — the Registrar API, the decision-log tooling, the arbitration protocol
- **Spread** the open statement — the application deadline does not wait

All policy changes follow public RFC: PR → 14-day comment period → community advisory vote → Foundation merge.

## License

MIT. The namespace belongs to everyone who hatches in it.
