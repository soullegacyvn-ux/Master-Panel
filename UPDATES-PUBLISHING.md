# Publishing Master Panel updates

From 3.0.2 the updater prefers the complete installer so the desktop app and Xbox Game Bar widget stay on the same version.

Publish both assets in the same GitHub release:

- `Master-Panel-vVERSION-Setup.exe`: complete installer, used by the new updater and fresh installations.
- `Master-Panel-vVERSION.exe`: native app compatibility entry for 3.0.1 and older EXE-only updaters. It must be the real 64-bit GUI application with matching embedded version metadata, never a renamed Setup executable.

Upload both verified files to a draft, wait for their completed upload rows, compare SHA-256 digests, then publish the release. Do not publish a partially uploaded package. Preserve existing releases for recovery.

Old clients first replace the native app through their existing protected transaction. The new app records that the matching full package still needs installation before acknowledging readiness. It can then download that exact current-version Setup and finish the panel/widget update. Newer clients download Setup directly. Saved user data remains in the existing folder.

The full-package helper waits for normal app shutdown, installs the package, verifies the installed native version and registered UWP version, then restarts the app. Failed package attempts keep a diagnostic log and hold automatic retries. This does not claim rollback of every partially changed Windows package. The separate native-only transaction retains its verified rollback path.

Release CI verifies official optional-component downloads, native builds, software tests, install/uninstall, the live installed bridge and upgrades from 3.0.1 and 3.0.2 installations. It models the 3.0.1 client's first native swap and runs the new helper; for 3.0.2 it uses the original installed native process and helper unchanged. Physical Win 5 behavior and the original 3.0.1 Update UI/network leg require device checks.

The complete application project lives in the owner's separately supplied source archive. GitHub's automatic source ZIPs in this public repository contain release documentation.
