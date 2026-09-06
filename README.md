# Artic: Zephyr ICU

**Artic: Zephyr ICU** ist ein Kodi-Skin für **Kodi Piers (v22)** mit nativer **Skin Shortcuts V3**-Integration. Das Projekt basiert auf **Arctic: Zephyr** von **jurialmunkey** und dem späteren **Arctic: Zephyr - Reloaded / Mod** von **beatmasterRS**.

Dieses Repository wird von **ICU83** weitergeführt. Die ursprünglichen Autoren, Credits und die bestehende Lizenz bleiben ausdrücklich erhalten.

## Aktueller Stand

- Add-on-ID: `skin.artic.zephyr.icu`
- Version: **1.0.21**
- Kodi: **Piers / v22**
- `xbmc.gui`: **5.18.0**
- Skin Shortcuts: **3.0.2~beta16 oder neuer innerhalb der V3-Linie**
- Native V3-Konfiguration in `shortcuts/`
- 6 Widget-Slots pro unterstütztem Menüeintrag
- 9 Custom Hubs (`1111` bis `1119`)
- Piers-spezifische Audio-/Video-Codec-Normalisierung

## Installation

Die normale Installation erfolgt über **Kodi → Add-ons → Aus ZIP-Datei installieren**. Eine ausführliche Anleitung steht unter [docs/INSTALLATION.md](docs/INSTALLATION.md).

> **Wichtig:** Bestehende Skin-Shortcuts-V2-Benutzerdaten des alten Skins werden absichtlich nicht automatisch in das V3-Format migriert oder verändert.

## Dokumentation

- [Installation und Updates](docs/INSTALLATION.md)
- [Komplette Anleitung der Skin-Einstellungen](docs/SETTINGS.md)
- [Skin Shortcuts V3](docs/SKINSHORTCUTS_V3.md)
- [Kodi Piers / V3 Smoke Test](docs/PIERS_V3_SMOKE_TEST.md)
- [Entwicklung und Release-Prüfung](docs/DEVELOPMENT.md)
- [ICU-Changelog](CHANGELOG.md)
- [Credits und Herkunft](CREDITS.md)

## ICU-spezifische Erweiterungen

Der ICU-Zweig enthält unter anderem:

- native Portierung auf `script.skinshortcuts` V3,
- sechs unabhängig editierbare Widget-Slots,
- editierbare Widget-Titel,
- V3-kompatible Untermenüs und Custom Hubs,
- robustere Emby-/Library-Node-Unterstützung,
- aktualisierte Audio-Flags für Atmos, DTS:X und neue Kodi-v22-Codecwerte,
- normalisierte Video-Codec-Flags für Kodi Piers,
- Live-TV-OSD-Option für `VideoPlayer.Title` statt Sendername,
- Music-OSD-Option **„Nur Albumcover anzeigen“** ohne CD/DiscArt/Fake-CD,
- ICU-Projekticon und eigener ICU-Startbildschirm.

## Herkunft und Credits

Die Design- und Codebasis stammt aus den vorausgehenden Arctic-Zephyr-Projekten. Dieses Repository beansprucht die ursprüngliche Arbeit nicht als eigene. Details und Quellprojekte stehen in [CREDITS.md](CREDITS.md).

Provider in `addon.xml`:

`jurialmunkey, beatmasterrs, ICU83`

## Lizenz

Das vorhandene Projekt bleibt unter der im Skin mitgelieferten **Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported**-Lizenz. Siehe [LICENSE.txt](LICENSE.txt).

Zusätzliche Icons können eigenen Lizenzbedingungen ihrer ursprünglichen Quellen unterliegen; die historischen Hinweise aus dem Upstream-Projekt bleiben im Repository erhalten.

## Repository

Projektadresse: `https://github.com/ICU83/skin.artic.zephyr.icu`
