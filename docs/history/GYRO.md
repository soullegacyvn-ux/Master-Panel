# Gyro controls

Gyro is off on a fresh installation. Opening its tab previews sensor rates without
injecting mouse input. Enable aiming explicitly and choose LT/RT or Always, then save.
Calibrate while the device is still. Tune sensitivity, deadzone, smoothing and axis
inversion in the panel. Only relative mouse aiming is implemented; this is not a
virtual Xbox right stick or a replacement driver. A game must accept mouse input.

Input pauses while panel controls, Game Bar or the desktop shell are active.
A held trigger must be released before a new aiming session. Hidden pinned telemetry
alone does not pause a game. Missing, stale or invalid readings stop aiming.

Uses the built-in Windows.Devices.Sensors.Gyrometer API. If Windows has no default gyro,
Master Panel enumerates gyro devices exposed by the Windows sensor stack and opens
the sole available device. Check sensor retries discovery without enabling aiming.
If several devices are available without a default, disconnect external motion
sensors and retry. Xbox 360 gamepad identity is separate from the gyro sensor;
a controller name does not prove a BMI260 driver is missing. No sensor driver is
automatically installed. GPD lists a BMI260 six-axis
sensor: https://www.gpd.hk/gpdwin5techspecs34524234456
ABI verified against Microsoft windows-rs sensor metadata:
https://github.com/microsoft/windows-rs/blob/master/crates/libs/windows/src/Windows/Devices/Sensors/mod.rs

No firmware or BIOS writes and no new kernel driver. Physical axis orientation,
actual latency, CPU/battery use and game compatibility need testing on the Win5.
