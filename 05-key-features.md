# Key Features

**Continuous attestation, not point-in-time audits**
Custodians submit evidence on a recurring cadence they set, so a Proof of Reserve record has a visible last-checked timestamp instead of resting on an annual audit.

**Privacy-preserving by default**
Raw photos, video, and full inventory stay with the custodian. What's published is a hash, a signature, and a status — enough to verify, not enough to expose.

**Automated + human-reviewed verification**
Media authenticity, consistency, and duplication checks run automatically; anything inconclusive or high-stakes routes to a human assayer or auditor before acceptance.

**Double-pledge detection**
Every attestation checks its holding identifiers against the network, so the same bar can't carry two active, conflicting claims.

**Claim-specific proofs**
Possession, ownership, and aggregate value are distinct claim types — a Proof of Reserve record states which one it's making, rather than implying more than the underlying attestation supports.

**Custodian-agnostic**
MVN and RMaaS are built to work with any custodian or assayer willing to sign attestations — this isn't tied to a single vault network.

## Current status

This is an early-stage system. The attestation model, verification checks, and proof format described in these docs represent the design as it stands today, including the parts we know are unfinished — see the closing section of the [Introduction](01-introduction.md) for the honest version of what photo/video evidence can and can't prove on its own, and what's planned to close that gap.
