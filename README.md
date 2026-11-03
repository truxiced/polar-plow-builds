# Polar Plow: builds

Windows and Linux builds of **Polar Plow**, a goofy first-person co-op game where you and up to seven friends clean the South Pole, starting with a toothbrush. This repository only holds the builds. There is no source code here.

## Install on Windows (once)

1. Download **[PolarPlowLauncher.exe](https://github.com/truxiced/polar-plow-builds/releases/latest/download/PolarPlowLauncher.exe)**.
2. Run it. Windows may say *"Windows protected your PC"* because the game is not signed: click **More info**, then **Run anyway**.
3. The launcher installs itself and shows a path like
   `C:\Users\<you>\AppData\Local\PolarPlow\PolarPlowLauncher.exe`.
   Press **Copy path**. You can delete the file you downloaded.
4. In Steam: **Games > Add a Non-Steam Game to My Library… > Browse…**, paste the path into the file name box, press **Open**, then **Add Selected Programs**.
5. Optional: right-click the new entry in your library, choose **Properties**, and rename it to *Polar Plow*.

## Install on Linux (Ubuntu, once)

1. Open a terminal and run:
   ```sh
   cd ~/Downloads
   curl -fLO https://github.com/truxiced/polar-plow-builds/releases/latest/download/PolarPlowLauncher.x86_64
   chmod +x PolarPlowLauncher.x86_64
   ./PolarPlowLauncher.x86_64
   ```
   Downloaded with a browser instead? The file is not executable yet, and double-clicking it in Files does nothing: run the `chmod` and `./` lines above.
2. The launcher installs itself to `~/.local/share/PolarPlow` and adds **Polar Plow** to the app menu. Press **Continue** to download the game. You can delete the file you downloaded.
3. In Steam: **Games > Add a Non-Steam Game to My Library…**, tick **Polar Plow** in the list, then **Add Selected Programs**.
   Not in the list? Press **Browse…**, press **Ctrl+H** to show hidden folders, and pick `~/.local/share/PolarPlow/PolarPlowLauncher.x86_64`.

You can also start it from the app menu without Steam.

## Play

Start it from Steam. Each time, the launcher checks for a newer build, installs it, shows what changed, and starts the game when you press **Play**. If you are offline, it offers the build you already have.

To play together, everyone needs the same build. If joining fails with *"Version mismatch"*, whoever has the older build should quit and start the game from Steam again.

## Where things are

| | Windows | Linux |
|---|---|---|
| Launcher and game builds (the current and the previous one) | `%LOCALAPPDATA%\PolarPlow` | `~/.local/share/PolarPlow` |
| Your saves (updates never touch them) | `%APPDATA%\Godot\app_userdata\Polar Plow` | `~/.local/share/godot/app_userdata/Polar Plow` |
| Launcher log, for when something goes wrong | `%LOCALAPPDATA%\PolarPlow\launcher.log` | `~/.local/share/PolarPlow/launcher.log` |

To uninstall, delete the launcher folder and remove the game from Steam. On Linux also delete `~/.local/share/applications/polar-plow.desktop`.

## Releases

Each release is one build, named after its build number (for example `build-11` is version `0.1.0+11`). It holds the game for Windows and Linux, both launchers, and `latest.json`, which the launcher reads. Builds are published automatically and only the newest 20 are kept.
