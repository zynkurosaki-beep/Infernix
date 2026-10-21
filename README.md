# Infernix

Releases for the Infernix desktop app. This repository holds no source code.
It only hosts the installers and the release history that the app checks for updates.

## Download

Get the newest installer from [Releases](https://github.com/zynkurosaki-beep/Infernix/releases/latest).
Download `Infernix Setup X.X.X.exe` and run it.

## Updates

Infernix checks this repository each time it starts, and again when you press
**Settings > Updates > Check now**.

1. The app reads the tag of the latest release, for example `v1.5.1`.
2. If that tag is newer than the version you have installed, an **Upgrade** button appears.
3. Press **Upgrade**. The app downloads the installer from the release and shows its progress.
4. Infernix closes, installs the new version silently, and opens again on its own.

Your settings, scripts and autoexec folder are kept across upgrades.

## Release notes

See [Releases](https://github.com/zynkurosaki-beep/Infernix/releases) for what changed in each version.
Maintainers: see [RELEASING.md](RELEASING.md) for how to publish one.
