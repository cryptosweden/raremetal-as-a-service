# Introduction

Bullion has always run on a handshake. A vault says the gold is there. A certificate says it was checked, once, on a date already months old. Everyone downstream — a lender, a fund, a buyer — inherits that trust without ever being able to test it themselves.

We're building the layer that lets them test it.

## The problem: reserves you're asked to believe, not verify

Almost every "backed by physical metal" claim today rests on the same three things: a self-reported inventory list, an audit that happened once and is already stale, and a PDF nobody outside the audit firm can independently check. None of that is *proof* — it's paperwork. By the time a discrepancy surfaces, the metal has often already moved, been re-pledged, or never existed at all.

This isn't a hypothetical. It's the standard failure mode behind every bullion fraud of the last fifty years: a real vault, a real certificate, and inventory that was quietly overstated the whole time.

## The approach: continuous, cryptographic, and physical

Instead of a static certificate, custodians submit recurring evidence — photos, video, weight and purity readings — on a cadence they choose. That evidence is verified, hashed, and signed. The hash goes onchain. The metal itself never has to leave the vault, and the underlying media never has to leave the custodian's hands, for the world to check that the claim is real.

Where Proof of Reserves in crypto asks "does this wallet hold what it claims," we're asking the same question of something that can't be read off a blockchain by default: a bar sitting in a vault. That gap — between what's easy to verify onchain and what's actually valuable in the real world — is the one we're closing.

## What we're building

**Metal Verification Network (MVN)**
The trust layer. Custodians, assayers, and auditors submit signed attestations of what they hold — weight, purity, serials, imagery — without exposing the full inventory or the client behind it.

**Proof of Reserve**
The output. A continuously updated, independently checkable record that a given holding exists, matches its last attestation, and hasn't been double-pledged elsewhere.

**RareMetal-as-a-Service**
The framework. Register a holding, attach it to a custodian, set a verification cadence, and get a proof feed that lenders, buyers, or regulators can check without ever seeing your vault's floor plan.

## What this replaces

Not the vault. Not the custodian. Not the assayer. Those all still need to exist — someone has to physically hold and inspect the metal. What this replaces is the *distance* between that physical check and the person relying on it: the quarter that passes between audits, the trust placed in a PDF's letterhead, the inability to ask "is this still true, right now."

## A known gap, stated plainly

Photos and video are easier to fake than a wallet signature. A single frame proves a bar existed in front of a camera at some point — it doesn't by itself prove custody, allocation, or that the same bar isn't being shown to two different verifiers. We treat this as a real limitation of a v1 system, not a solved problem, and the roadmap includes harder-to-forge signals — serialized bar registries, tamper-evident tagging, third-party assayer sign-off — specifically because photo evidence alone isn't the end state.
