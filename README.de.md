<div align="center">
  <h1>Euro-CLI-KI</h1>
  <p><strong>Windows-CLI für lokale referenzgestützte Bildgenerierung und iterative Bildbearbeitung mit OpenAI.</strong></p>
  <p>Installer-orientierte Distribution für Endanwender. Kein Source-Checkout erforderlich.</p>
  <p><a href="./README.md">English Version</a></p>

  <p>
    <img src="./euro-cli-ki-logo.png" alt="Euro-CLI-KI Logo" width="720">
  </p>

  <p>
    <a href="https://github.com/EuroCent82/euro-cli-ki-release/releases/latest"><img src="https://img.shields.io/badge/download-windows%20installer-2f6fed?logo=windows&logoColor=white" alt="Windows Installer herunterladen"></a>
    <img src="https://img.shields.io/badge/version-0.0.1-2f6fed" alt="Version">
    <img src="https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white" alt="Windows">
    <img src="https://img.shields.io/badge/license-MIT-0b7285" alt="MIT Lizenz">
    <img src="https://img.shields.io/badge/OpenAI-Image%20API-412991?logo=openai&logoColor=white" alt="OpenAI Image API">
  </p>

  <p>
    <a href="#download">Download</a> |
    <a href="#installation">Installation</a> |
    <a href="#konfiguration">Konfiguration</a> |
    <a href="#befehle">Befehle</a> |
    <a href="#nutzung-mit-vs-code">Nutzung mit VS Code</a>
  </p>
</div>

---

## Überblick

Euro-CLI-KI ist ein lokales Windows-Kommandozeilenwerkzeug für referenzbasierte Bild-Workflows. Es ist für Fälle gedacht, in denen neue Bilder visuell zu bestehenden Assets passen müssen, statt ohne Kontext generiert zu werden.

Dieses Repository ist der öffentliche Distributionskanal für den Windows-Installer, Release-Notizen und Lizenzinformationen.

## Download

Den aktuellen Windows-Installer findest du auf der [Releases](https://github.com/EuroCent82/euro-cli-ki-release/releases/latest)-Seite:

- `euro-cli-ki-setup.exe`

## Installation

1. `euro-cli-ki-setup.exe` herunterladen.
2. Den Installer ausführen.
3. Im Startmenü den Ordner `Euro-CLI-KI` öffnen.
4. `Euro-CLI-KI` starten, um die CLI-Shell zu öffnen.

Der Installer:

- installiert die CLI nach `%LOCALAPPDATA%\Programs\EuroCliKi`
- erstellt den Startmenü-Ordner `Euro-CLI-KI`
- legt `Euro-CLI-KI` und `Uninstall Euro-CLI-KI` an
- platziert eine Konfigurationsvorlage unter `%APPDATA%\EuroCliKi\.env.example`
- zeigt auf der Abschlussseite ein kopierbares VS-Code-`settings.json`-Snippet an

## Konfiguration

Erstelle oder aktualisiere:

```text
%APPDATA%\EuroCliKi\.env
```

Beispiel:

```env
OPENAI_API_KEY=your_api_key
OPENAI_IMAGE_MODEL=gpt-image-1
```

Voraussetzungen:

- gültiger OpenAI API Key
- aktive API-Abrechnung auf der OpenAI Platform

OpenAI-Links:

- [API Keys erstellen oder verwalten](https://platform.openai.com/api-keys)
- [OpenAI Image API Dokumentation](https://developers.openai.com/api/docs/guides/image-generation)

## Befehle

Öffne den Startmenü-Eintrag `Euro-CLI-KI` oder starte die EXE direkt:

```powershell
"$env:LOCALAPPDATA\Programs\EuroCliKi\eurocliki.exe" doctor
```

Wichtige Befehle:

- `doctor` prüft Konfiguration, Verzeichnisse und Umgebung
- `generate` erzeugt ein einzelnes Bild aus Prompt und Referenzen
- `session` startet einen iterativen Bildbearbeitungs-Workflow

Beispiel:

```powershell
"$env:LOCALAPPDATA\Programs\EuroCliKi\eurocliki.exe" generate `
  --create="Create an iron mine in the style of the references" `
  --reference=".\references" `
  --output=".\output\iron-mine-v1.png"
```

## Nutzung mit VS Code

Die VS-Code-Extension wird separat veröffentlicht:

- <https://github.com/EuroCent82/euro-cli-ki-vscode>

Nach der Installation der CLI trage den EXE-Pfad in die VS-Code-Einstellungen ein:

```json
{
  "euroCliKi.cliPath": "C:\\Users\\<DEIN_BENUTZER>\\AppData\\Local\\Programs\\EuroCliKi\\eurocliki.exe"
}
```

## Release-Dateien

Dieses öffentliche Repository soll bewusst schlank bleiben. Die öffentliche Release-Fläche besteht aus:

- `README.md`
- `README.de.md`
- `CHANGELOG.md`
- `LICENSE`
- `euro-cli-ki-logo.png`
- `euro-cli-ki-setup.exe` als GitHub-Release-Asset

## Changelog

Die Release-Historie steht in [CHANGELOG.md](./CHANGELOG.md).

## Lizenz

Veröffentlicht unter der [MIT Lizenz](./LICENSE).
