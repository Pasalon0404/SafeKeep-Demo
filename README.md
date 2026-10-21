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

- Version stamp: `v1.50 · build 315 · ff1e6c3 · 2026-10-21 · demo`
- Built from SafeKeepVault release [`v1.50`](https://github.com/Pasalon0404/SafeKeepVault/releases/tag/v1.50) (commit `ff1e6c3`)
- SHA-256 of `index.html`: `7697650408a6c2acc7f2d84c15fa0735d11582296e4d535530bd8c420d54e1b3`

To rebuild it yourself:

```sh
git clone https://github.com/Pasalon0404/SafeKeepVault.git
cd SafeKeepVault
git checkout v1.50
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
