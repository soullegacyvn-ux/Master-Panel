# Sources and third-party notices

Master Panel is distributed under **GPL-3.0-or-later** (see LICENSE).

| Component | Use | License |
|---|---|---|
| [libOpenWinControls](https://github.com/OpenWinControls/libOpenWinControls), © 2026 kylon | V2 controller protocol, key tables and generated reset buffers in internal/v2proto; writing/flash routines ported from ControllerV2.cpp. The RAM/flash command paths were reviewed against commit 036035b042c9bf6ba787773bfe28e61f6bafb855; permanent commits are restricted to Win5 firmware 1.12 with backup, readback and a durable recovery journal. | GPL-3.0-or-later |
| [OpenWinControls](https://github.com/OpenWinControls/OpenWinControls) | Compatible YAML profile key names | GPL-3.0-or-later |
| [PawnIO.Modules](https://github.com/namazso/PawnIO.Modules) 0.2.9 | Signed RyzenSMU.bin, AMDFamily17.bin and LpcIO.bin modules embedded in internal/win/pawnio/modules | LGPL-2.1-or-later |
| [PawnIO](https://pawnio.eu) | User-installed driver, accessed through IOCTL | GPL-2.0+ with the IOCTL application exception |
| [golang.org/x/sys](https://github.com/golang/sys) v0.37.0 | Windows API bindings in vendor | BSD-3-Clause |
| [go-webview2](https://github.com/jchv/go-webview2) 5659883, © 2020 John Chadwick, portions © 2017 Serge Zaitsev | WebView2 window; vendored webviewloader/module.go is patched to exclude the executable directory from DLL search in this elevated app; webview.go adds a hidden initial-window option for startup in tray and dispatches native RPC work to background workers so scheduler/driver waits do not block the panel, with new-call rejection, dialog cancellation and worker draining before resource teardown; 0.7.4 fixes signed HRESULT/nil initialization checks, bounded retries, safe late callback cleanup and verified COM callback identities | MIT |
| [go-winloader](https://github.com/jchv/go-winloader) c1995be, © 2021 John Chadwick | In-memory WebView2Loader fallback | ISC |
| WebView2Loader.dll 1.0.992.28, Microsoft WebView2 SDK | Signed loader embedded via go-webview2 | BSD-3-Clause, © Microsoft Corporation; see LICENSE-WebView2SDK.txt |
| [Be Vietnam Pro](https://github.com/bettergui/BeVietnamPro), © 2021 The Be Vietnam Pro Project Authors | Legacy font source retained for provenance; 0.7.4 uses the Windows UI font and does not embed this font | SIL Open Font License 1.1; see internal/ui/fonts/OFL-BeVietnamPro.txt |
| AMD Display Library SDK ABI declarations, © 2016–2022 Advanced Micro Devices | AdapterInfo, ADLDisplayInfo and color constants | MIT; see LICENSE-AMD-ADL.txt |

Hardware facts (register addresses, SMU commands and PM table offsets) were checked against these projects; their implementation code was not copied:

- Handheld Companion (CC BY-NC-SA 4.0): Devices/GPD/GPDWin5.cs and Processors/AMD/RyzenSmuService.cs.
- RyzenAdj (LGPL-3.0): lib/api.c and lib/nb_smu_ops.c.
- Handheld Daemon (LGPL-2.1): wincontrols2.py and adjustor.
- Linux kernel drivers/hwmon/gpd-fan.c (GPL-2.0+).
- LibreHardwareMonitor (MPL-2.0): Tctl and RAPL decoding.
- Panel de Control (GPL-3.0): Win5 TDP ranges and brightness readback.
- Handheld Companion: RTSSHooks64.dll export names for FramerateLimit.

The RTSS profile-property names and shared-memory protocol follow Unwinder SDK declarations/examples available in [RTSS_SDK_for_GC](https://github.com/icaros7/RTSS_SDK_for_GC), [rtss-cli RTSSInterface.h](https://github.com/xanderfrangos/rtss-cli/blob/main/RTSSInterface.h), and [RTSSTweaks SDK headers](https://github.com/jaxFF/RTSSTweaks/blob/master/thirdparty/rtss-sdk/Include/RTSSSharedMemory.h). Master Panel's bounds checks, locking and text-slot implementation were written independently. RTSS itself is not redistributed.

[MangoPeel](https://github.com/Gawah/MangoPeel) informed the metric/configuration UX; no plugin code was copied.

The AMD atiadlxx.dll driver is not redistributed. The app loads the system driver with NewLazySystemDLL when present.

Higgsfield generated outline drafts using images supplied by the user. The final embedded asset is an independently authored SVG UI illustration referencing the supplied rear photograph, style reference and draft geometry. It is not a measured technical drawing. Draft prompts/provenance remain in the working assets; the release source contains the final SVG and provenance.

## External integrations added in 0.7.0

FxSound is controlled through its documented [CLI/status interface](https://github.com/fxsound2/fxsound-app/blob/main/docs/COMMAND_LINE_OPTIONS.md). The original FxSound application is AGPL-3.0; no FxSound implementation, DSP, source or binary is copied into this build. The protocol validation and client are independently written. FxSound remains an independently installed external application.

Lossless Scaling remains the user's separately installed proprietary Steam application (app 993090). No LS/LSFG binaries or proprietary rendering code are redistributed; activation uses a configured shortcut and the Steam launch URI.

Touch Keyboard's GUID/interface facts are referenced from [GestureSign](https://github.com/TransposonY/GestureSign/blob/master/GestureSign.CorePlugins/TouchKeyboard/TouchKeyboard.cs) and Microsoft's Windows SDK. The hook, chord filter, release/focus guards and COM integration are independently written. ITipInvocation is undocumented; IFrameworkInputPane::Location is documented. No OSK binary is replaced. Core Audio follows Microsoft's COM interface declarations; no third-party audio library is included.

RTSS font and color/size/alignment protocol facts are referenced from the original OverlayEditor SDK sources redistributed in [RTSSTweaks](https://github.com/jaxFF/RTSSTweaks/tree/master/thirdparty/RTSSOverlayEditor); original sample code was not copied.

The legacy Master Panel app icon/mark was generated by Higgsfield (gpt_image_2_5, job 2f56fb15-b873-4238-9e80-4c6091cb522a). The unchanged original, exact prompt and provenance accompany the source. Only resizing and format/resource packaging were performed. The logo wordmark uses native English text. Product credit: Powered by Vincent; support: mythvietnamese@gmail.com.

Shared YAML key/format facts follow the pinned OpenWinControls BackButtonV2Widget exporter/importer and MainWindow profile handling. The strict subset parser, folder connector, byte-preserving updates and backups are independently written. OpenWinControls is not redistributed. The folder picker uses Microsoft IFileOpenDialog (FOS_PICKFOLDERS) on an STA worker thread.

WebView2 callback interface GUIDs in the 0.7.4 hardening were checked against Microsoft's official Microsoft.Web.WebView2 1.0.4258.31 NuGet SDK WebView2.h (SHA256 dff1e3181ec7ec203a34ef6efa966590e0ef0ba1a5c3fe3b69da6508c2f8a02e). Only interface identity facts are used; that newer SDK's loader/binaries are not redistributed. The existing signed loader remains unchanged.

0.7.5 adds guarded explicit WebView controller visibility and validates its HRESULT, with panel show/focus queued on the owning UI message loop. The existing base WebView interface is preserved.

## Current 1.2.2 additions

The active mark uses the user-supplied M image, preserved in assets. It was traced
to native vector geometry; only the outer circular region was thinned. SVG mask
coloring follows the panel gradient. Windows icon PNG frames are rasterized from
that final vector for resources. This is not the legacy Higgsfield icon.

Windows Night light's reverse-engineered typed schema and captured test fixtures
are referenced from [win-nightlight-cli](https://github.com/kvnxiao/win-nightlight-cli),
© 2025 Kevin Xiao, MIT (LICENSE-NightLight.txt). The bounded Go parser/transaction
client are independently implemented; no upstream helper binary is bundled.
Night light does not alter firmware or implement a separate color filter.

Lossless Scaling and shared OpenWinControls integration described in historical
notices above are removed from the current panel.

## Current 1.2.3 front artwork

The active front/Keyboard-Mouse device is a clean native SVG redrawn to the
user-supplied line-art (win5-front-reference.webp), with its proportions
and buttons retained. Geometry/projection provenance is included. The old
Higgsfield PNG remains a historical reference and is not embedded in the app.
The new metric/navigation icons are independently authored native SVG symbols.

1.2.4 private native assets: Rear SVG redrawn to supplied reference using the
shared Front silhouette; black M/rounded gray tile with Volt-highlight app/tray
resource; panel vector mask retained. New original Go GPU aggregation and PDH
code uses Windows APIs; no additional DLL/runtime is bundled.

## Xbox Game Bar widget (experimental, private build)

The widget in `xbox-widget/` follows the project layout, activation code and manifest proxy-stub registration of Microsoft's [XboxGameBarSamples](https://github.com/microsoft/XboxGameBarSamples) WidgetSampleCS (MIT License, Copyright (c) Microsoft Corporation). At build time it references the Microsoft.Gaming.XboxGameBar, Microsoft.NETCore.UniversalWindowsPlatform and Microsoft.UI.Xaml (WinUI 2, which brings Microsoft.Web.WebView2) NuGet packages under Microsoft's licenses; none of them is included in this source. The built widget package depends on the Microsoft.UI.Xaml 2.8 and VCLibs framework packages, installed from the build output. The full widget shows Master Panel's own page in the Microsoft Edge WebView2 Runtime that ships with Windows 11. Package-family-name derivation in `internal/widgetbridge/pfn.go` is checked against Microsoft's published family names. The widget images are rendered from the existing Master Panel mark by `xbox-widget/tools/make_assets.py`.

## 3.0.0 icons and gyro

The Power save battery/leaf SVG is the user-supplied Microsoft Fluent System Icons
`ic_fluent_battery_saver_24_filled` contour, recolored with currentColor. MIT,
Copyright (c) 2020 Microsoft Corporation; see LICENSE-Fluent-System-Icons.txt.
MP branding, the redrawn turbo bolt, headphone/gyro symbols and UI presentation
follow the user's supplied references. The Windows gyrometer integration is
original code using Windows API/ABI declarations; no sensor driver is distributed.
