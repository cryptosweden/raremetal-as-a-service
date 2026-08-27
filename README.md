# raremetal-as-a-service
Todays goldvaults build mostly on a "trust us" policy. This is going to change that so that if verifable and proven that it acutally exsists.



Core pieces:

DVN equivalent → Metal Verification Network (MVN) — attestors (vault custodians, assayers, auditors) submit signed proofs of metal holdings (weight, purity, serial/bar numbers) without exposing the full inventory or client identity.
RareMetal-as-a-Service — the framework for registering a metal holding, linking it to a custodian attestation, and issuing a verifiable "proof of reserve" that others can check onchain without seeing the raw data.
Marketplace layer (optional, like YieldApp) — could surface metal-backed lending, redemption, or trading opportunities once the base verification exists.


Problems with the project that will be fixed:

Custodian trust model: metals aren't natively onchain like a wallet balance — you need a trusted (or federated) custodian/assayer to attest "yes, 100oz of 99.99% gold sits in vault X allocated to entity Y." That's an oracle problem, not a pure ZK problem.

Proof granularity: do you want to prove possession (bar exists, is real), ownership (this entity has claim to it), or value (aggregate worth without revealing which bars)? These need different proof designs.

This will be fixed with AI. The fix flow:

Custodian uploads photo/video of metal holding (weekly/monthly, their choice)
AI (vision model) checks: does this look like real bars/coins, do visible serials/hallmarks match what's registered, does it match previous submissions (same bars, consistent)
AI verdict + hash of the media + metadata → signed attestation
Attestation (hash only, not the raw media) → written onchain as a "Proof of Reserve" record
Anyone can verify: hash exists onchain, timestamp, custodian signature, AI confidence score — without seeing the actual photo or full inventory




https://cryptosweden.github.io/raremetal-as-a-service/ - early website of the Metal Verification Network will look like and function.
