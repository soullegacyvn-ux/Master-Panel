# Master Panel 4.0.0

Windows control panel and Xbox Game Bar widget for GPD Win 5.

[Windows installer](https://github.com/soullegacyvn-ux/Master-Panel/releases/tag/v4.0.0) · [Quick start](QUICK-START.txt) · [Stability and validation](STABILITY.md)

The desktop panel and widget share one hardware engine and saved settings. Use the physical Keyboard/Mouse ↔ Gamepad Swap button for the desktop panel, or Win+G → Widgets → Master Panel.

## What changed

- Apply source ceilings on the first telemetry sample too, including a DC-to-battery change during boot recovery. Plugging in does not raise the chosen TDP; Reset remains 45 W or the lower active ceiling.
- Separate slow FxSound status work from Windows volume/mute controls, with one serialized FxSound request and failure backoff.
- Discard deferred widget actions and controller samples after view ownership changes.
- Retry failed cleanup of Master Panel's own RTSS output, including a saved-Off startup after a crash; stop retry writes once cleanup succeeds.
- Record bounded, read-only RTSS slot and loaded-plugin diagnostics on Check connection. Other applications' output is preserved.
- Refresh the shared Master TDP control with compact readings, a cold-to-hot mode scale and a complete focus outline; adapt metric cards to narrow panels.

The release retains AMD Custom Color, Night light, fan controls, controller mapping/vibration, configurable Master cards, optional FxSound, RTSS typography, shared Lossless Scaling controls and Tools Overview. Gyro remains removed.

## Install or update

Exit the previous Master Panel from its tray menu, then run **Master-Panel-v4.0.0-Setup.exe**. Setup installs the matching desktop panel and widget in **C:\Program Files\Master Panel** and retains user settings. No uninstall is needed for a normal upgrade.

In-app updates use **Settings → Updates → Check for updates → Download → Update & restart** when the release is available on the stable channel. The complete package updates both views.

WebView2 is required for the full UI. PawnIO is required for supported hardware controls; RTSS, FxSound and Lossless Scaling are optional. Settings → Components opens official component installers. Lossless Scaling is purchased separately through Steam.

The widget uses the included self-signed public certificate and local loopback access. No private signing key is distributed. The installer has no commercial code-signing certificate.

## Validation and limits

See VALIDATION-4.0.0.txt and the matching accepted Windows CI run for the exact software checks. Physical Win 5 controls, game rendering and Winhanced boot coexistence require device verification. A successful generic Windows build does not prove those outcomes.

Winhanced may use RTSS independently of Master Panel. Master Panel does not disable its background services or erase its overlay. A duplicate overlay that returns at boot needs a diagnostic captured while it is present.

No BIOS or battery charge-limit writes are added. Firmware can enforce lower power limits.

## Source and notices

The public release repository contains binaries and documentation; GitHub's automatic source archives contain that documentation. The complete application source is supplied separately to the owner. Third-party notices are available in Settings → Third-party licenses.

Powered by Vincent · mythvietnamese@gmail.com
