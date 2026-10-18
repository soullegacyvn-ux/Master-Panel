# Master Panel 3.3.2

Fixes TDP range behavior and hardens FxSound sharing between the desktop panel and Xbox Game Bar widget.

- Defaults the slider ceiling to 85 W on battery and 100 W on DC. Legacy 55/85 W (and 55/75 W) default pairs migrate to the new range; custom ceilings remain. Newly saved lower ceilings are preserved.
- Saving a ceiling updates both TDP sliders and checks fresh engine readback. Battery Caution starts above 65 W; DC Caution starts above 85 W. Caution does not block an explicit target inside the saved range. Reset remains 45 W, or the lower source ceiling.
- FxSound detection and commands use the current user/session. Automatic widget activation reuses an existing owner; new launches use the normal user context instead of inheriting the elevated hardware host. Persistent duplicate owners are reported instead of receiving more commands; short-lived CLI forwarding helpers are not counted as duplicate processors.
- Retains the 3.3.1 Modern Standby detection fix.

Update both views from Settings → Updates. Stop Download Mode and close games before Update & restart. Manual fallback: exit the app from its tray menu and run Master-Panel-v3.3.2-Setup.exe.

The user's delayed/duplicated audio has not been reproduced on Win 5 here. The process-sharing changes address a possible cause; actual audio after switching Xbox/desktop modes and physical high-TDP readback still require on-device testing. Firmware can enforce lower limits. USB-C and unknown supply retain their separate limits.
