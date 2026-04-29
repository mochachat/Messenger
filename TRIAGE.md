# Labels and Triage

This page is a simple public triage guide for the Messenger repository.

## Suggested labels

- `bug`
- `enhancement`
- `docs`
- `ui-ux`
- `compatibility`
- `protocol`
- `question`
- `accepted`
- `considering`
- `needs-repro`
- `needs-design`
- `private-port-needed`
- `out-of-scope`

## Suggested triage flow

1. Confirm whether the report belongs in `Messenger` or `Protocol`.
2. Add a type label such as `bug`, `enhancement`, or `docs`.
3. Add a scope label such as `compatibility`, `ui-ux`, or `protocol`.
4. Mark accepted ideas with `accepted` or `private-port-needed` if the work
   belongs in the private repository.
5. Close clearly out-of-scope items with a short explanation.

## Good maintainer habits

- ask for build number and Windows version on bug reports
- ask for screenshots on UI issues when possible
- keep public replies clear about the private implementation workflow
- use `private-port-needed` only when the idea is genuinely intended for the
  private repo
