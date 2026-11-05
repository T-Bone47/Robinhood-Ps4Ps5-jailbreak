# Robinhood PS4/PS5

## v0.1.55 — merged fixed host

This repository contains the fixed PS4 host UI from the Robinhood/Nemotron v0.1.55 merge.


## 🧩 WebKitty runtime integration (review branch)

A reviewed integration branch, `integration/webkitty-upstream-6b2f4df`, pins the upstream [WebKitty PS4 host](https://github.com/ArabPixel/WebKitty) at commit `6b2f4df39fb427819d3a0ded282c7adc23643d5d` (AGPL-3.0-or-later). Its GitHub Pages workflow assembles the upstream host under `/webkitty/`, preserving its relative exploit and firmware-cache paths. The Robinhood interface links to that separate host.

See [integration/README.md](integration/README.md) and [firmware route metadata](integration/firmware-routes.webkitty.json).

**Important:** the upstream source includes WebKit/kernel exploit implementations and per-firmware cache manifests, but this does not make every route hardware-verified in Robinhood. GoldHEN binaries are not bundled or verified. The Robinhood status remains gated pending payload provenance, exact-firmware validation, and real-console testing. The branch is not live on GitHub Pages until reviewed and merged into `main`.

## 🌐 Live host

**Robinhood v0.1.55:**

https://t-bone47.github.io/Robinhood-Ps4Ps5-jailbreak/

This is a GitHub Pages **project site**. GitHub project sites use the pattern `https://<owner>.github.io/<repository>/`. citeturn0search3turn0search4

> **Important:** The current v0.1.55 Pages build is a PS4 host UI. The repository name includes PS4/PS5, but this release does **not** claim that PS5 exploit execution is implemented or verified.

## 🎮 PS4 user setup

### Before you start

1. On the PS4, open **Settings → System → System Information** and note the exact system software version.
2. Keep the console on the firmware you intend to use. Do not update simply because the host does not list or verify your firmware.
3. Use the exact firmware entry shown by the host. A selector entry is a research/route entry and **does not mean hardware execution has been verified**.
4. Make sure the PS4 has network access to the live host.

### Using the Robinhood web host

1. Open the PS4 web browser / User's Guide entry available on your system.
2. Navigate to the live Robinhood host:
   `https://t-bone47.github.io/Robinhood-Ps4Ps5-jailbreak/`
3. Wait for the host interface to load.
4. Select **AUTO DETECT FIRMWARE** if supported by the environment. Browser-based detection may not be able to read the console firmware automatically.
5. Select the **exact firmware version** manually when automatic detection is unavailable.
6. Review the route status and evidence state shown by the host.
7. Only use an execution route when the UI reports that the required adapter/payload/evidence gates have been satisfied.
8. If the route is shown as **LOCKED**, stop there. Do not treat a locked or simulated route as a working jailbreak.

### What the firmware buttons mean

The PS4 host is matrix-driven and exposes the current research firmware set instead of the previous hard-coded 6.72 / 7.02 / 7.5X / 9.00 buttons.

Current selector entries include the existing legacy set plus 9.03, 9.04, 9.50, 9.51, 11.50, 11.52, 12.00, 13.00, 13.02, 13.04, 13.50 and 13.52. The route catalog records upstream chain candidates separately from Robinhood hardware-test status.

These entries are **not a promise of exploit availability**. Where shown, WebKitty chain names are upstream range candidates, not a guarantee for every point release. Robinhood keeps execution locked until exact-firmware evidence, payload provenance, and hardware validation are recorded.

## 🧪 PS4 local/self-hosted option

If you are developing or testing the host locally, you can serve the static project from a computer on your LAN with a normal HTTP server and open the resulting local URL from the console. Keep this separate from the production GitHub Pages host.

## 🎮 PS5 status

**PS5 is not currently a verified end-user jailbreak path in this v0.1.55 Pages release.**

The project architecture keeps PS4 and PS5 models, chains, adapters, payloads and routes separated. Do not follow the PS4 instructions on a PS5 or assume that a PS4 firmware entry applies to PS5.

When a PS5 route is genuinely implemented and hardware-verified, it should receive its own clearly labelled model/firmware route and installation documentation.

## 🔐 Hardening / verification boundary

The merged design keeps research, simulated adapters, unverified payloads and runtime execution as separate states. Passing software tests does **not** constitute hardware verification.

- Simulated adapters must not be presented as verified hardware adapters.
- Unverified payloads must not be presented as verified payloads.
- A firmware matrix entry must not be presented as proof of exploit availability.
- Runtime execution must remain behind the project's evidence/adapter gates.

## 🛠️ Developer verification

From a local checkout:

```bash
npm run validate
npm test
npm run build
npm run package
```

The v0.1.55 hardening baseline reported 333 passing tests. Re-run the commands locally after changing the code rather than relying on an old test result.

## 📦 GitHub Pages deployment

The repository deploys the static host through GitHub Actions and GitHub Pages. GitHub Pages supports project sites directly from repositories, and an `index.html` at the top level of the published artifact is a valid entry point. citeturn0search3turn0search4

The deployment workflow is currently configured for GitHub Actions. After a push to `main`, check the repository's **Actions** tab and wait for the `Deploy Robinhood Pages` workflow to complete successfully.

## ⚠️ Safety / accuracy note

This README intentionally does not claim that every listed firmware has a working public jailbreak. Firmware support changes over time, and this repository's hardening model requires evidence and hardware verification before promoting a route to runtime execution.
