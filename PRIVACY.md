# Mocha Messenger Privacy Policy

Last updated: April 29, 2026

This Privacy Policy explains how MochaChat Contributors ("Mocha," "we," "us,"
or "our") handle information in connection with:

- the Mocha Messenger Windows client;
- Mocha Passport;
- Mocha Messenger Service, including the Notification Server and Switchboard;
- Mocha websites and download pages that we operate; and
- related support and pre-release testing workflows

This policy is intended to describe the current data practices reflected in
the current Mocha codebase and public service stack as of the date above.
Because Mocha is actively developing the Services, those practices may change
as the software changes.

## 1. The Services covered by this policy

Mocha currently includes the following service components:

- `Mocha Messenger`, a Windows desktop client;
- `Mocha Passport`, the account, contact, token, privacy, and activity-alert
  service;
- `Mocha Messenger Service / Notification Server`, which handles login,
  contact sync, presence, and conversation routing; and
- `Mocha Messenger Service / Switchboard`, which relays conversation traffic
  in real time

## 2. Information we collect

### Account and identity data

When you create and use a Mocha Passport account, the current implementation
stores:

- your username, which the current Windows client presents as your sign-in
  address;
- your display name;
- an internal user ID such as `u1`;
- whether the account currently has administrator access; and
- your password hash and password salt

Passwords are not stored in plain text in the Passport database.

### Authentication and session data

Mocha Passport currently issues and stores:

- signed session tokens;
- refresh tokens;
- refresh-token creation, expiration, and revocation timestamps; and
- token lifetime settings used to authenticate the client to Mocha services

### Contact, privacy, and social graph data

The current implementation stores:

- your contact list entries;
- contact aliases;
- blocked-user lists;
- incoming and outgoing contact-request state; and
- the list of users who may currently see or request access to you through
  contacts or pending requests

### Administrative and moderation data

When Mocha administrative controls are used, the current implementation can
store:

- whether an account has administrator access;
- whether an account is currently banned from the Mocha service;
- whether a ban is permanent or temporary;
- a temporary-ban expiration timestamp, if applicable;
- a moderation action timestamp;
- an optional moderation reason; and
- the user ID of the administrator who issued the ban

### Presence and profile data

When you sign in and use the Messenger client, the Services process:

- your display name;
- your selected status or presence code;
- your personal message; and
- the same fields for users you interact with through your contact list and
  active sessions

### Conversation and activity data

The current server implementation processes real-time conversation data such
as:

- message payloads;
- typing notifications;
- conversation invitations;
- voice and video conversation invitations and related session-control
  messages;
- current media-relay payloads used during active voice or video
  conversations;
- participant join and leave events; and
- file-transfer control messages and file chunks used during transfers

In the current implementation, general message history is not written to a
permanent server-side message archive. However, if a recipient is offline,
Passport can temporarily store an `ActivityAlert` record containing:

- a generated alert ID;
- the recipient's internal user reference;
- an alert type such as `message`;
- the sender's user ID, username, and display name; and
- a short text field truncated to 320 characters

Those activity alerts are returned to the recipient when they poll for
activity and are then deleted from Passport storage.

### Local device data stored by the Windows client

The current Windows client stores user settings locally in:

`%AppData%\\Mocha\\Mocha Messenger\\client-options.json`

That settings file can include:

- local display-name and personal-message preferences;
- message font and graphics preferences;
- audio and video device preferences, including acoustic echo-cancellation
  preference;
- country/region and phone-number fields entered in the options UI;
- run-in-background and inactivity preferences;
- notification and sound preferences;
- local alert-history entries and update-deferral preferences stored by the
  client;
- the configured receive-files folder;
- blocked contact IDs mirrored locally from Passport;
- recent sign-in addresses;
- auto-sign-in preferences;
- contact sorting and local contact-group assignments; and
- proxy settings, including proxy host, port, user ID, and proxy password if
  entered

If you enable remembered sign-in, the client also stores a protected version
of your password locally using Windows DPAPI for the current Windows user
account.

If you accept incoming files, the client stores those files in the receive
folder you configure, which defaults to a folder under your Documents
directory.

### Technical and log data

The current service code writes operational logs to standard output, and
deployed infrastructure such as `nginx`, service managers, hosting providers,
or reverse proxies may also create logs. Depending on deployment, those logs
can include:

- IP addresses;
- ports;
- timestamps;
- hostnames;
- request paths;
- HTTP status codes;
- command diagnostics; and
- service errors

The Notification Server and Switchboard also log client connection and
disconnection events and certain protocol diagnostics. The current desktop
client keeps a protocol monitor in memory during runtime and redacts login
passwords from that in-memory monitor. The desktop client does not persist
that protocol monitor to disk by default.

## 3. How we use information

We use information to:

- create and authenticate accounts;
- operate contacts, privacy controls, presence, messaging, typing, voice and
  video conversations, and file transfer;
- issue and validate session and switchboard-access tokens;
- route conversations, media relay traffic, activity alerts, service notices,
  and update checks;
- manage administrative access, service moderation, and bans;
- secure the Services and investigate abuse, bugs, and reliability issues;
- provide support and respond to bug reports; and
- improve or maintain the Services during development

## 4. What we do not currently do

Based on the current Windows client and core service code inspected for this
build:

- we do not include a dedicated advertising SDK;
- we do not include a dedicated client telemetry or analytics SDK in the
  Windows client;
- we do not maintain a permanent server-side general message-history database
  in the current Passport, Notification Server, or Switchboard
  implementation; and
- we do not intentionally store complete transferred files on the server side
  in the current implementation

That said, infrastructure logs, reverse proxies, crash situations, or future
builds may change actual data handling, so you should review the current
published policy for the specific build and deployment you use.

## 5. How information is shared

We share information only as needed to operate the Services and support
users, including with:

- Mocha service components that need the data to authenticate you, sync
  contacts, apply privacy rules, route messages, or relay conversations;
- hosting, network, reverse-proxy, certificate, and infrastructure providers
  used to run the Services;
- service operators, moderators, and contributors who need access for
  support, abuse handling, security, debugging, or maintenance; and
- third-party services you choose to use, such as Discord for bug reports or
  support

We do not state in this policy that Mocha sells personal information.

## 6. Retention

Retention depends on the type of data:

- account records, administrator-access flags, moderation records stored on
  user accounts, contacts, blocked-user entries, and contact requests remain
  until changed, removed, expired, or deleted from the underlying service
  storage;
- refresh tokens remain until they expire or are revoked;
- temporary activity alerts remain until they are polled and deleted, or
  until service data is otherwise cleared;
- infrastructure and service logs remain according to the retention settings
  of the deployed environment; and
- local client settings, local alert history, deferred update state, and
  received files remain on your device until you remove them or
  reinstall/reset the software

At the time of this draft, the current codebase does not expose a complete
self-service account-deletion workflow in the client or Passport API. Privacy
or deletion requests may therefore require manual handling through Mocha
support channels.

## 7. Your choices and controls

Depending on the current build and service deployment, you can:

- create or stop using a Mocha Passport account;
- edit your local display-name and personal-message preferences;
- manage contacts, blocks, and contact requests through the client and
  Passport APIs;
- choose audio/video devices and local call preferences through the client;
- disable remembered sign-in and remove local saved credentials;
- clear local alert history by resetting or replacing the local client
  settings file;
- change the folder where received files are stored; and
- delete local settings files and received files from your own device

For manual support, privacy requests, or bug reports for this pre-release
period, contact Mocha through the official Discord server:

`https://discord.gg/D5kTDnGkXs`

If you contact us through Discord or another third-party service, that third
party's own privacy policy also applies.

## 8. Security

In the current implementation:

- Passport hashes passwords with PBKDF2-SHA256 and a per-password salt;
- Passport issues signed session tokens;
- the Notification Server issues signed switchboard tickets;
- TLS is used for the Notification Server and Switchboard; and
- the Windows client can validate service certificates using the system trust
  store, a bundled Mocha root certificate, or a known local development
  certificate fallback

No system can guarantee perfect security, especially during active
development and pre-release testing.

## 9. Children

Mocha Messenger is not intended to be a service directed to children under
13. If you believe a child has provided personal information to Mocha
inappropriately, contact us through the official Discord server so we can
review the issue.

## 10. International use

Mocha may be used from different locations, and infrastructure may be hosted
in jurisdictions different from your own. By using the Services, you
understand that your information may be processed in the jurisdictions where
Mocha or its infrastructure operators run the Services.

## 11. Changes to this policy

Because Mocha is actively developed, we may update this Privacy Policy as the
product or deployment changes. We will update the "Last updated" date when we
revise this document for a new published version.

## 12. Contact

For support, bug reports, and privacy questions related to this build,
contact:

Official Mocha Discord server: `https://discord.gg/D5kTDnGkXs`

This document is a product-specific operational privacy draft, not a
representation that every deployment of Mocha is identical or that the
Services satisfy every jurisdiction's legal requirements without additional
review.
