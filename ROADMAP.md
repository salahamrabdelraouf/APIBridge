# APIBridge roadmap

Near-term, honest items only — things already designed or already
promised, in the order they are likely to land. This list is a plan,
not a promise: items move as real-world reports come in.

## In progress

- **Staged, step-by-step bulk testing** — large model test runs split
  into sequential, visible steps sized by a smart scheduler referenced
  to a 4 GB RAM floor, so the interface stays responsive at any scale
  (250, 500, 1000, 2000+ models).
- **Mid-stream continuation for the 🧠 Smart unified model and the
  two-model team** — if a model stalls mid-generation, a substitute
  continues the active session from the exact point of failure, without
  losing context.

## Next

- **Data-folder ACL tightening, opt-in** — an explicit Settings action
  that restricts the data folder to the current user, offered (never
  forced), because portable installs may live on shared drives.
- **Skill Scanner: pinned resolution** — evaluate a skill URL's DNS
  answer once and connect to that exact address, closing the
  check-then-connect race completely.
- **Provider quick links** — open each provider's official website
  directly from Provider Management (independent of its API base URL).

## Not planned

- Cloud sync, accounts, or any server component — APIBridge is local,
  permanently.
- Telemetry of any kind.
- An installer. Portable is the product.

Shipped history lives in [CHANGELOG.md](CHANGELOG.md).
