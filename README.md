<div align="center">
  <h1>Euro-CLI-KI</h1>
  <p><strong>Windows CLI for local reference-based image generation and iterative image editing with OpenAI.</strong></p>
  <p>Installer-first distribution for end users. No source checkout required.</p>

  <p>
    <a href="https://github.com/EuroCent82/euro-cli-ki-release/releases/latest"><img src="https://img.shields.io/badge/download-windows%20installer-2f6fed?logo=windows&logoColor=white" alt="Download Windows Installer"></a>
    <img src="https://img.shields.io/badge/version-0.0.1-2f6fed" alt="Version">
    <img src="https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white" alt="Windows">
    <img src="https://img.shields.io/badge/license-MIT-0b7285" alt="MIT License">
    <img src="https://img.shields.io/badge/OpenAI-Image%20API-412991?logo=openai&logoColor=white" alt="OpenAI Image API">
  </p>

  <p>
    <a href="#download">Download</a> |
    <a href="#install">Install</a> |
    <a href="#configure">Configure</a> |
    <a href="#commands">Commands</a> |
    <a href="#use-with-vs-code">Use with VS Code</a>
  </p>
</div>

---

## Overview

Euro-CLI-KI is a local Windows command-line tool for reference-based image workflows. It is designed for cases where new images must stay visually aligned with existing assets instead of being generated without context.

This repository is the public distribution channel for the Windows installer, release notes, and license information.

## Download

Download the latest Windows installer from the [Releases](https://github.com/EuroCent82/euro-cli-ki-release/releases/latest) page:

- `euro-cli-ki-setup.exe`

## Install

1. Download `euro-cli-ki-setup.exe`.
2. Run the installer.
3. Open the Start Menu folder `Euro-CLI-KI`.
4. Start `Euro-CLI-KI` to open the CLI shell.

The installer currently:

- installs the CLI to `%LOCALAPPDATA%\Programs\EuroCliKi`
- creates the Start Menu folder `Euro-CLI-KI`
- adds `Euro-CLI-KI` and `Uninstall Euro-CLI-KI`
- places a config template at `%APPDATA%\EuroCliKi\.env.example`
- shows a copyable VS Code settings snippet on the finish page

## Configure

Create or update:

```text
%APPDATA%\EuroCliKi\.env
```

Example:

```env
OPENAI_API_KEY=your_api_key
OPENAI_IMAGE_MODEL=gpt-image-1
```

Requirements:

- valid OpenAI API key
- active API billing on the OpenAI Platform

## Commands

Open the Start Menu entry `Euro-CLI-KI` or run the executable directly:

```powershell
"$env:LOCALAPPDATA\Programs\EuroCliKi\eurocliki.exe" doctor
```

Main commands:

- `doctor` checks config, directories, and environment
- `generate` creates a single image from prompt and references
- `session` starts an iterative image-editing workflow

Example:

```powershell
"$env:LOCALAPPDATA\Programs\EuroCliKi\eurocliki.exe" generate `
  --create="Create an iron mine in the style of the references" `
  --reference=".\references" `
  --output=".\output\iron-mine-v1.png"
```

## Use With VS Code

The VS Code extension is published separately:

- <https://github.com/EuroCent82/euro-cli-ki-vscode>

After installing the CLI, add the executable path to your VS Code settings:

```json
{
  "euroCliKi.cliPath": "C:\\Users\\<YOUR_USER>\\AppData\\Local\\Programs\\EuroCliKi\\eurocliki.exe"
}
```

## Release Files

This public repository is intended to stay minimal. The release surface consists of:

- `README.md`
- `CHANGELOG.md`
- `LICENSE`
- `euro-cli-ki-setup.exe` as a GitHub Release asset

## Changelog

Release history is documented in [CHANGELOG.md](./CHANGELOG.md).

## License

Distributed under the [MIT License](./LICENSE).
