# FAQ: Xbox mode / Full Screen Experience

## Xbox mode or “Choose home app” is missing. What should I do?

**If your device does not expose Xbox mode / Full Screen Experience, the optional tool below may help enable it. It is not required when Windows already offers the feature.**

Panel and the Xbox Game Bar Widget have separate requirements; this guide concerns Windows FSE integration. Opening the launcher fullscreen on the desktop does not by itself mean Windows FSE is active.

### 1. Try Windows setup first

Update Windows and update **Xbox** and **Xbox Game Bar** through Microsoft Store, then restart.

Check **Settings → Gaming → Xbox mode** (called **Full screen experience** on some builds). On supported handheld configurations, **Choose home app** selects the installed gaming launcher; the startup option controls entry after sign-in. Other PC configurations can expose a simpler Xbox mode toggle instead.

See [Microsoft’s Xbox mode setup guide](https://support.microsoft.com/en-us/servicing/os/windows/docs/2025/10/windows-gaming-full-screen-experience).

### 2. Optional: enable missing FSE options

If the settings remain unavailable, consider the third-party [Xbox Full Screen Experience Tool by 8bit2qubit](https://github.com/8bit2qubit/XboxFullScreenExperienceTool).

Before proceeding, read its current compatibility requirements and warnings. It changes Windows configuration and is not a Microsoft utility; compatibility is not guaranteed. Back up important files and create a restore point.

1. Download the MSI from the [tool’s official Releases page](https://github.com/8bit2qubit/XboxFullScreenExperienceTool/releases/latest).
2. Install and open it, then choose **Enable Xbox Mode (FSE)**.
3. Follow its checks and restart prompts. Update Xbox and Game Bar from Microsoft Store afterward.
4. Reopen **Settings → Gaming → Xbox mode / Full screen experience**.

Follow the [upstream instructions](https://github.com/8bit2qubit/XboxFullScreenExperienceTool#-quick-start) if labels or requirements change. To undo the tool’s changes, use **Disable & Restore**, then restart.

This is an external download link only. MasterPanel does not bundle the utility or incorporate its code.

### 3. Select MasterPanel

Enabling Windows FSE and registering MasterPanel are separate steps.

If MasterPanel is listed under **Choose home app**, select it. Enable startup entry only if you want to enter FSE after signing in.

If Xbox is available but MasterPanel is missing, use the optional gaming-home/developer-preview registration in the MasterPanel installer, if included in your package. This preview requires Developer Mode and its separate permission prompts. It does not represent Microsoft production authorization. Enabling Windows FSE with an external tool does not grant that authorization or guarantee registration.

## Registration failed or Windows did not retain the selected home

Do not repeatedly reinstall the FSE-enabling utility when the Windows feature already exists. Report the registration failure instead.

Include the MasterPanel version, device model, Windows version/build from `winver`, the exact error, and whether **Choose home app** appears. If available, include the relevant entry from:

```text
%LOCALAPPDATA%\MasterPanelHome\FSEPreview\setup.log
```

Review diagnostic files before sharing them. Use MasterPanel’s report feature where available or contact [MasterPanel support on Discord](https://discord.gg/n2fD2jvjvz); avoid posting personal details in public issues.

[Back to documentation](README.md) · [Download MasterPanel](https://github.com/soullegacyvn-ux/Master-Panel/releases/latest)
