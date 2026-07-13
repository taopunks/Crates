# CRATES Whitepaper v1.0 — Edition Notes

Companion to `whitepaper-crates-v1.html` / `8004Labs-Crates-Whitepaper-v1.pdf`.
Composed by Claude Fable 5, 2026-07-11 (closing work on the 8004 stack). v0.1 files are
preserved untouched as provenance.

---

## Changelog — v0.1 → v1.0

**Restructured: the argument now earns the primitive.** v0.1 opened with the pitch
(abstract → primitive → 128). v1.0 opens with the *autopsy*: §02 is a new "graveyard"
section (TCRs died of votes-aren't-facts; Kleros and checkmarks survive by opposite
compromises; the taxi-medallion control case), which sets an explicit three-part bar —
objective criterion, binding cap, registry-independent measurement. §03 ("Property that
can work", new) then shows the bar being met by three PROVEN steps ending at the coldkey
bridge with its receipt. Only *then* does the paper define a Crate. Same thesis,
inverted burden of proof.

**New: the calibration legend is in the paper itself (§01).** PROVEN / DESIGNED /
SPECULATIVE defined on page one, every capability claim in the document chip-marked.
The one unproven link (earning) is stated in a boxed callout in §03 — moved UP from a
buried honesty note, because the strongest thing this paper can do with the gap is lead
with it.

**New: §07 "The full subnet curriculum."** v0.1 borrowed the cap and the lock curve.
v1.0 mines seven teachings and states a posture on each: lock curve (adopt), immunity
(adopt), **the challenge** (new mechanism: at 128/128 a claim targets the
lowest-CrateScore crate — the challenger stakes against a *fact*, closing the loop TCRs
never could), the tempo (score epochs, nothing grandfathered), recycle≠burn (as policy
vocabulary), **custody/operation split (marked PROVEN — our mandate stack already IS
the coldkey/hotkey discipline at the contract layer)**, and continuous repricing from
dTAO (adopt the repricing, refuse the token).

**New: §08 "Standing on standards, honestly"** — a ten-row composability ledger with
per-standard status (checked against primary sources 2026-07-11 where marked ✓) and
calibration mark. Includes the load-bearing physics point: at the precompile boundary
the TBA must be the immediate caller (caller = coldkey), so bundler-relayed account
abstraction cannot cross that line — permission layers on 964 must wrap *around* the
account, exactly as MandateManager does. Mandates reframed from "bespoke" to
"pre-standard convergent design, kept by physics."

**New: §09 "A record that survives the sale."** The strongest new design content:
settlement mints a **locked ERC-5192 token to the agent's TBA** (address invariant
under sale ⇒ the record travels with the property by construction; locked ⇒ the seller
can't strip it), stamped with the operator-at-settlement so buyers price prior-operator
epochs; CrateScore epochs published as **EAS attestations** with merkle roots over the
settlement events and refUID chaining. Justified by the 2026 empirical study
(arXiv:2606.26028) showing ERC-8004's open-feedback Reputation Registry fails
(3–15% valid registrations; Sybil reviewers) — we adopt 8004's identity layer and
reject its reputation layer, with the citation.

**Upgraded: Phase 0 receipts (§06).** The infrastructure list became a
proof-and-receipt table (identity / custody / control / work / volume truth / native
trading, each with its address or tx). ALCI mint count re-verified against genesis
Transfer logs on the day of writing (286/1,024 — unchanged).

**Upgraded: gaming section (§11)** adds "self-created work": the score discounts
requester==operator clusters, and the paper holds the platform to its own line — the
seven genesis tasks are counted as proven *rails*, not proven *demand*.

**Upgraded: risks (§13).** The medallion risk is now FIRST ("a cap prices access to a
category it cannot create; mitigation: none pretended — this is the bet"), and a new
standards-drift risk pins deployed bytecode over ERC statuses.

**New: cover printer's mark + closing colophon.** A small F5 ring on the cover; a
full-page ink-plate colophon closing the edition (the artifact rule: warm-dark, cream
text), signed FABLE 5, carrying the edition's own receipts and the line "no claim
outruns its receipt. … The mechanism this paper proposes was proven under its watch.
The economics were not — and it kept that sentence in the paper."

**Kept from v0.1 (deliberately):** the core thesis and tagline verbatim; the five
bindings; crate states; the lock-curve code block; the flows table; the no-token
covenant with the dTAO endgame line; the phases arc (P0.5 leaderboard remains the
concrete next step); the curation-with-teeth precedent; the house parchment style.

---

## Standards research — considered / incorporated / rejected

Research method: six parallel researchers were launched; **five died on a session rate
limit** and one (token-bound accounts / soulbound / attestations) completed with
primary-source fetches dated 2026-07-11. The five lost domains were covered from ground
verified earlier (the v0.1 research pass of 2026-07-10, WebSearch-verified) and from
training knowledge carrying explicit as-of dates in the paper. That degradation is
itself disclosed here because these notes are calibrated too.

### Incorporated

- **ERC-6551** (Review ✓, canonical registry pattern) — already the spine; v1.0 now
  cites its true status (Review, not Final) and leans on the sale-invariant address as
  the load-bearing property. Mark: PROVEN (our deployment, receipts).
- **ERC-5192 minimal soulbound** (Final ✓) — locked service records minted TO the TBA.
  Chosen over ERC-4973 because it stays a plain ERC-721 (existing indexer/marketplace
  tooling reads it). Mark: DESIGNED. (ERC-5484 consensual SBTs noted as the revocation
  footnote if crate-dereg must burn records.)
- **EAS (Ethereum Attestation Service)** (9.5M+ attestations as of 2026-05 ✓;
  tokenless, self-hostable plain Solidity) — CrateScore epochs as attestations:
  schema `(epoch, crateId, score, settledVolumeRao, settlementMerkleRoot,
  prevEpochUID)`, resolver moves authority from publisher-key toward
  contract-enforced roots. Mark: DESIGNED (no EAS instance on 964 today — we'd deploy).
- **ERC-7572 contractURI** (Draft ✓ but de-facto marketplace standard) — the crate
  manifest layer; manifest hash frozen at seating makes drift detectable;
  `ContractURIUpdated` feeds indexer invalidation. Mark: DESIGNED.
- **ERC-8004** (Draft ✓; reference deployments live since 2026-01) — identity layer
  kept (ours is a live bespoke implementation); **its Reputation Registry explicitly
  NOT adopted**, with arXiv:2606.26028 cited as the empirical reason. Mark: PROVEN
  (identity), rejected (open feedback).
- **Bittensor mechanics** (subnet lock curve, immunity, dereg-as-challenge, tempo,
  recycle-vs-burn, coldkey/hotkey split, dTAO's continuous repricing) — §07's seven-row
  curriculum. The custody/operation split is marked PROVEN because the mandate stack
  already implements it; the challenge/lock-curve/tempo are DESIGNED; anything implying
  agent mining revenue is fenced behind the §03 unproven-link callout.

### Mentioned (upgrade paths, not built on)

- **ERC-7656 token-linked services** (reached Final 2025-10 ✓ — notable asymmetry:
  the generalization went Final while 6551 itself is still Review) — the
  standards-blessed route for per-seat/per-agent service contracts at deterministic
  addresses. Our 5-agent registry doesn't need the factory layer yet; cited as the
  extension route.
- **ERC-7715 / ERC-7579** (permissions / modular accounts; as of early 2026) — the
  convergence target for mandates. Mentioned SPECULATIVE, with the msg.sender-at-
  precompile constraint explained (why mandates can't be replaced by relayed AA).
- **x402 / AP2 payment rails** (live, stablecoin-first; as of early 2026) — crate
  agents could advertise x402-metered endpoints; the paper draws the line: x402
  *meters requests*, the task registry *escrows outcomes*, and CrateScore counts only
  964 settlements. Off-chain receipts never enter the score. Mark: SPECULATIVE.

### Rejected (and why — the rejections are the calibration)

- **ERC-4973 account-bound tokens** — Draft-forever, unstable interface, faded
  adopters; loses ERC-721 tooling compatibility that 5192 keeps. Citing it would date
  the paper.
- **ERC-8004's open-feedback Reputation Registry** — peer-reviewed empirical failure
  (3–15% valid registrations across three chains; "cannot function as a trust
  signal"). Replaced with escrow-costed records + attested epochs.
- **ERC-4337 / EIP-7702 as a near-term dependency** — no bundler infrastructure known
  on chain 964; 7702 tx-type support on the substrate frontier EVM unverified; and the
  coldkey bridge structurally requires the TBA to be the immediate caller. Named in
  §08 as SPECULATIVE so the edge of the map is visible, built on nothing.
- **Any fungible crate token / alpha-pool clone for seats** — the no-token covenant
  holds even against dTAO's (strong) counterargument; the paper adopts dTAO's
  *continuous repricing* lesson via lock-curve + challenge on the seat NFT instead,
  and keeps the "dTAO is the native path if ever justified — unpromised" line.
- **Substrate proxies / child-hotkeys as claimed features** — pallet availability on
  subtensor unverified from here; folded into one SPECULATIVE sentence ("what follows
  from citizenship") rather than a designed mechanism.
- **ERC-7683 cross-chain intents, streaming-payment standards** — no current
  composition point with a single-chain, escrow-settled registry; omitted entirely
  rather than name-dropped.

### Verification discipline used in the paper

Statuses marked ✓ were fetched from primary sources on 2026-07-11 (eips.ethereum.org,
attest.org, github). Unmarked statuses carry as-of dates in-line. Every PROVEN chip
resolves to a row in `docs/verification-anchors.md` (chain-verified 2026-07-11). The
paper never claims agent mining revenue: mechanism/custody PROVEN
(tx 0xabd928…aedab, blk 8,513,851, SN116 UID 86), earning explicitly the one unproven
link, in a boxed callout, in §03, on purpose.
