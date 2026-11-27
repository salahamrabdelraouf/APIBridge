# Security policy — APIBridge

## Reporting a vulnerability

Please report suspected vulnerabilities **privately first**, through
GitHub's private vulnerability reporting on this repository
(**Security → Report a vulnerability**), or via the project's channels:

- Telegram: https://t.me/PromptixOfficial
- Facebook: https://facebook.com/Promptix

Include the APIBridge version (About page → "Version & build"), what you
did, what you expected, and what actually happened. A small reproduction
is worth more than a long theory. Please do **not** include real
provider API keys in a report — synthetic keys demonstrate the same
behaviour.

## Supported versions

Only the latest release is supported with security fixes. If you are
running an older version, update first and check whether the issue
still reproduces.

## Response expectations

APIBridge is maintained by a small team led by its founder. Reports are
acknowledged as fast as reasonably possible, and confirmed
vulnerabilities are fixed in the next release; the fix and its
regression test are described in that release's audit notes. There is
no bug bounty.

## Verifying your download

Every release publishes `SHA256SUMS.txt` next to the portable and
source archives. Compare the hash of your download before running it:

```powershell
certutil -hashfile APIBridge-vX.Y.Z-portable.zip SHA256
```

The shipped files are additionally covered by the app's built-in
integrity manifest: if a listed file is missing or changed, the app
shows an Integrity Locked screen instead of starting. Restoring the
original files from the official package unlocks it.

## What the security controls do — and do not do

APIBridge is a local bridge. Its security model, stated precisely:

**It does**

- Listen only on the loopback interface (127.0.0.1). Requests from the
  local network are not accepted; a Host/Origin check rejects
  browser-driven (DNS-rebinding style) requests, and an optional strict
  mode additionally requires a per-install local token.
- Store provider keys locally on your machine, encrypted at rest with
  Windows DPAPI (current-user scope), and mask key-shaped strings in
  its logs.
- Send each provider only its own key, as the normal sign-in for your
  request, and never follow a redirect that would carry a key to a
  different host.
- Screen assistant traffic for secrets and tokenize them through a
  local vault (placeholders travel; real values stay on your machine),
  unless you mark a provider trusted and approve an exemption yourself.
  Exemptions are cryptographically sealed, re-verified at every use,
  and suspended automatically if anything about them drifts.
- Write integration changes to your tools' config files only after a
  backup, a format-preserving merge, and JSON verification — and refuse
  rather than guess when a file cannot be understood. Files APIBridge
  cannot parse are preserved byte-for-byte and reported, never silently
  reset or deleted.

**It does not**

- Protect you from software already running as your own Windows user
  or as administrator — no local app can.
- Control what a provider does with a request once you send it to them.
- Make an untrusted provider trustworthy; trust scores and scan results
  are evidence to help your decision, not a guarantee.

The companion statement of data practices is [PRIVACY.md](PRIVACY.md).
