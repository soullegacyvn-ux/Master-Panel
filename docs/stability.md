# Master Panel 4.0.0 stability

## Runtime ownership

One desktop engine owns supported hardware and serves both desktop and Game Bar views. View activation leases gate controls. Deferred requests from an earlier activation are rejected. Hidden interfaces stop their UI polling; hardware safety continues independently.

The fan worker maintains its coherent fresh sensor cache independently of optional display/audio/overlay integrations. General telemetry reuses that cache. Curves and manual fan control require valid recent readings and surrender to EC Auto after sensor loss, prolonged stall, external ownership changes or resume. Firmware remains responsible before sign-in and after forced process termination.

## Power recovery

TDP changes validate the active source ceiling, save recovery before mutation, verify hardware readback and attempt rollback on failure. Source changes constrain an existing target even on the first telemetry sample after boot recovery. Plugging in does not raise the target. Reset chooses 45 W or a lower configured active ceiling with boost off. A failed reduction is shown as failed; firmware-limited writes are not reported as successful.

Unknown or unreadable recovery records block unsafe writes. Interrupted controller permanent writes keep their journal for explicit recovery; they are not replayed blindly. No BIOS or battery charge-limit writes are added.

## Audio and view handoff

Slow external FxSound requests are serialized independently of Windows playback controls. Status polling is bounded and backs off on failures. Deferred controller actions require their original view activation. Late FxSound replies cannot undo a newer volume/mute choice. Saved endpoint and duplicate-processor guards remain in effect.

## Overlay and FPS

Only one Master publisher serves both views. Failed cleanup of its owned RTSS slots remains pending and is retried; successful cleanup stops idle write retries. Other clients are preserved. Global RTSS settings modified by Master are backed up and restored only while their ownership receipt remains valid.

Check connection captures bounded slot metadata, per-profile statistics flags and observed loaded plugin basenames. An owner or module name alone is not proof of who publishes a specific bar. Master does not kill Winhanced services or erase foreign output to force takeover. Winhanced boot coexistence is a device test, not a generic CI guarantee.

External LSFG display FPS uses actual measurements when available, never an FPS multiplier estimate. Missing original/display data remain independently unavailable. The PresentMon helper runs only for an active supported LS session with the saved FPS field enabled and is stopped when no longer needed.

## Release acceptance

The required Windows workflow exercises Go tests/vet, native SDK oracles, bridge/controller/UI regression cases, original-user elevated launch, Program Files install/uninstall and complete package updates retaining user settings. Portable race tests supplement native Windows checks.

Generic hosted Windows checks cannot validate GPD EC/SMU behavior, permanent vibration/remap persistence, real game rendering, actual hardware power consumption or the user's Winhanced startup. CPU/RAM/FPS overhead must be measured on a real Win 5. See the accepted build logs and [4.0.0 validation](validation/VALIDATION-4.0.0.txt) for scope.

## Support

Settings → Report a problem creates a local bounded diagnostic ZIP. Reports exclude mapping/recovery raw backups and WebView profile data; no automatic upload occurs. For RTSS duplicates, capture Check connection while the unwanted overlay is actually present.
