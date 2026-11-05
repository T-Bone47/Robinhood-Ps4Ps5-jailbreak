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

GoldHEN is **not included** by this integration. The upstream GitHub release notes for v2.4b18 list support through 11.00, while newer firmware support claims require separate provenance and validation. Do not map a GoldHEN binary to 11.02–13.52 without a release artifact whose support statement covers that exact firmware. Never rename an unrelated payload to `goldhen.bin`.

## Licensing

WebKitty is AGPL-3.0-or-later. Its original LICENSE file is preserved in the deployed `webkitty/` directory. Robinhood must preserve copyright notices, offer the corresponding source, and mark modifications if any are made to the upstream code.

## Validation still required

1. Confirm the GitHub Pages build contains the entire `webkitty/` directory.
2. On each target PS4 firmware, run the matching cache page and verify the AppCache reaches `cached` or `noupdate`.
3. Test each chain on real hardware, record console model and exact firmware, and retain logs.
4. Verify any user-supplied GoldHEN binary by source provenance and SHA-256 before adding it to a firmware-specific payload mapping.
5. Keep Robinhood execution controls locked until the above evidence is recorded.
