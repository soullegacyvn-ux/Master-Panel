# Master Panel 3.2.1

Maintenance update for the desktop panel and Xbox Game Bar widget.

- Stops TDP changes if recovery data cannot be saved before a hardware write.
- Serializes optional service pause/resume with app exit and update restart, retaining recovery after an unconfirmed stop.
- Reuses fresh fan/temperature readings and reduces repeated TDP, slider, EQ and bridge work.
- Avoids a duplicate FxSound CLI refresh during low-volume checks.
- Removes unused Lossless Scaling source and obsolete build wiring; updates the Go runtime and Windows dependency.
- Keeps the existing separate battery/DC ceilings, source-specific caution and 45 W/lower-cap Reset behavior.

Use the full Setup EXE to update both views together. Saved user settings are retained. See AUDIT-3.2.1.md and VALIDATION-3.2.1.txt for changes and test scope. Software checks do not replace physical Win 5 testing.
