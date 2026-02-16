# skillseal-attestations

Third-party attestation bundles for [SkillSeal](https://github.com/mcyork/skillseal) skill packages.

## What is this?

Each `.attestation.json` file is a multi-key-signed, content-addressed statement vouching for a specific version of a skill package. Attestations are independent of the skill author — the reviewer creates and hosts them here.

As of v0.2.0, attestation bundles carry multiple signatures (GPG + SSH) in a `signatures[]` array. Verification requires only one valid signature.

## Directory convention

```
{author-github}/{skill-name}/{version}.attestation.json
```

## Verifying an attestation

```bash
# Fetch and verify against a local skill
skillseal verify ~/path/to/skill \
  --attestation https://raw.githubusercontent.com/mcyork/skillseal-attestations/main/mcyork/skillseal-demo-sslcheck/1.0.0.attestation.json

# Or clone this repo and verify locally
skillseal verify ~/path/to/skill --attestation ./mcyork/skillseal-demo-sslcheck/1.0.0.attestation.json
```

## Reviewer

- **Name:** Ian McCutcheon
- **GitHub:** [mcyork](https://github.com/mcyork)
- **Keys:**
  - GPG: `7097CE1EF54E0808FD3855427ED9682FF64286D0` ([public key](https://github.com/mcyork.gpg))
  - SSH: `SHA256:vZcivMOtxMdRjvcyGpNSjECXhb/wspMSsHO/bfPXBmQ` (Ed25519)

## Format

See the [attestation format spec](https://github.com/mcyork/skillseal/blob/main/spec/attestation-format.md).

## Attested Skills

### mcyork (self-authored, signed)
- `skillseal-demo-sslcheck` v1.0.0
- `skillseal-demo-plugin` v1.0.0

### danielmiessler (third-party, unsigned)
- 37+ PAI skills attested with full-review scope
