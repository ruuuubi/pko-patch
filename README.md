# pko-patch — Pirate King Online patch distribution

Public repository that distributes client updates to the **Pirate King Online launcher**.

## How it works

- Client binaries are delivered through **GitHub Releases**: each release carries the
  changed files as content-addressed assets (`<sha256>.bin`) plus a full-state `manifest.json`.
- The launcher reads `manifest.json` from the latest release, compares it against the local
  install, and downloads only the files whose hash differs — all with **no token** (public repo).

## What git tracks here

| File | Purpose | Edited by |
|------|---------|-----------|
| `content.json` | Side panels: server rates, upcoming mazes, level cap, news, links | You, by hand |
| `status.json` | Live players-online count | A server-side script |
| `manifest.json` | Full file list → sha256 + size + asset URL (also uploaded per release) | The publish tool |
| `README.md` / `.gitignore` | Repo setup | — |

The full game client is **not** stored here — it lives locally as the publish source and is
delivered to players only as release assets. Launcher source lives in the private `pko-launcher` repo.
