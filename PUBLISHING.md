# Publishing Rift Companion updates

Build the application locally using `build_desktop.py --version X.Y.Z`. The configured build embeds this repository's update feed and generates the versioned installer, the versioned application ZIP, and `latest.template.json`.

For each version:

1. Increase the version. Never replace an already distributed version's application ZIP.
2. Run the application checks and packaged executable checks before publishing.
3. Rename a copy of `latest.template.json` to `latest.json`. Its version, download URL, ZIP byte count, and SHA256 must match the build exactly.
4. Create a GitHub release tagged `vX.Y.Z` and attach all three files: `RiftCompanionSetup-X.Y.Z.exe`, `RiftCompanion-X.Y.Z-windows-x64.zip`, and `latest.json`.
5. Wait for all uploads to finish, then publish as the latest stable release. Keep older releases available.
6. Check the public downloads and the application's **Check updates** action.

The permanent update feed is https://github.com/Elashootgun/rift-companion-releases/releases/latest/download/latest.json .

Only upload the generated release files. Do not upload the working project, personal JSON files, imported history, account folders, API keys, build logs, or build-info.json.

The initial 0.16.0 preview does not have this feed embedded. Install 0.16.1 once to switch to GitHub updates. Later versions will use the in-app updater.
