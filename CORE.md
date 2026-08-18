# Cards-pub — Core

Public releases-only mirror of `Cards-private` (offline-first encrypted card vault, Flutter —
see that repo's `CORE.md` for the full architecture, security invariants, and feature registry;
not re-pasted here). This repo holds **no source code**, only signed release APKs.

## Why it must stay public

`Cards-private`'s `scripts/release.sh` publishes each release here under tag `vX.Y.Z`, and the
app's on-device update checker (`UpdateChecker.kt`) reads
`https://api.github.com/repos/jitendrajangidcodes-cloud/Cards-pub/releases/latest`
unauthenticated. It must be public for that check to work without a token. The central
`app-store-web` hub also auto-mirrors this repo's latest release under its own `cards` tag (see
`app-store-web`'s `CORE.md` → "App Release Distribution"), but the in-app checker reads this repo
directly, not the hub.
