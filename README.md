# Master Panel 1.2.0

A compact Windows control panel built around everyday use of the GPD Win 5.

[Download the Windows EXE](https://github.com/soullegacyvn-ux/Master-Panel/releases/download/v1.2.0/Master-Panel-v1.2.0.exe) · [Release and ZIP](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v1.2.0) · [Quick start](QUICK-START.txt)

Run Master Panel, then press the Win 5's physical **Keyboard/Mouse ↔ Gamepad
Swap button** to open or hide it. Controller navigation is intended to work
right away, without clicking or touching the panel. Release held buttons and
sticks before navigating. Ctrl + Alt + Space and the tray menu also work.

## Controls

- TDP presets and slider, supported CPU Turbo Boost, fan presets/manual curves.
- Brightness and supported AMD display colors, with local display profiles.
- Front/rear controller mapping, local profiles, Temporary RAM and confirmed
  Permanent storage with backups, firmware checks and readback.
- RTSS overlay with an optional Handheld layout and aligned metric columns.
- Windows audio and a separately installed compatible FxSound version.
- Battery percentage, net charging W/A and time estimates in Performance,
  where the Windows battery driver supplies valid physical readings.

Settings uses a simple **Open with Windows** checkbox. Saved fan restoration
and the device keyboard button are built-in. Lossless Scaling integration
and OpenWinControls shared-profile controls are removed in this release.
Separate installed apps and old preference files are not deleted.

## Update

Exit the previous copy from the tray, put the new EXE in a fixed folder, and
run it as Administrator. Enabled startup schedules repair their EXE path after
an update. Microsoft WebView2 is required for the UI; hardware control needs
PawnIO. RTSS and FxSound are optional separate installs.

This update is based on 1.1.1. Portable regression tests, UI handler mocks,
race checks, Windows compilation and EXE/resource inspection pass. The build
host cannot execute Windows or GPD hardware; native focus, brightness, HID
flash and FxSound/RTSS behavior still require testing on the Win 5. Time to
full uses the current battery charge rate and may change as charging slows.

## Source and notices

This repository contains release documentation. GitHub's automatic Source
code archives contain that documentation, not the Master Panel application
source. Included third-party notices and corresponding module source are
available in **Settings → Third-party licenses**.

Powered by Vincent · Support: mythvietnamese@gmail.com
