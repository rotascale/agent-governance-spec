# Changelog

## v0.2 — 2026-08-13 (draft)

**Corrected 2026-08-16, while v0.2 is still a draft.** The "out of scope" entry
for OTel semantic conventions said *"The mapping exists in an SDK."* It does
not: `opentelemetry` is a dependency of no package in this project, and neither
SDK contains a span, an exporter or a mapping. The entry now says a mapping is
the obvious approach, belongs upstream at OpenTelemetry rather than here, and
does not exist yet.

**v0.1 is unchanged and still carries the original sentence.** Under
`VERSIONING.md` a published version is frozen: "if a requirement turns out to
be wrong, the fix ships in a new version and the old one keeps saying what it
said." That rule exists because implementations of this document produce
evidence, and a record stating it was produced under `0.1` has to mean in 2030
what it meant on the day it was written. Quietly correcting v0.1 was the first
thing attempted here and it was wrong for exactly the reason the document
gives. Tracked as rotascale-console#204.

**Adds §6, Clearance.** Whether an agent was checked before it was allowed to
act, and whether that check still holds.

Minor rather than major: nothing that conformed to `0.1` stops conforming.
Criterion 9 is conditional — it binds an implementation that issues clearances
at all, and says nothing about one that does not.

**Specified:** a clearance is a state computed at read time, never a stored
verdict; it binds to an agent in one environment; six causes that a reader must
be told apart, of which `drifted` MUST NOT invalidate and `superseded` MUST;
each check carries one of the three states of §5 rather than a pass or a fail,
with the judgement supplied by a named human; `not_recorded` must not block
issuance; clearance is required for authority that can refuse and must not be
required for authority that only observes; **every** path to enforcing
authority must be gated.

**Deliberately absent:** a certificate wire format. Clearance is a state and a
set of causes, not a document to exchange — and a format others should
interoperate with needs another implementer first.

Two requirements are lessons rather than design. `drifted` not invalidating
comes from noticing that a clearance expiring on every deployment is
permanently expired, which teaches people to ignore it. "Every path, not some"
comes from the reference implementation gating two of four and leaving the two
that mattered — one of them promotion along the enforcement ladder, which is
the transition the whole thing exists for.

## v0.1 — 2026-08-12 (draft, unpublished)

First draft. Entity model and authority grammar.

**Specified:** agent, grant, trajectory, decision, taint and evidence batch; the
nine decision gates and their order; four trace states; delegation with
attenuation on five axes; ancestor debiting; the enforcement ladder; revocation
cascade; key custody; the three-state discipline.

**Deliberately absent:** contract language, evidence wire schema, OpenTelemetry
conventions, conformance tests, cross-deployment identity federation.

Written as documentation of a running system rather than a design. Several
requirements — budget debited last, ancestor debiting, the enforcement ladder
being one-directional, `not_applicable` being distinct from `passed` — are
lessons from getting each of them wrong first.
