# Ademola Ernest Ajala

**AI-native software developer** building payment infrastructure, developer tooling, and fintech products — across Stellar/Soroban, TypeScript, and mobile.

I work as core developer and maintainer across three active projects. Below is what each one actually does and where it stands, not a highlight reel.

---

### 🔗 [Accensa](https://accensa-dashboard.vercel.app/) — merchant back-office for x402 sellers on Stellar
*Core developer & maintainer of all three repos.*

x402 lets an AI agent pay for an API call over HTTP — but the merchant is left reading raw ledger transfers with no revenue view, no per-route attribution, and no way to resolve a dispute. Accensa closes that gap: an indexer reconstructs payment history from Stellar, receipts are Merkle-anchored on-chain so agents can verify them without trusting the seller's dashboard, and a refund vault runs on an enforced, non-custodial policy.

| Repo | What it is | Stars |
|---|---|---|
| [`accensa-contracts`](https://github.com/accensa/accensa-contracts) | Soroban contracts — receipt anchoring + refund vault. Both are **immutable by design** (no upgrade path), with property-based fuzz suites pinning invariants like "float always equals deposits − refunds − withdrawals." | 18 |
| [`accensa-app`](https://github.com/accensa/accensa-app) | Next.js dashboard, Stellar indexer, and the `@accensa/sdk` TypeScript package for route-level payment attribution. Live testnet deployment. | 13 |
| [`x402-facilitator-stellar`](https://github.com/accensa/x402-facilitator-stellar) | x402 payment facilitator conformance spike. Ships settled, on-chain-verifiable testnet transactions — and documents which upstream conformance scenarios still fail, rather than hiding them. | 11 |

---

### 🔗 [Tollcraft](https://tollcraft.github.io/soroban-cost-profiler/) — cost-awareness pipeline for Soroban contracts
*Core developer.* Accepted into the Stellar Wave Program (Drips Wave 7).

Soroban meters CPU, memory, and storage — and many expensive mistakes are structurally obvious before you ever hit testnet. Tollcraft is a three-tier pipeline that catches them earlier and earlier: a compile-time linter, a CI-blocking runtime assertion layer, and a flamegraph profiler for when a budget check fails and you need to know exactly where the cost went.

| Repo | Tier | Stars |
|---|---|---|
| [`soroban-cost-linter`](https://github.com/Tollcraft/soroban-cost-linter) | 1 — static AST lints (storage-in-loop, redundant clones, redundant host calls), Dylint-powered | 30 |
| [`soroban-budget-assert`](https://github.com/Tollcraft/soroban-budget-assert) | 2 — `#[budget_cpu_lt(N)]` test macros + a workspace-wide network-verified cost report | 0 |
| [`soroban-cost-profiler`](https://github.com/Tollcraft/soroban-cost-profiler) | 3 — DWARF-mapped WASM execution tracing → flamegraphs | 1 |

---

### 🔗 [StaffPurse](https://github.com/StaffPurse/) — spend control for informal micro-businesses
*Core developer.* Built for BMONI's "Hack the Future" hackathon.

Nigerian micro-businesses that can't clear formal registration or multi-tier banking approval still need to delegate spending to staff. StaffPurse issues capped virtual cards backed by BMONI's embedded smart wallets, so an owner keeps self-custody of the main balance while staff get a hardware-keystore-secured card with a hard spend ceiling.

**Stack:** Flutter (mobile-only — hardware keystore requirement rules out web/desktop) · Riverpod · Supabase/PostgreSQL · BMONI Embedded SDK (secp256k1 signing via Secure Enclave/Android Keystore)

---

### Tech

`Rust` · `Soroban / Stellar` · `TypeScript` · `Next.js` · `Flutter` · `PostgreSQL` · `MQL5`

---

### Also

Ongoing MQL5 Expert Advisor development and auditing across several algorithmic trading strategies — including a critical missing-stop-loss catch on a live straddle-breakout EA.
