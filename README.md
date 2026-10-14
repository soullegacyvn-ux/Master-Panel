# Master Panel 1.1

A compact control panel for the GPD Win 5 on Windows.

[Download for Windows](https://github.com/soullegacyvn-ux/Master-Panel/releases/latest) · [Website](https://master-panel-win5.bloomy-oasis-8003.chatgpt.site)

- See temperatures, fan speed, battery and power draw. Choose the widgets you need.
- Adjust TDP with a slider or six editable presets: 8, 18, 24, 28, 38 and 45 W.
- Choose a fan preset, manual speed or a custom curve. Saved fan and power settings return when the hardware is ready at startup.
- Tune brightness and supported AMD color controls; save display profiles.
- Map front and rear controls, save profiles and share compatible YAML profiles with OpenWinControls. Choose outputs first; Flash applies the draft. Temporary and firmware-gated permanent storage are available where supported.
- Customize the live RTSS overlay. Start or toggle your installed Lossless Scaling over a game; apply 2× or 3× over a running game. Supported Tune profiles reload LS in the background.
- Control Windows audio and a compatible, separately installed FxSound version.

## Open the panel with Swap

Run Master Panel, then press the physical **Keyboard/Mouse ↔ Gamepad Swap button** on your Win 5 to show the panel. Press it again to hide. The button still switches the controller mode; the app must be running. **Ctrl + Alt + Space** and the tray menu’s **Show** action also work.

Enable **Settings → Open with Windows** to start in the tray at sign-in. Keep the EXE in a fixed folder and check the startup schedule after updating.

## Lossless Scaling while playing

You can enable frame generation after opening the game. Use Borderless or Windowed mode, press Swap, select its matching LS profile in Tune, then press **Apply 2×** on Master. Your game stays open while LS reloads minimized.

Set up your purchased Windows copy of LS once: use a matching profile with Auto Scale on, or configure its scaling shortcut. If LS closes to its tray, exit it there before applying again. Enable **Draw FPS** in Tune to see LS output; RTSS reports the original game FPS. Profile Tune exposes 40 recognized fields; native LS remains available for app preferences and unsupported variants.

## Windows setup

Download the EXE and run it as Administrator. Hardware sensors, TDP and fan control need the separately installed PawnIO driver. The panel uses Microsoft WebView2. RTSS, Lossless Scaling and FxSound are optional and are not included.

The app stores settings locally. **Report a problem** creates a local diagnostic ZIP that you can send to support yourself.

## Performance

Use a TDP your game needs and leave GPU headroom for frame generation. Available power ranges follow the detected Win 5 model and power source. Cooling falls back to firmware Auto when required sensor readings are lost.

## Distribution

This repository contains release documentation, not the Master Panel application source. Third-party licenses and corresponding module source accompany the EXE and can be saved from **Settings → Third-party licenses**. Earlier distributions keep their original licenses.

The owner reports the 1.0.4 base working on their 64 GB / 2 TB Win 5. Release 1.1 passed portable logic/UI mock checks and Windows build inspection. The build environment cannot execute Windows or test hardware; the new 1.1 quick-action flow has not been tested on a device here.

Powered by Vincent · Support: mythvietnamese@gmail.com
