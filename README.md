# Agent Governance Specification

A vocabulary for stating, in advance, what an autonomous agent is permitted to
**do** — and for recording what was decided, whether it was allowed or refused.

**Status: v0.1 draft.** One implementation. Comments and second implementers
both welcome; see [Contributing](CONTRIBUTING.md).

- **[Read the specification →](spec/v0.1.md)**
- [Changelog](CHANGELOG.md) · [Versioning policy](VERSIONING.md)

---

## Why this exists

Existing AI governance addresses the **model**: what it was trained on, how it
scores on evaluations, whether its outputs are toxic. None of that constrains
what an agent may do on a Tuesday afternoon with a payment API in reach.

The gap is not observability — agent frameworks already emit traces. The gap is
**authority**: a statement, made in advance by an accountable human, of what a
specific agent may do, up to what value, until when, and under what conditions,
enforced before the action rather than described after it.

Every platform vendor is building this for their own estate, and none will build
it across, because governing a competitor's runtime well is a feature that helps
a customer leave. An enterprise runs agents on several. The authority and the
evidence have to be expressible in terms none of those vendors own.

That is what this document is for.

## What it specifies

| | |
|---|---|
| **Entity model** | agent, grant, trajectory, decision, taint, evidence batch |
| **Authority grammar** | nine decision gates in normative order, four trace states |
| **Delegation** | attenuation on five axes, ancestor debiting, revocation cascade |
| **Enforcement** | the observe → shadow → canary → enforce ladder |
| **Custody** | what a signature is worth, given who held the key |
| **Three-state discipline** | why "we did not record this" is a third answer |

## What it does not specify

Contract language, evidence wire schema, OpenTelemetry conventions, conformance
tests, and identity federation between deployments — each named in the document
with the reason.

Conformance tests are absent **on purpose**. Publishing a conformance claim
without them asks implementers to grade themselves, which is the practice this
specification exists to replace.

## It is descriptive, and that is checked

Everything specified here is implemented and running. Nothing in it is planned.

That claim is the document's credibility, so it is enforced rather than
asserted: the reference implementation's test suite reads the gate order, trace
states, custody vocabulary and enforcement ladder out of its own source and
fails the build when the specification drifts from them.

A specification describing a roadmap is a press release, and the first reader to
check one against a running system decides which kind they are holding.

## Reference implementation

[Rotascale](https://rotascale.com) is the reference implementation, and
currently the only one. That is stated plainly rather than implied: **a
specification with one implementation is a description with ambitions.** A
second implementer is what would change that, and is the most useful
contribution anybody could make.

The specification is deliberately separable from that implementation. It names
no product, requires no particular storage or policy engine, and every
requirement in it can be satisfied by software written from scratch against the
document.

## Licence

[Apache License 2.0](LICENSE) — permissive, and carrying an explicit patent
grant, which matters for a specification people are meant to implement.
