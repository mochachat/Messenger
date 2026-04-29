# Contributing to Mocha Messenger

Thanks for wanting to help.

Mocha Messenger is developed in a private source repository, but this public repository is available so the community can still contribute ideas, documentation, testing notes, and design feedback.

## Good contributions for this repository

- documentation fixes
- release note wording
- compatibility reports
- screenshots
- UI mockups
- workflow suggestions
- protocol-adjacent public documentation updates
- wiki improvements

## Things that are reviewed here but implemented privately

- feature proposals
- client behavior changes
- moderation and service suggestions
- account and sign-in flow ideas
- network and conversation UX ideas

If accepted, these are manually reviewed and then ported into the private Mocha development repository by maintainers.

## Please do not submit

- private source code copied from the client
- reverse-engineered private internals that are not meant for public distribution
- secrets, tokens, server endpoints that are not already public, or deployment materials
- binaries containing unclear provenance

## Pull request expectations

Public pull requests should be narrow and easy to review.

Good examples:

- “Clarify release channel wording in README”
- “Add known limitation for Windows 10 software rendering compatibility”
- “Propose revised conversation mockup for contact actions”

## Private port workflow

When a public issue or PR is accepted:

1. The team confirms the idea publicly.
2. The change is reviewed for product fit and risk.
3. If it belongs in the shipped product, the Mocha team ports it into the private development repository.
4. The public thread is updated when appropriate.

## Bug reports

Helpful bug reports include:

- exact build number
- Windows version
- whether DWM / accent / custom shell tooling is in use
- reproduction steps
- screenshots
- whether the issue happens on a fresh sign-in or only after longer use

## Feature proposals

Feature requests are most useful when they explain:

- the user problem
- the expected behavior
- any MSN Messenger precedent, if relevant
- why the feature belongs in Mocha specifically
