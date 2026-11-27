# Contributing to APIBridge

Thank you for helping. APIBridge is a Windows desktop app written in
C# (WinForms, .NET Framework) and built with the C# compiler that ships
with Windows — no SDK or IDE is required to build it.

## Ways to help

- **Report bugs** — use the bug-report template. A screenshot and the
  exact steps are gold.
- **Suggest features** — use the feature-request template. Explain the
  problem first, then the idea.
- **Improve documentation** — typos, clarity, translations (the app is
  bilingual Arabic/English; documentation PRs in either are welcome).
- **Code** — see below.

## Building

1. Clone the repository.
2. Run `build.bat` (uses the in-box `csc.exe`).
3. Run the built app from the output folder, or run the self-test:
   `APIBridge.exe --selftest`

## Ground rules for code changes

- **Portable only.** No installer behaviour, no registry writes, no
  AppData. All state lives in the `data` folder beside the executable.
- **Data safety is sacred.** Never silently reset, delete, or rewrite a
  file the app cannot fully understand. Preserve it, report it, and let
  the user decide.
- **No silent UI.** Every action gives visible feedback inside the
  interface. No `MessageBox` for routine flows.
- **Destructive actions need deliberate friction** — an explicit button
  and, where the app already does so, a timed second confirmation.
- **Test what you change.** The self-test suite must pass, and UI
  changes should be verifiable from screenshots on real Windows.
- Keep changes focused: one purpose per pull request.

## Pull requests

- Describe what changed, why, and how you verified it.
- Include before/after screenshots for UI changes.
- By contributing you agree your work is licensed under the project's
  MIT license.
