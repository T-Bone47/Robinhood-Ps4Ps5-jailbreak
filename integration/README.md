# Robinhood × WebKitty integration

This branch pins the complete WebKitty host source at commit `6b2f4df39fb427819d3a0ded282c7adc23643d5d`.

## Runtime

The GitHub Pages workflow checks out the pinned upstream commit into `webkitty/`. Robinhood links to `./webkitty/index.html`, which runs the upstream host in its own directory so its relative script, exploit, and cache-manifest paths remain intact.

## Included by the pinned upstream source

- WebKit userland entry adapters: PSFree, CSSFontFace, Slopkit and related supported chains
- Kernel chain dispatch: Lapse, Netctrl and Relapse
- Firmware-specific offset and chain tables
- Firmware-specific AppCache manifests and cache pages
- Existing upstream payload-loader support

## Firmware map

See [firmware-routes.webkitty.json](./firmware-routes.webkitty.json). These are upstream-supported chain candidates, not Robinhood hardware test results.

## GoldHEN boundary

GoldHEN binaries are **not bundled**. The host reads `goldhen-builds.json` and exposes a firmware-specific source link. Official GoldHEN v2.4b18 explicitly lists 11.00. The community EEJTek v2.4b18.12 repository claims a wider firmware matrix, including 13.52, but is not an official GoldHEN release; its binary provenance is not independently established here. Treat that as an optional community candidate, not a verified official build. Never rename an unrelated payload to `goldhen.bin`.

## Licensing

WebKitty is AGPL-3.0-or-later. Its original LICENSE file is preserved in the deployed `webkitty/` directory. Robinhood must preserve copyright notices, offer the corresponding source, and mark modifications if any are made to the upstream code.

## Validation still required

1. The Pages workflow validates the pinned runtime files, firmware catalog, GoldHEN provenance metadata and host links on pull requests; it deploys only `main`.
2. On each target PS4 firmware, run the matching cache page and verify the AppCache reaches `cached` or `noupdate`.
3. Test each chain on real hardware, record console model and exact firmware, and retain logs.
4. Before any GoldHEN binary is mirrored or auto-loaded, verify its exact source artifact, firmware support statement and SHA-256.
5. Keep automatic payload execution locked until those checks and hardware tests are complete.


## Host navigation

Robinhood's firmware profile includes a top-level **Open WebKitty Runtime** link. It deliberately opens the pinned upstream host as a top-level page rather than embedding the exploit runtime in an iframe, preserving the upstream page's browser context and relative asset paths. The selected firmware is shown in Robinhood's route log; confirm the exact firmware again in WebKitty before starting an exploit.
