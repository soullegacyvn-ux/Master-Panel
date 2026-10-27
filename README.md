![MasterPanel overview](media/masterpanel-overview.png)

# MasterPanel

Your game library and handheld controls, together on Windows.

**[Download MasterPanel 1.0.0.2](https://github.com/soullegacyvn-ux/Master-Panel/releases/latest)** · **[Join Discord](https://discord.gg/n2fD2jvjvz)** · **[Install guide](docs/releases/1.0.0.2.md)** · **[FAQ / FSE troubleshooting](docs/fse-troubleshooting.md)**

**MasterPanel 1.0.0.2 is available.** Download the Windows Setup package from Releases. The optional Windows gaming-home integration remains a developer preview.

## Why MasterPanel

MasterPanel brings the gaming experience together:

- **Performance-focused FSE.** Tune TDP, cooling and per-game profiles to optimize gameplay. FPS gains vary by game, device and settings.
- **Compact controls.** Panel and Widget share one control engine and saved settings, with the controls you need close at hand.
- **Device-aware support.** Includes GPD Win 5 and ONEXPLAYER X2 Mini Pro profiles. Available controls and hardware validation vary by device and firmware.
- **Easy to navigate.** Browse games and adjust settings through interfaces designed for controller, touch and desktop use.
- **Community inside FSE.** Meet MasterPanel players, manage friends and send invitations to play together from the launcher. Steam and Discord integrations are also in preview.
- **More to come.** Planned improvements cover the library, supported hardware and Community. Development priorities will follow testing and player feedback.

## One app, three interfaces

| Interface | Purpose |
| --- | --- |
| **Launcher** | Browse your game library in a controller-friendly fullscreen home. |
| **Panel** | Reach supported power, cooling, display, audio and controller settings. |
| **Game Bar Widget** | Open shared controls while playing with **Win+G**. |

Panel and Widget use the same control engine and saved settings. Hardware features depend on the device and firmware.

![MasterPanel fullscreen launcher](media/masterpanel-fse.png)

![MasterPanel control panel](media/masterpanel-panel.png)

## Install

1. Download the **Setup EXE** from the [stable release](https://github.com/soullegacyvn-ux/Master-Panel/releases/latest).
2. Exit the older Panel from its tray menu, then run Setup. A normal upgrade keeps your preferences.
3. Open Panel from its shortcut, or use **Win+G → Widgets → Master Panel**.

Windows 11 x64 is the intended platform. Hardware controls are device-specific; support and validation vary by model. WebView2, Xbox Game Bar and PawnIO support the relevant components; see the [quick start](docs/quick-start.txt).

The optional Windows gaming-home integration is a developer preview. Microsoft production authorization is pending.

**Missing Xbox mode or “Choose home app”?** Start with our [FSE setup and troubleshooting guide](docs/fse-troubleshooting.md), including an optional third-party tool for devices where Windows does not expose these settings.

## Community and support

[Join MasterPanel on Discord](https://discord.gg/n2fD2jvjvz) for help, game profiles and development updates. For a bug report, include the app version, device, power source and steps to reproduce it.

Use **Settings → Report a problem** for diagnostics. Review the report and share it only with your consent.

[Guides](docs/README.md) · [1.0.0.2 release notes](docs/releases/1.0.0.2.md) · [Historical validation](docs/validation/VALIDATION-4.0.0.txt)

## License

See [LICENSE](LICENSE) and [third-party notices](NOTICE.md). This public repository contains release documentation and product images; the application build workspace is separate.

**Powered by Vincent** · [Contact](mailto:mythvietnamese@gmail.com)
