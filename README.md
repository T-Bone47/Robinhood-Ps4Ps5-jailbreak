# Robinhood PS4/PS5

## v0.1.55 — merged fixed host

This repository contains the fixed PS4 host UI from the Robinhood/Nemotron v0.1.55 merge.

### Firmware selector

The PS4 host is matrix-driven and exposes the current research firmware set instead of the previous hard-coded 6.72 / 7.02 / 7.5X / 9.00 buttons.

Current selector entries include 5.05, 6.72, 7.00, 7.02, 7.55, 7.5X, 8.03, 8.52, 9.00, 9.60, 10.00, 10.01, 10.50, 10.70, 10.71, 11.00, 11.02, 12.02, 12.50, 12.52 and 12.02–12.52.

Routes remain explicitly locked until their evidence/adapter gates are satisfied. A firmware entry in the UI is not a claim of verified hardware execution.

### v0.1.55 hardening boundary

The merged design keeps research, simulated adapters, unverified payloads and runtime execution as separate states. Passing software tests does not constitute hardware verification.

Open `index.html` for the static PS4 host UI.