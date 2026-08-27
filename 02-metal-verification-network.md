# Metal Verification Network (MVN)

MVN is the infrastructure layer underneath everything else. It doesn't hold metal and it doesn't issue proofs on its own — it's the pipe that gets an attestation from a custodian's vault to a form the outside world can check.

## Who submits to it

**Custodians** — vault operators holding physical metal on behalf of a client.
**Assayers** — independent parties who test purity and weight.
**Auditors** — periodic third-party reviewers who can co-sign a holding's history.

Any of these can be an *attestor*. A single holding can carry attestations from more than one, which matters more than it sounds — a custodian attesting to their own vault is a much weaker claim than a custodian and an independent assayer agreeing.

## What gets submitted

For each holding, an attestation bundles:

- **Identity data** — serial or bar number, refinery mark, denomination
- **Physical measurements** — weight, purity (fineness), sometimes dimensions
- **Evidence** — photo or video captured at submission time
- **Custodian signature** — cryptographically signed by the attesting party
- **Timestamp** — when the check happened, not when it was reported

## What gets published

The raw evidence stays with the custodian. What goes onchain is:

```
holding_id       → unique reference for this metal holding
evidence_hash    → cryptographic hash of the photo/video, not the file itself
metadata_hash    → hash of weight, purity, serial data
attestor_sig     → signature from the submitting custodian/assayer
timestamp        → when the attestation was made
status           → verified / flagged / stale
```

Anyone can confirm that a specific piece of evidence corresponds to this hash, that the signature belongs to a known attestor, and that the attestation is current — without ever seeing the photo, the vault's address, or the client's identity.

## Verification, not just recording

An attestation isn't accepted just because it was submitted. Before a holding's status moves to "verified," the submission goes through:

1. **Media authenticity checks** — is this a real, unmanipulated capture, and is it recent
2. **Consistency checks** — does this match the holding's prior attestations (same bar, same marks, plausible condition change)
3. **Cross-reference checks** — is this serial/holding already attested elsewhere, which would indicate double-pledging

Where this can be automated reliably, it is — image and video analysis are well suited to catching manipulation, duplication, and inconsistency at a speed no manual audit process can match. Where the automated check isn't confident, or the stakes are high enough to warrant it, the attestation is routed to a human assayer or auditor before it's accepted. The goal is a system that never rubber-stamps a submission automatically just because it arrived — every path ends in either a resolved verification or a flag.

## Privacy is the point, not a feature

The whole design exists so that "prove it" and "expose it" don't have to be the same request. A lender can confirm collateral exists without seeing the borrower's full vault contents. A regulator can confirm solvency without receiving a client list. That separation — proof without disclosure — is what makes continuous verification practical instead of just theoretically nice.
