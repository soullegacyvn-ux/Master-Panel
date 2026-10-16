# Master Panel 3.0.0

A compact Windows control panel built around everyday use of the GPD Win 5, now with an Xbox Game Bar widget.

[Download the Windows app + widget](https://github.com/soullegacyvn-ux/Master-Panel/releases/download/v3.0.0/Master-Panel-v3.0.0-Windows.zip) · [Release and individual downloads](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v3.0.0) · [Quick start](QUICK-START.txt)

Extract the full ZIP, exit the old app from the tray, and run **Install.cmd** to update both the desktop app and widget to 3.0.0. Press the physical **Keyboard/Mouse ↔ Gamepad Swap button** for the desktop panel. Press **Win+G → Widgets → Master Panel** for the widget. The widget uses **LT/RT** to switch tabs; the desktop panel uses **LB/RB**. Release held inputs after opening or changing focus.

## One app, two views

The desktop panel and widget share one hardware engine, settings and telemetry. An inactive view discards unsubmitted edits, and the view you return to refreshes the shared state before accepting new changes. Hidden views stop frequent input and live-preview polling.

3.0.0 fixes widget fan preset highlighting and the mapping picker closing early, adds controller navigation inside the widget, and refreshes the MP logo and icons across both views. A dedicated **Gyro** tab offers a motion preview, calibration, trigger activation, sensitivity, smoothing, deadzone and axis settings. Gyro starts **off**; preview alone does not move the mouse.

## Controls

- TDP adjustment with a draggable limit and measured CPU draw. On detected DC, the 395 model can select up to 85 W and the 385 up to 75 W. Battery stays capped at 55 W and USB-C at 40 W. The 65 W+ range is vivid orange with a caution symbol. Adapter and firmware capabilities still matter.
- CPU Boost, fan presets and custom fan curves, with saved mode restoration.
- Brightness, Night light temperature/schedule, and saved Natural/Vivid/Soft/OLED display profiles. Profile edits have a five-second Save/Cancel confirmation.
- Customize: vector telemetry cards, three gray styles, seven accents, panel width and saved widget arrangement. CPU/GPU load, temperatures and available battery/charging data are selectable.
- Front/rear controller mapping, local profiles, Temporary RAM and reviewed Permanent storage, backups, firmware checks and readback.
- RTSS overlay, Windows volume controls and compatible FxSound EQ. RTSS and FxSound are optional separate installs. Lossless Scaling integration remains removed.

## Install requirements and validation

Windows x64, WebView2 for the UI, PawnIO for supported hardware control, and Xbox Game Bar for the widget. Enable **Open with Windows** to start at sign-in and restore saved controls. Replacing only the EXE does not update an older installed widget; use the full ZIP for this upgrade.

The widget is sideloaded using the included self-signed certificate. Its installer trusts that certificate locally and enables the widget's loopback connection to the app. The package includes install/uninstall scripts and a validation report.

Portable race tests and Windows software tests, controller-policy checks, native compilation, widget packaging, installation registration and the real app bridge are checked during the build. These checks do not validate physical Win 5 hardware or interaction inside a real Game Bar session. Gyro orientation/aiming, Game Bar controller focus and selected toolbar appearance, fan/flash/display/audio behavior and sleep/resume need device testing. No BIOS or battery charge-limit writes are added.

## Source and notices

This public repository contains release documentation. GitHub's automatic **Source code** archives contain that documentation, not the Master Panel application project. Included notices and corresponding module source are available in **Settings → Third-party licenses**.

Powered by Vincent · Support: mythvietnamese@gmail.com
