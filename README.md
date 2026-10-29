# SafeKeepVault online demo

This repository only hosts the online demo of [SafeKeepVault](https://github.com/Pasalon0404/SafeKeepVault) at **https://demo.safekeepbitcoin.com**. The source code lives in the SafeKeepVault repository; the files here are build output.

**Do not use this demo with real bitcoin.** It runs in your web browser on an online computer. Only the public demo seeds work in it, and anything sent to a demo address can be taken by anyone. To protect real bitcoin, use the real vault, which runs offline from a USB stick: https://safekeepbitcoin.com/download.html

## What's here

| File | What it is |
|---|---|
| `index.html` | The demo, built with `npm run build:demo` |
| `favicon.svg` | The site icon |
| `CNAME` | The demo's domain, for GitHub Pages |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## This build

- Version stamp: `v1.56 · build 415 · 9d36cf2 · 2026-10-28 · demo`
- Built from SafeKeepVault `main` at commit [`9d36cf2`](https://github.com/Pasalon0404/SafeKeepVault/commit/9d36cf2): release [`v1.56`](https://github.com/Pasalon0404/SafeKeepVault/releases/tag/v1.56) plus two demo-only changes: [PR #85](https://github.com/Pasalon0404/SafeKeepVault/pull/85) (slow phones open on the demo seed instead of the setup screen) and [PR #86](https://github.com/Pasalon0404/SafeKeepVault/pull/86) (the banner says the demo is a preview, not a working vault, and that the vault runs on a laptop or desktop)
- SHA-256 of `index.html`: `9af1c58eac5e453ff7524ddd32e7be9881b57a8c28eddacd7dbd295ba153d340`

To rebuild it yourself:

```sh
git clone https://github.com/Pasalon0404/SafeKeepVault.git
cd SafeKeepVault
git checkout 9d36cf2
cd seed-xor-tool
npm ci
npm run build:demo
```

The result is in `seed-xor-tool/dist-demo/`.

## The demo's safeguards

These are described in the SafeKeepVault README ("Online Demo") and implemented in `seed-xor-tool/shared/demo-mode.js`:

- Only the public demo seeds work. Any other seed is refused.
- Seeds created in the demo are never shown; the demo continues with a public demo seed.
- The page can't make network connections (Content-Security-Policy `connect-src 'none'`).
- A banner that can't be closed, and "SAFEKEEP DEMO — NOT A REAL BACKUP" on every printout.
