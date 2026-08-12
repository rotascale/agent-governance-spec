# Versioning

Versions are `MAJOR.MINOR`. There is no patch level: an editorial fix that
changes no requirement is not a release.

## What each bump means

**MINOR** — new requirements, or existing ones clarified without changing what
conforms. An implementation conforming to `0.1` still conforms to `0.1` after
`0.2` ships; it simply does not claim `0.2`.

**MAJOR** — a change that makes a previously conforming implementation
non-conforming. Reordering the decision gates would be major. Adding a tenth
gate would be major. Renaming an outcome would be major.

## Nothing is silently redefined

A published version is frozen. If a requirement turns out to be wrong, the fix
ships in a new version and the old one keeps saying what it said.

This matters more here than in most specifications. Implementations of this
document produce **evidence**, and evidence is read years later by people who
were not in the room. A record stating it was produced under `0.1` has to mean
in 2030 what it meant on the day it was written, or the record is worthless.

## Pre-1.0

Below `1.0` the shape may still move, and this document says so rather than
implying stability it has not earned. What will not happen below `1.0` is a
silent change: every version is tagged, and the changelog says what moved and
why.

`1.0` requires two things, neither of which is a date:

1. **A conformance test suite.** Until then, conformance is a claim implementers
   make about themselves.
2. **A second independent implementation.** Until then this is a description of
   one system, however carefully it is written.
