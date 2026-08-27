# RareMetal-as-a-Service

RareMetal-as-a-Service (RMaaS) is the framework that turns a physical metal holding into a verifiable, ongoing proof feed. It's the layer someone actually interacts with — MVN is the trust infrastructure underneath it.

## What it does

1. **Register a holding** — a custodian or holder registers metal (gold, silver, platinum, or other) with identifying details: type, weight, purity, serials if applicable.
2. **Attach a custodian** — link the holding to the vault or party that will physically attest to it going forward.
3. **Set a verification cadence** — weekly or monthly, chosen by the holder.
4. **Get a proof feed** — a live, checkable Proof of Reserve record that updates on that cadence and can be shared with whoever needs to rely on it.

## Why "as a service"

Building your own attestation pipeline — signature schemes, hash anchoring, staleness tracking, double-pledge checks — is a lot of infrastructure to stand up just to prove you have the gold you say you have. RMaaS exists so a custodian or fund can plug into a working verification pipeline instead of building one.

## Who this is for

- **Custodians and vault operators** who want to offer verifiable holdings as a differentiator, not just a marketing claim
- **Funds and lenders** using physical metal as collateral, who need proof that survives more scrutiny than a PDF
- **Individual holders** who want an independently checkable record of what they own, without publishing their full holdings publicly

## What it deliberately doesn't do

RMaaS doesn't custody metal, doesn't set prices, and doesn't make ownership determinations on its own — it verifies and publishes attestations made by custodians and assayers. The physical chain of custody is still a real-world problem that real-world parties are responsible for; RMaaS makes that chain checkable, it doesn't replace it.
