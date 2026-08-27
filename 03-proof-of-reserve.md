# Proof of Reserve

Proof of Reserve is what a verified holding looks like from the outside — the object a lender, buyer, or regulator actually checks.

## The three things it can prove

These are different claims, and a Proof of Reserve record specifies which one it's making:

**Possession** — this specific bar or lot exists and was verified as genuine at the given timestamp. Doesn't say who owns it.

**Ownership** — this entity holds legal claim to the attested holding. Requires the custodian to attest allocation, not just existence — an unallocated pool doesn't qualify.

**Aggregate value** — this entity's total holdings are worth at least X, without revealing which bars, how many, or where they sit. Useful for solvency claims where the specific inventory is nobody else's business.

Most institutions asking "prove your reserves" actually want ownership or aggregate value, not possession alone — a genuine bar sitting in a vault proves nothing about who it belongs to.

## Cadence

Custodians choose how often a holding gets re-attested — weekly or monthly are the common defaults. A Proof of Reserve record always shows its last-verified timestamp, so staleness is visible rather than hidden inside an annual audit cycle. A holding that hasn't been re-attested within its expected window is marked stale automatically, not left looking current by default.

## What double-pledging protection looks like

The failure mode that makes physical-asset backing risky isn't usually a fake bar — it's one real bar attested to two different parties at once. Every attestation checks its holding identifiers against the network before being accepted, so a serial number already carrying an active, verified attestation elsewhere gets flagged rather than silently accepted a second time. This is enforced at the network level, not left to individual custodians to self-police.

## Reading a Proof of Reserve record

A verifier — someone who didn't submit the attestation and doesn't work for the custodian — should be able to check, independently:

- That the claimed holding has a currently valid attestation
- Which type of claim is being made (possession, ownership, or aggregate value)
- When it was last checked, and by whom
- Whether it's ever been flagged for inconsistency

They should not need, and should not receive, the underlying photo, the vault's location, or any identifying detail beyond what the claim type requires.
