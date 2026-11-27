# Changelog

All notable changes to APIBridge are documented here. The format
follows [Keep a Changelog](https://keepachangelog.com/), and the
project uses date-stamped portable releases. The same changelog is
readable inside the app on the About page.

## [6.1.13] — 2026-11-26

- Per-tab Models toolbars (Failover / Active / Quarantine / Smart each
  show only their own tools).
- Test All stability roots fixed: fixed status strip, dedicated button,
  per-row progress reservation.
- OpenRouter FREE/PAID classification rebuilt on live pricing evidence
  (both prices zero = FREE; the `:free` suffix is a hint, never the
  rule), with per-model evidence in Discover.
- Bulk exemption verification now records passes with evidence and a
  per-row Approve path.
- Logs filter chips contrast fixed in both themes.

## [6.1] — 2026-11-25

- Data Manager arrives (from 6.1.3 it lives **inside Settings** as a
  popup): per-item explanations and safety labels, a guide assistant,
  Chrome-style clear-data panel, and wipe-everything-except-providers.
- Automatic quarantine with escalating retests and full history.
- Security rebuild: sealed trusted-provider exemptions, DPAPI-protected
  local token, owner-only data-folder ACL option.
- Model Test Chat from the Models page; registry-driven Settings.

## [6.0] — 2026-11-24

- Test-a-model from the Models list (ping / details / chat per
  provider), new motion system, redesigned Security page, live event
  log v2 with AI error diagnostics.

## [5.4] — 2026-11-24

- Internal security audit fixes (exact Host/Origin guard, same-host
  redirect discipline), trust package (SECURITY.md, ROADMAP.md, About
  does/does-not-do card).

_Earlier history (v2.1–v5.3) is summarised in the in-app changelog._
