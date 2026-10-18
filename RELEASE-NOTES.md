# Master Panel 3.3.0

Tools Overview is available in both the desktop panel and Xbox Game Bar widget.

- Sleep -> Hibernate: separate battery and plugged-in Windows timeouts.
- Download Mode: temporary 8 W APU TDP, optional display behavior and stop timer; restores the previous limit when stopped. On Modern Standby battery, the screen stays on to keep downloading.
- Memory Reduce: manual trimming of eligible background-process working sets.
- Shared state and native control engine for both views. Download Mode blocks conflicting TDP actions and automatic restart for updates.

Update in Settings -> Updates to install the matching desktop app and widget together. Saved settings are retained. For manual installation, exit Master Panel from the tray and run Master-Panel-v3.3.0-Setup.exe.

8 W is APU TDP, not total device power. Automated Windows checks do not replace physical Win 5 sleep/resume, controller and hardware testing. No BIOS or battery charge-limit writes are added.
