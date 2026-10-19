# Master Panel 3.3.4

Improves RTSS overlay coexistence and connects Display colors to AMD Custom Color in both the desktop panel and Xbox Game Bar widget.

- RTSS presets show their selected state, reload and synchronize across both views. Layout actions use the current shared configuration. Grid/Ribbon spacing avoids overlapping labels and values.
- Detects other RTSS providers, including modern 32KB text. Master Panel pauses its own overlay by default while another provider is active and resumes when it stops. Optional “Show alongside other overlays” allows explicit overlap. Stale slots owned by Master Panel are cleared; foreign providers remain untouched.
- RTSS diagnostics show the actual connection error, provider names and running build. RTSS’s own statistics are restored when Master Panel releases its owned settings.
- Display uses AMD ADLX Custom Color for brightness, contrast, saturation, hue and color temperature. Refresh reads the driver without applying a profile; visible idle controls read back live changes.
- Legacy color profiles are kept separately. On first use, the new color store starts from current AMD settings, avoiding automatic replay of old values. Natural captures that starting baseline. Night light remains a separate Windows control.

Update both views from **Settings → Updates → Check for updates → Download → Update & restart**. For manual installation, exit Master Panel from the tray and run **Master-Panel-v3.3.4-Setup.exe**. Saved settings are retained; no uninstall is needed. The separate native EXE supports older updaters.

Automated Windows checks cover software behavior, the real RTSS SDK, widget packaging, Program Files installation and upgrades. Actual Win 5/Adrenalin behavior and Winhanced overlays inside a game still need device testing.
