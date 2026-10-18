# Master Panel 3.3.1

Fixes incorrect Sleep detection on Modern Standby PCs, including the user's Win 5 with S0 Low Power Idle and Hibernate available.

- Reads the Windows SDK power capability structure by named fields. The 3.3.0 reader used the wrong byte for the AoAc / Modern Standby flag and could show “Windows exposes no supported sleep state”.
- Correct detection also restores the intended screen-on protection for Download Mode on Modern Standby battery.
- Adds byte-level regression fixtures and an independent native Windows SDK layout/runtime check.

Update from Settings → Updates. The desktop panel and Xbox Game Bar widget update together and retain saved settings. Stop Download Mode and close games before Update & restart. For manual installation, exit the app from its tray menu and run Master-Panel-v3.3.1-Setup.exe.

Sleep -> Hibernate timing/resume and real screen-off download behavior still require on-device testing. No BIOS, firmware or driver changes are made by this fix.
