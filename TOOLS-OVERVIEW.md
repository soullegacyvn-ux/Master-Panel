# Tools Overview — 3.3.4

The accepted compact Overview is part of the shared offline page. Both the
desktop and Xbox Game Bar call the same four native bindings: `refreshTools`,
`saveSleepPolicy`, `setDownloadMode`, and `reduceMemory`. Existing per-view
interaction checks and controller focus rules apply. No second utility engine
or UI-owned background task exists.

## Sleep → Hibernate

An explicit enable saves separate battery and AC timeout indices using documented
PowrProf APIs and the Windows HIBERNATEIDLE setting. The default is off, 15 minutes
on battery and 30 minutes on AC. An enable request can enable Windows hibernation
when needed; unsupported sleep states fail visibly. Zero AC disables the fixed plugged-in hibernate timer. Master Panel stores original indices before any write, verifies the
result and restores only values it still owns when disabled. The Windows policy
continues after the panel exits; there is no timer trying to run during sleep.

## Download Mode

Start applies a temporary stable 8 W APU TDP through the existing verified SMU
controller, without changing the user's saved TDP preference. It temporarily
disables idle sleep and timed hibernation on the active power plan, holds Windows
SystemRequired/ExecutionRequired requests, and optionally turns off the screen
after two seconds. On battery with Modern Standby, the display stays on instead:
Windows limits screen-off execution there. Unplugging switches to display-required
mode within 15 seconds. Fan policy, display brightness and volume are unchanged.

The mode ends manually or after 30/60/120 minutes; two hours is the initial option.
Stop restores the previous TDP within the current source ceiling and restores
owned Windows policy. A newer external TDP/policy edit is preserved. Manual
Windows sleep or app exit stops the mode. Crashes release power-request handles;
startup restores the interrupted power policy and uses existing TDP recovery.
An external power-plan/policy change stops the mode on the next 15-second check.
The automatic updater cannot interrupt an active utility transaction or download.

8 W is a TDP cap, not a measurement of battery or wall power. This mode does not
detect download completion from network silence and does not download in S3/S4. Screen-off mode on battery is limited to traditional sleep PCs.

## Memory Reduce

The explicit Reduce button invokes the documented K32EmptyWorkingSet API only for
background processes owned by the current user/session. Visible window families,
Windows processes, game library processes, Game Bar, RTSS and FxSound are excluded.
An active RTSS game blocks the action. No process is terminated. The UI reuses the
existing RAM telemetry and reports a processed count without claiming guaranteed
freed RAM or higher FPS. There is no automatic memory cleaner or undocumented
standby/modified-list purge.

## References and validation

- [Windows hibernate timeout](https://learn.microsoft.com/en-us/windows-hardware/customize/power-settings/sleep-settings-hibernate-idle-timeout)
- [Power request behavior](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-powersetrequest)
- [Windows power capabilities](https://learn.microsoft.com/en-us/windows/win32/api/winnt/ns-winnt-system_power_capabilities)
- [EmptyWorkingSet](https://learn.microsoft.com/en-us/windows/win32/api/psapi/nf-psapi-emptyworkingset)

Portable policy tests cover durable journals, partial writes, crash recovery,
outside edits, plan switching and process-family exclusions. Windows engine tests
use fake hardware for temporary 8 W, saved preference preservation, source caps,
external TDP changes and update/action exclusion. Node VM checks use shipped UI
handlers for drafts, synchronization, focus-node retention and recovery controls.
Actual Win 5 sleep timing, screen-off downloads and resume still need hardware
testing; software release checks do not replace these on-device checks.
