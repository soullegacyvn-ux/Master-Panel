# Master Panel 2.0.0

A compact Windows control panel built around everyday use of the GPD Win 5.

[Download the Windows EXE](https://github.com/soullegacyvn-ux/Master-Panel/releases/download/v2.0.0/Master-Panel-v2.0.0.exe) · [Release and ZIP](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v2.0.0) · [Quick start](QUICK-START.txt)

Run the app, then press the physical **Keyboard/Mouse ↔ Gamepad Swap button** to
open or hide it. Navigate with the controller immediately; release held inputs
first. **Open with Windows** starts the panel at sign-in and restores saved controls.

## Controls

- TDP adjustment, measured CPU draw, supported CPU Boost and fan presets/curves.
- Matching Brightness/Night light cards, temperature +/- and native schedule.
- Natural/Vivid/Soft/OLED color profiles, applied to the supported AMD display
  driver and remembered for the next app start. Five-second Save/Cancel for edits.
- Customize: 19 vector telemetry widgets as Cards, three gray styles, seven accents,
  width and saved widget arrangement. GPU load can be selected in Master and RTSS.
- Front/rear controller mapping with local profiles, Temporary RAM and reviewed
  Permanent storage, backups, firmware checks and readback.
- RTSS overlay and Handheld layout; Windows audio, volume +/- and compatible FxSound EQ.
- Battery/plug status, percentage and available charging W/A/time estimates.

## Install or update

Exit the old copy from the tray, keep the new EXE in a fixed folder and run as
Administrator. WebView2 is required for the UI and PawnIO for hardware control.
RTSS and FxSound are optional separate installs. Saved fan restoration is built in.
Enabled startup schedules repair moved EXE paths. Enable Open with Windows for
color profile restoration at sign-in; no new service is installed for display colors.
Lossless Scaling integration remains removed.

Portable tests, color-profile race/failure/restart checks, JS handler mocks, HTML
structure, Windows vet and compilation pass. The build Mac cannot execute Windows
or Win 5 hardware; new layout/startup color restore and native device integrations
need device testing. Battery charging estimates use the current rate. BIOS and
battery charge limits are not changed by the app.

## Source and notices

This repository contains release documentation. GitHub's automatic Source code
archives contain that documentation, not the Master Panel application source.
Included notices and corresponding module source are available in
**Settings → Third-party licenses**.

Powered by Vincent · Support: mythvietnamese@gmail.com
