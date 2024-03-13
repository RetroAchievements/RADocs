# Setting Up Each Emulator for Development

## Official RetroAchievements Emulators
The following emulators do not need any special setup and will automatically install RAIntegration upon running them for the first time:

- RALibRetro
- RAMeka
- RANes
- RAP64
- RAppleWin
- RAQUASI88
- RASnes9x
- RAVBA

## Other
The following emulators are maintained outside of RetroAchievements and support RAIntegration via some tweaking:

### Bizhawk
- Download the [latest Dev Build](https://gitlab.com/TASVideos/BizHawk/-/jobs).
- Install as you normally would.
- Add a copy of `RA_Integration.dll` to `/Bizhawk/dll/` and rename it to `RA_Integration-x64.dll`
- Launch the emulator via `EmuHawk.exe`.
- Log in.
- The RetroAchievements toolkit should be under `Tools -> RetroAchievements`.

### DuckStation
DuckStation uses its own implementation of rcheevos, so you will not be able to use the built-in achievement features alongside RAIntegration. It is recommended to have a separate instance of DuckStation specifically for achievement development so it does not interfere with playing.

- Download the [latest nightly](https://www.duckstation.org/).
- Install as you normally would.
- Add a copy of `RA_Integration.dll` to the main directory.
- Using a command line, change the directory to the DuckStation directory.
- Enter `duckstation-qt-x64-ReleaseLTCG.exe -raintegration`.
- Log in.
- The RetroAchievements toolkit should be under `Tools -> RAIntegration`.

### PCSX2
PCSX2 uses its own implementation of rcheevos, so you will not be able to use the built-in achievement features alongside RAIntegration. It is recommended to have a separate instance of PCSX2 specifically for achievement development so it does not interfere with playing.

- Download the [latest nightly](https://pcsx2.net/downloads/).
- Install as you normally would.
- Add a copy of `RA_Integration.dll` to the main directory.
- Using a command line, change the directory to the PCSX2 directory.
- Enter `pcsx2-qt.exe -raintegration`.
- Log in.
- The RetroAchievements toolkit should be under `Tools -> RAIntegration`.

### WinArcadia
WinArcadia works very similar to the official RA emulators. However, some users have encountered issues that were fixed by running WinArcadia in Windows 8 compatibility mode.

- Download and extract the [lastest binary](https://amigan.1emu.net/releases/WinArcadia-bin.rar).
- Run `WinArcadia.exe`
- Go to `Tools -> RetroAchievements` and log in. `RetroAchievements` in the menu bar should now be clickable.
