# SafeKeepVault online demo

This repository only hosts the online demo of [SafeKeepVault](https://github.com/Pasalon0404/SafeKeepVault) at **https://demo.safekeepbitcoin.com**. The source code lives in the SafeKeepVault repository; the files here are build output.

**Do not use this demo with real bitcoin.** It runs in your web browser on an online computer. Only the public demo seeds work in it, and anything sent to a demo address can be taken by anyone. To protect real bitcoin, use the real vault, which runs offline from a USB flash drive: https://safekeepbitcoin.com/download.html

## What's here

| File | What it is |
|---|---|
| `index.html` | The demo, built with `npm run build:demo` |
| `favicon.svg` | The site icon |
| `CNAME` | The demo's domain, for GitHub Pages |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## This build

- Version stamp: `v1.69 · build 607 · 91e3dfe · 2026-11-27 · demo`
- Built from SafeKeepVault release [`v1.69`](https://github.com/Pasalon0404/SafeKeepVault/releases/tag/v1.69) (commit [`91e3dfe`](https://github.com/Pasalon0404/SafeKeepVault/commit/91e3dfe)), which includes the demo changes from [PR #85](https://github.com/Pasalon0404/SafeKeepVault/pull/85), [PR #86](https://github.com/Pasalon0404/SafeKeepVault/pull/86) and [PR #111](https://github.com/Pasalon0404/SafeKeepVault/pull/111)
- SHA-256 of `index.html`: `4060fd9169f8b2e233547dc51f53964c771768046b1a9f8048d4af09320bd68f`

To rebuild it yourself:

```sh
git clone https://github.com/Pasalon0404/SafeKeepVault.git
cd SafeKeepVault
git checkout v1.69
cd app
npm ci
npm run build:demo
```

The result is in `app/dist-demo/`.

## The demo's safeguards

These are described in the SafeKeepVault README ("Online Demo") and implemented in `app/shared/demo-mode.js`:

- Only the public demo seeds work. Any other seed is refused.
- Seeds created in the demo are never shown; the demo continues with a public demo seed.
- The page can't make network connections (Content-Security-Policy `connect-src 'none'`).
- A banner that can't be closed, and "SAFEKEEP DEMO — NOT A REAL BACKUP" on every printout.
