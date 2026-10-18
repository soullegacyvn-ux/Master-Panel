# Master Panel 3.2.1 source audit

Compared with the supplied 3.2.0 application snapshot. The review covers the active Go engine, embedded shared UI, native widget bridge, UWP host, update/install flow, dependencies and release packaging. This is a software audit; it cannot certify every hardware behavior.

## Fixed

- **Recovery durability:** a failed recovery-journal save previously logged an error but allowed a TDP write. Applying a target now stops before writing when its recovery cannot reach disk, and retains the previous in-memory intent. Confirmed readback remains authoritative if later cleanup fails.
- **Service lifecycle:** queued service stops could outlive shutdown recovery, duplicate actions could overlap, and an uncertain stop lost its recovery entry. Actions are tracked, serialized with exit recovery, rejected during package restart, and retain a journal until resume succeeds. Already-stopped/running Windows service states are handled as success.
- **Telemetry:** the sampler repeated the fan worker's temperature and EC reads using the original handles. It now consumes the coherent fan snapshot, including reconnected handles, and rejects readings older than three seconds. The 500 ms fan control loop, hot-temperature protection and Auto fallback remain active.
- **UI work:** removed duplicate TDP rendering in each state poll. Unchanged sliders no longer rewrite CSS; EQ SVG nodes are retained until plot data, selection or width changes. Single-value sliders avoid division by zero.
- **Bridge work:** RPC success replies encode once, while serialization errors still produce an error envelope. The immutable embedded page is assembled once per process; removed a duplicate state-slice copy. UWP request objects are disposed on success, retry and exception.
- **Audio work:** a periodic FxSound status refresh is reused by the same low-volume observation rather than immediately invoking the CLI again. Existing mute, endpoint-switch and boot-volume protection remain in place.

## Cleanup and dependencies

Removed the unused internal/lossless package (21 files, 114,328 bytes), external ../deps replacements, the obsolete widget-only workflow and its historical patch file. Lossless Scaling was already absent from the running app, so deleting its source alone does not reduce runtime memory.

Production builds use Go 1.27.2. x/sys is updated from 0.37.0 to the first fixed version 0.44.0 for [GO-2026-5024](https://pkg.go.dev/vuln/GO-2026-5024). The old dependency was present, but the source scanner did not identify a call to its affected function. The final Windows amd64 source scan reports zero known vulnerability findings against the retrieved Go database. This does not prove the absence of unknown vulnerabilities.

The embedded third-party notices were brought up to date with the shipped dependency metadata and existing controller attribution; a regression checks them against the source notices and license bytes.

The existing vendored WebView2 asynchronous RPC and shutdown-drain patches, and all winloader bytes, were preserved exactly. Do not blindly regenerate the entire vendor directory: those local patches are part of the application.

## Verification and limits

Portable Go tests with the race detector, Windows vet, active Node VM suites and a Windows amd64 cross-build are run locally. The release CI runs Windows-only unit tests, .NET controller checks, publisher hash checks, native/UWP builds, Program Files install/bridge/uninstall and actual package-helper upgrades from 3.0.2, 3.1.0 and 3.2.0. The 3.0.1 test models its initial EXE swap before the full-package helper. The published CI result and checksums identify the completed gates.

Regression tests cover failed recovery saves without hardware writes, queued service close ordering, failed stop recovery, service/update exclusion, fresh/stale shared sensor data, single-encode RPC replies, unchanged slider/EQ rendering and changed EQ/width repainting. Older 0.x–2.x prototype QA fixtures remain historical references; the active gates are listed in qa/README.txt.

No measured CPU/RAM/battery-saving percentage is claimed. Physical Game Bar controller focus, controller flash/vibration persistence, fan/display/audio effects, reboot/sleep recovery and sustained high-power operation still require the GPD Win 5. Existing source-specific TDP ceilings, caution boundaries and 45 W/lower-cap reset policy remain unchanged.
