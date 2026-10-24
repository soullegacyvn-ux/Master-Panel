# Master Panel 4.0.0 — Windows stability

The panel and Game Bar widget use the same controls and state. This release focuses on startup power ceilings, responsive audio, view handoff and recovery.

- Constrain an already restored high DC target when the first telemetry sample discovers battery/USB power.
- Keep volume/mute responsive while FxSound status is delayed; bound and back off failed status requests.
- Reject deferred controller actions across focus loss, close and reactivation.
- Retry failed cleanup of Master-owned RTSS output and recover stale own slots on a saved-Off startup.
- Add explicit read-only RTSS slot, statistics and loaded-module diagnostics.
- Keep matching panel/widget installation and saved settings during package updates.
- Refresh the Master TDP control with compact setpoint/CPU draw readouts, restrained inactive modes and a clear active range.

Exit the old panel and run Master-Panel-v4.0.0-Setup.exe, or use the in-app stable updater when available. A normal upgrade retains user settings.

Windows CI software validation and physical GPD Win 5 testing are distinct. Winhanced's own boot overlay behavior and real LSFG display metrics are not proven fixed by this package. No Winhanced service or foreign RTSS output is disabled automatically.
