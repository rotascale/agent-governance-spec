# Releasing

## Where the text is maintained

The specification is **maintained in the reference implementation's repository**
and copied here on release. That is deliberate, and it is temporary.

The reason is the guard. `test_spec_describes_the_implementation.py` reads the
gate order, trace states, custody vocabulary and enforcement ladder out of the
implementation's own source and fails its build when this document drifts from
them. That check is what makes the descriptive claim in §1 true rather than
merely stated — and it can only run where both the document and the code are.

So the flow is: change the code and the spec together, in one commit, with the
guard passing. Then release.

## What changes when there is a second implementer

This arrangement stops being right the moment somebody else implements the
document, because at that point the text is no longer one project's to hold. The
guard becomes one implementation's conformance check rather than the source of
truth, and this repository becomes canonical.

That is the intended end state. It is written down here so the transition is a
decision somebody makes rather than a thing nobody noticed was overdue.

## Steps

1. The change lands in the reference implementation with its guard passing.
2. Copy the specification file here.
3. Update `CHANGELOG.md` — what moved, and why.
4. Commit, tag `vMAJOR.MINOR`, push the tag.
5. Confirm the two copies agree — see below.

## Step 5 is a test, not a person remembering

Two copies of a document always drift, and a specification that disagrees with
itself across two repositories is worse than one that is merely out of date,
because a reader has no way to tell which is current.

`test_the_published_copy_says_the_same_thing`, in the reference
implementation, compares them whenever this repository is checked out beside
it. It skips when it is not, because "not checked out" is an environment fact
rather than a defect.

This step used to ask for the two files to be **byte-identical**. They are
not, and never were: the source carries a banner saying it is the source, and
the copy here carries the licence and the versioning policy. Asking for
something that has never been true is how a release step becomes a box people
tick. The test compares the **specification body** — everything from §1 to the
licence — which is the part a reader relies on.
