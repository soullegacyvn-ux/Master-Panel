Fixes FxSound launching and replaces manual TDP ceiling entry with immediate presets in the desktop panel and Xbox Game Bar widget.

- FxSound can launch and receive commands through the verified, normal-user Windows desktop shell. This avoids the split-token access-denied path reported in 3.3.2. Existing FxSound ownership and duplicate-instance checks remain.
- Maximum TDP saves immediately: battery 65 / 75 / 85 W; DC 65 / 75 / 85 / 100 / 120 W. The engine updates only the chosen source and returns its saved state. Raising the ceiling never raises active TDP. Lowering it clamps a higher active target.
- Five shared modes: Power save 8–<18 W; Performance 18–<28 W; Turbo 28–<48 W; Extreme 48–<65 W; Caution from 65 W on both battery and DC. Caution warns without blocking a target within the selected range. Reset remains 45 W, or a lower source ceiling.
- Master uses the entire usable slider span, removes the 0 W/locked gray section and idle instructions, and adds brighter mode colors.
- Master metric cards show only icon, title and reading; all 19 metric types have distinct vector symbols.
- The widget has a smaller icon rail with Tools visible at short heights, direct accent coloring for the selected menu, and more compact Master presets/cards. Theme accents are more vivid; MP placement is optically adjusted.

Update both views from Settings → Updates. Stop Download Mode and close games before Update & restart. Manual fallback: exit Master Panel from its tray menu and run Master-Panel-v3.3.3-Setup.exe.

Physical Win 5 audio playback, high-power hardware readback and controller use still require on-device testing. The normal-user launch is tested with Windows process helpers; CI without a normal Explorer shell cannot replace a real split-UAC desktop test. Firmware and USB-C/unknown-source limits remain applicable.
