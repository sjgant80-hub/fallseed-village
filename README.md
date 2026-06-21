# FallSeed · Village

> **The level-4 seed.** A sovereign single-HTML PWA for institution-tier governance. 5 institution presets: Village · Guild · DAO · Housing-Coop · Parish.

**Live:** https://sjgant80-hub.github.io/fallseed-village/

## What this is

`fallseed-village` is one HTML file. Multi-actor governance via **signed JSON bundles** — each member generates an Ed25519 keypair locally, signs their proposals and votes, exports their state as a bundle, and shares it. Other members import bundles; signatures are verified; deterministic merge resolves order. No server. No P2P required.

When Socket VIII (live P2P mesh substrate) lands, the same SEED schema runs over a live mesh with no code change — bundle events just flow continuously instead of in batches.

## Institution presets

| Preset | Use | Voting model |
|---|---|---|
| ◉ Village | General intentional community | Equal vote · 2/3 admit · 3/4 charter |
| ◇ Guild | Craft / professional association | Tiered (apprentice/journeyman/master) · masters set standards |
| ◈ DAO | Open-source / shared infrastructure | Weighted by contribution · multi-sig treasury |
| ◍ Housing co-op | Residential co-operative | One household, one vote |
| ◌ Parish council | Local elected representation | Elected for 4-year terms · public ledger |

## Tabs

Welcome · Institution · Members · Charter · Proposals · My votes · Ledger · Bundles · Build · LLM Providers · Fork Seed · Inspect · Settings · Install

## Architecture invariants

- One HTML file · IDB primary · BroadcastChannel mesh (`fall-village` + `fall-signal`)
- **Web Crypto API · Ed25519** keypair per member (fallback to ECDSA P-256 for older browsers)
- **Signed bundles** — every export carries a signature; every import verifies before merging
- P3 audit chain on every state mutation
- Append-only ledger · deterministic conflict resolution by timestamp + signature order
- 8-provider LLM cascade with streaming
- Fork Seed packager (jsLiteral serializer)
- Cross-seed mesh handlers (`introspect` · `records-export`)

## Cosmology

Prime **1277**, spine-clean mod 127 = 7 (spine prime itself). Seed level **4**. Mesh channel **`fall-village`**. Root seed (parent: null). Seal **◊·κ=1**.

## Socket VIII note

Levels 4-5 of the FallSeed lift hierarchy were always going to require a multi-actor coordination substrate. Without Socket VIII (live P2P mesh) the substrate is signed JSON bundles passed by file / link / paste. The mechanic is structurally sound and ships today; the live-mesh upgrade is purely a substrate swap when ACGP2P or equivalent becomes available.

## Disclaimer

**Governance scaffolding, not legal advice.** This tool helps a group structure decisions — it does not constitute a binding legal entity, contract, or trust. For things that need legal force (a registered DAO, a CIC, a co-op with banking) pair this with the appropriate legal wrapper.

## Licence

MIT © Simon Gant.
