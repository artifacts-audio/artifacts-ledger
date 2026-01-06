# Authenticity Policy

This document defines what makes an Artifact authentic and how authenticity is determined.

## Definition

An Artifact is **authentic** if and only if:

1. It appears in the [Registry](../registry/index.md)
2. Its checksum matches the registered checksum
3. Its signature verifies against the Artifacts Audio release key
4. It has not been revoked

All four conditions must be true. If any condition fails, the Artifact is not authentic.

## The Chain of Authenticity

```
Creator → Forge → Signature → Registry → Verification → User
```

1. **Creator** authors the Artifact in Forge
2. **Forge** packages and prepares it for signing
3. **Signature** is applied using the release key
4. **Registry** entry is created in this ledger
5. **Verification** is performed by the user before installation
6. **User** can trust the Artifact is what it claims to be

No step can be skipped. The chain is only as strong as its weakest link.

## What Authenticity Guarantees

An authentic Artifact guarantees:

- **Origin**: It was created by the registered creator
- **Integrity**: It has not been modified since signing
- **Identity**: It is the Artifact it claims to be (correct ID, version, stage)
- **Standing**: It has not been revoked or recalled

## What Authenticity Does Not Guarantee

Authenticity does not guarantee:

- **Quality**: An authentic Artifact may still have bugs
- **Fitness**: An authentic Artifact may not suit your needs
- **Safety**: An authentic Artifact may have undiscovered vulnerabilities
- **Value**: Authenticity does not determine market value

Authenticity is necessary but not sufficient for trust.

## Verification Responsibility

**Artifacts Audio** is responsible for:

- Maintaining the integrity of the signing key
- Accurately recording releases in the registry
- Promptly revoking compromised or defective releases
- Providing clear verification instructions

**Users** are responsible for:

- Verifying downloads before installation
- Reporting suspected forgeries
- Not installing unverified Artifacts
- Keeping verification tools up to date

## Forgery and Fraud

Creating, distributing, or selling inauthentic Artifacts that claim to be authentic is:

- A violation of our terms of service
- Potentially illegal (fraud, trademark infringement)
- Harmful to the ecosystem

If you encounter a suspected forgery:

1. Do not install or use it
2. Document where you obtained it
3. Report it to [security@artifacts.audio](mailto:security@artifacts.audio)

We investigate all reports and take action to protect users.

## Edge Cases

### Modified Artifacts

If you modify an Artifact (even legitimately, for personal use), it is no longer authentic. The checksum will not match. This is by design.

Modified Artifacts:

- Cannot be verified
- Should not be distributed
- Are used at your own risk

### Unsigned Builds

Development or beta builds may not be signed. These are:

- Clearly labeled as unsigned
- Not listed in the official registry
- For testing purposes only
- Not supported for production use

### Third-Party Artifacts

When community-created Artifacts are supported, they will have:

- A distinct ID prefix
- Their own creator signatures
- Clear labeling as community content
- Separate verification paths

The authenticity rules will be equivalent but attribution will differ.
