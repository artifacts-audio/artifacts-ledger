# Cryptographic Integrity

How Artifacts prove their authenticity without requiring always-online verification.

## Self-Verifying Signatures

An Artifact carries everything needed to prove its authenticity:

- **Artifact contains**: Content, Signatures, Public key references
- **Ledger contains**: Public keys (verification data)
- **Verification**: Signature + Content + Public Key = Valid or Invalid

No server required. No internet required. Just math.

## The Ledger's Role

This repository (artifacts-ledger) is the root of trust. Public keys published here are canonical.

---

*Cryptographic integrity is the foundation. Without it, scarcity and evolution would be theater.*
