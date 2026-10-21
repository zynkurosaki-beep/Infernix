# Publishing a release

Every Infernix install reads the **latest** release in this repository.
Follow these rules, or the update check skips the release.

## Steps

1. In the app source, set `"version"` in `infernix-executor/package.json`, for example `1.5.1`.
2. Build the installer: `npm run dist:win`. It writes `release/Infernix Setup 1.5.1.exe`.
3. Here, open **Releases > Draft a new release**.
4. Create the tag `v1.5.1`. It must match the version from step 1.
5. Attach `Infernix Setup 1.5.1.exe` as a release asset.
6. Write the notes and press **Publish release**.

Installs of any older version now show **Upgrade** on their next start.

## Rules the updater checks

| Rule | Why |
| --- | --- |
| Tag is exactly `vX.X.X`, such as `v1.5.1` | Tags like `1.5.1`, `v1.5`, or `v1.5.1-beta` are ignored. |
| Release is published, not a draft or pre-release | The app reads only `releases/latest`, which skips both. |
| At least one `.exe` asset is attached | Without one, no Upgrade appears. An asset with `Setup` in its name is preferred. |
| The tag matches `package.json` of the build you attach | Otherwise the new install still sees itself as older and offers the same upgrade forever. |
| The tag is newer than the last one | Installs only move up. A tag older than the installed version is ignored. |

## Rolling back

Installs never move to an older version. To undo a bad release, rebuild the good code with a
higher version number (for example `1.5.4` with the `1.5.2` code) and publish that.
Deleting the bad release stops new upgrades to it, but installs that already have it stay on it.
