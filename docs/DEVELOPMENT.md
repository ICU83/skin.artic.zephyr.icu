# Entwicklung und Releases

## Repository

`https://github.com/ICU83/skin.artic.zephyr.icu`

## Grundprinzip

Der ICU-Zweig soll die Herkunft des Skins erhalten und Änderungen möglichst gezielt auf Kodi Piers sowie die ICU-Funktionen begrenzen. Upstream-Credits und Lizenz dürfen bei Releases nicht entfernt werden.

## Wichtige Dateien

- `addon.xml` — Add-on-ID, Version, Provider, Abhängigkeiten und Metadaten.
- `1080i/` — Kodi-Skin-Fenster, Includes und Dialoge.
- `shortcuts/` — native Skin-Shortcuts-V3-Konfiguration.
- `language/` — Übersetzungen.
- `media/` — Bilder, Icons und Media Flags.
- `CHANGELOG.md` — ICU-Release-Historie.
- `changelog.txt` — geerbte Upstream-Historie plus frühere Kodi-Changelog-Daten.
- `CREDITS.md` / `LICENSE.txt` — Herkunft und Lizenz.

## Versionsregel

Vor einem veröffentlichten Skin-Build muss die Version im Root-Element von `addon.xml` erhöht werden. Dokumentationsänderungen am Repository müssen nicht rückwirkend eine bereits veröffentlichte Skin-Version verändern; der nächste funktionale Build erhält die nächste Version.

## XML-Prüfung

Alle XML-Dateien sollten vor einem Release geparst werden. Beispiel mit Python:

```bash
python -c "from pathlib import Path; import xml.etree.ElementTree as ET; files=list(Path('.').rglob('*.xml')); [ET.parse(p) for p in files]; print(f'{len(files)} XML-Dateien OK')"
```

## Skin-Shortcuts-Prüfung

Vor einem Release prüfen:

- `script.skinshortcuts`-Mindestversion in `addon.xml`,
- `shortcuts/menus.xml`, `widgets.xml`, `backgrounds.xml`, `properties.xml`, `templates.xml` vorhanden,
- keine alten V2-`*.DATA.xml`, `overrides.xml` oder monolithischen `template.xml`-Dateien zurückgebracht,
- `Home.xml`/SkinSettings lösen `buildxml` aus,
- sechs Widget-Slots und Hubs 1111–1119 funktionieren.

## Installierbares ZIP bauen

Kodi erwartet einen Top-Level-Ordner mit dem Add-on-ID-Namen:

```text
skin.artic.zephyr.icu-<version>.zip
└── skin.artic.zephyr.icu/
    ├── addon.xml
    ├── 1080i/
    ├── media/
    └── ...
```

Beispiel:

```bash
cd ..
zip -r skin.artic.zephyr.icu-1.0.26.zip skin.artic.zephyr.icu \
  -x 'skin.artic.zephyr.icu/.git/*' \
     'skin.artic.zephyr.icu/.worktrees/*' \
     'skin.artic.zephyr.icu/*.zip'
```

## Release-Checkliste

1. Version in `addon.xml` erhöht.
2. `CHANGELOG.md` ergänzt.
3. Deutsche/englische neue Strings kontrolliert.
4. Alle XML-Dateien geparst.
5. ZIP-Integrität geprüft.
6. Kodi-Piers-Smoke-Test durchgeführt.
7. Hauptmenü/Submenü/6 Widgets/Hubs geprüft.
8. Live TV und Music OSD geprüft, wenn OSD-Code geändert wurde.
9. Audio-/Video-Flags geprüft, wenn Flag-Logik geändert wurde.
10. SHA-256 des Release-ZIPs dokumentiert.

## Credits-Regel

`provider-name` muss die ursprünglichen Provider **jurialmunkey** und **beatmasterrs** zusammen mit **ICU83** enthalten. Historische Herkunft darf nicht aus README, CREDITS oder Lizenz entfernt werden.
