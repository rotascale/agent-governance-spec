# Changelog

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
