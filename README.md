# Robinhood PS4/PS5

## v0.1.55 — merged fixed host

This repository contains the fixed PS4 host UI from the Robinhood/Nemotron v0.1.55 merge.

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

Current selector entries include 5.05, 6.72, 7.00, 7.02, 7.55, 7.5X, 8.03, 8.52, 9.00, 9.60, 10.00, 10.01, 10.50, 10.70, 10.71, 11.00, 11.02, 12.02, 12.50, 12.52 and 12.02–12.52.

These entries are **not a promise of exploit availability**. They are firmware-matrix entries used to route research/evidence state. Routes remain explicitly locked until their evidence/adapter gates are satisfied.

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
