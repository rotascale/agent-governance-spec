# Contributing

## The most useful contribution

**A second implementation.** This document currently describes one system,
however carefully it is written, and that is its main weakness. An
implementation built from the text — finding the places where the text is
ambiguous, under-specified, or quietly assumes something only the reference
implementation does — is worth more than any number of editorial improvements.

If you are building one, open an issue early. Where the specification is unclear
that is a defect in the specification.

## Proposing a change

Open an issue before a pull request. A change to a specification is a change to
what other people's software must do, so the discussion matters more than the
diff.

State: what the current text requires, what it should require instead, and **what
breaks** for an implementation that already conforms.

## What will be refused

**Requirements with no implementation.** Everything specified here is running
somewhere. A requirement nobody has built is a design proposal, and this document
is deliberately not that.

**Vendor-specific mechanisms.** If a requirement can only be satisfied by one
product, it belongs in that product's documentation.

**Conformance claims without tests.** See the specification's own §6 — asking
implementers to grade themselves is the practice this document exists to
replace.

## Editorial changes

Typos, grammar and clarity fixes are welcome as pull requests without an issue,
provided they change no requirement. If you are unsure whether a wording change
alters a requirement, it probably does — open an issue.
