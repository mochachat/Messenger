# Future Add-ins for Mocha Messenger

Mocha Messenger is expected to grow into a broader client experience over time, and future add-ins are part of that long-term direction.

This page is intentionally public and high-level. It explains the direction without exposing private implementation or security-sensitive design.

## What “add-ins” means here

Add-ins would allow trusted extensions or companion integrations to add capabilities around the core Messenger experience.

Examples of the kinds of things that may eventually fit:

- account or service integrations that complement Messenger
- lightweight web or profile tools
- community or event features
- companion utilities that build on Mocha identity or contact presence

## What is not promised

This is not a commitment that every MSN-era add-in pattern will return exactly as it once existed.

The Mocha team still needs to decide:

- how add-ins are distributed
- how trust and signing work
- what sandboxing or permission model is required
- how public and private services interact with third-party integrations

## Public goals for future add-ins

If Mocha exposes an add-in system, the public goals are likely to include:

- clear trust boundaries
- safe installation flow
- strong user visibility into what an add-in does
- compatibility with the core Messenger experience
- room for community ideas without compromising service safety

## Good public discussion topics

Helpful community input includes:

- what kinds of add-ins would actually be valuable
- how much access add-ins should have
- what kind of trust or permission prompts users would expect
- whether an add-in hub should focus on Mocha-run extensions, community submissions, or both

## Relation to the website

The website may eventually include an add-in hub or public information page for this ecosystem.

Until then, this repository and wiki are good places to capture public expectations and ideas.
