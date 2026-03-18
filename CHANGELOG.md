# Changelog

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog and this project currently tracks released versions from the Git repository.

## [0.0.1] - 2026-03-18

Initial public release.

### Added

- local CLI for reference-based image generation with `generate` and `session`
- `doctor` command for configuration and environment checks
- user-level config lookup via project `.env` and `%APPDATA%\EuroCliKi\.env`
- native Windows build pipeline for `eurocliki.exe` using Node SEA
- branded Windows installer `euro-cli-ki-setup.exe`
- Start Menu entries for `Euro-CLI-KI` shell and uninstaller
- finish-page snippet for connecting the CLI to the VS Code extension

### Changed

- installer is now `current-user` only and upgrades cleanly in place
- `eurocliki.exe` now carries Euro-CLI-KI icon and version metadata instead of inherited Node metadata
- direct double-click on `eurocliki.exe` now shows help and keeps the console open until confirmed

### Notes

- the VS Code extension is maintained separately at <https://github.com/EuroCent82/euro-cli-ki-vscode>
