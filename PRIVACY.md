# Privacy policy — APIBridge

_Last updated: 2026-11-27 · Applies to all current releases._

APIBridge is a **local desktop application**. It is not a service, it has
no servers, and it offers no user accounts. This policy therefore states,
precisely, what happens on **your own machine** — and the one place data
necessarily leaves it.

## The short version

- APIBridge collects **nothing**. No telemetry, no analytics, no crash
  reports, no usage statistics are transmitted anywhere. There is no
  APIBridge backend to transmit them to.
- Your API keys never leave your machine **except to the provider they
  belong to**, as the normal sign-in for requests you make — the same
  way any API client works.
- Everything APIBridge stores — providers, settings, logs, history —
  lives in a `data` folder **beside the executable, on your device**,
  under your control, deletable by you at any time.

## What APIBridge stores, and where

| Data | Where it lives | Who can see it |
|---|---|---|
| Provider API keys | `data` folder beside the app, encrypted at rest with Windows DPAPI (current-user scope) | Only your Windows user account |
| Provider list, model selections, settings | `data` folder beside the app | You |
| Request logs & usage counters | `data/logs` on your device; key-shaped strings are masked in logs | You |
| Assistant chats & model test history | `data` folder beside the app | You |
| Quarantine & health history | `data` folder beside the app | You |

You can inspect, export, back up, or delete every item from inside the
app (**Settings → Data Manager**), which explains what each item stores
and labels it by safety before you touch it.

## What leaves your machine — the complete list

1. **Requests you make.** When you (or a tool connected through
   APIBridge) send a prompt to a model, APIBridge forwards that request
   to the provider you selected, together with **that provider's own API
   key**, as the provider's normal authentication. This is the function
   of the app; it cannot work otherwise. What that provider then does
   with your request is governed by **the provider's own privacy
   policy**, not this one.
2. **Discovery and checks you initiate.** When you add a provider by
   URL, run a ping/health check, scan a skill, or verify a trusted
   provider, APIBridge contacts the address **you supplied** for that
   check — and nothing else.
3. **Links you click.** Buttons that open a provider's official
   website, this repository, or community pages open in your browser,
   like any link.

There is no other network destination. APIBridge does not "phone home",
check licences online, or fetch advertising.

## What connected tools receive

Tools you connect (for example ZCode or OpenCode) talk to APIBridge at
its local address. In **strict local-token mode** they receive a
per-install **local token** generated on your machine — **never your
real provider keys**. Your keys are used only by APIBridge itself, only
toward their own providers.

## The secret-leak shield

Assistant traffic passing through APIBridge is screened for secrets
(API keys, tokens, credentials). Detected secrets are replaced with
placeholders before the traffic continues, and the real values stay in
a local vault on your machine. If you deliberately mark a provider as
trusted and approve an exemption yourself, traffic to **that provider
only** may pass unshielded — the exemption is yours to grant, suspend,
or remove at any time, and it is cryptographically sealed against
tampering.

## Children, accounts, and tracking

APIBridge has no accounts, no sign-up, no advertising, no tracking
pixels, no third-party SDKs, and no profiling. It is suitable to run
entirely offline except for the provider requests you choose to make.

## Changes to this policy

If a future release ever changes any statement above, this file changes
in the same release, and the change is listed in `CHANGELOG.md`. The
honest sentence is the product: **if APIBridge ever collected data,
this policy would have to say so — and it does not, because it does
not.**

## Contact

Questions about this policy: open an issue in this repository, or use
the community channels in `README.md`.
