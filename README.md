# Master Panel

A compact control panel for the GPD Win 5 on Windows.

[Download for Windows](https://github.com/soullegacyvn-ux/Master-Panel/releases/latest) · [Website](https://master-panel-win5.bloomy-oasis-8003.chatgpt.site)

- See temperatures, fan speed, battery and power draw. Choose the widgets you need.
- Adjust TDP with a slider or six editable presets: 8, 18, 24, 28, 38 and 45 W.
- Choose a fan preset, manual speed or a custom curve. Saved fan and power settings return when the hardware is ready at startup.
- Tune brightness and supported AMD color controls; save display profiles.
- Map front and rear controls, save profiles and share compatible YAML profiles with OpenWinControls. Choose outputs first; Flash applies the draft. Temporary and firmware-gated permanent storage are available where supported.
- Customize the live RTSS overlay. Start or toggle your installed Lossless Scaling over a game; choose 2× or 3× while that app is closed.
- Control Windows audio and a compatible, separately installed FxSound version.

## Windows setup

Download the EXE and run it as Administrator. Hardware sensors, TDP and fan control need the separately installed PawnIO driver. The panel uses Microsoft WebView2. RTSS, Lossless Scaling and FxSound are optional and are not included.

The app stores settings locally. **Report a problem** creates a local diagnostic ZIP that you can send to support yourself.

## Performance

Use a TDP your game needs and leave GPU headroom for frame generation. Available power ranges follow the detected Win 5 model and power source. Cooling falls back to firmware Auto when required sensor readings are lost.

## Distribution

This repository contains release documentation, not the Master Panel application source. Third-party licenses and corresponding module source accompany the EXE and can be saved from **Settings → Third-party licenses**. Earlier distributions keep their original licenses.

The 1.0.0 build passed static and model checks. This build has not been executed on Windows or tested on a physical GPD Win 5 by the build environment.

Powered by Vincent · Support: mythvietnamese@gmail.com
