# Artic: Zephyr ICU 1.0.34
## ICU Day/Night Integration Release

Version 1.0.34 ersetzt die veraltete Arctic-Zephyr-Mod-AutoColors-Anbindung durch den ICU-eigenen Day/Night-Service.

### Day / Night Colors

- `script.arctic.zephyr.mod.autocolors` wurde in den Skin-Einstellungen durch `service.artic.zephyr.icu.daynight` ersetzt.
- Der Eintrag unter „Supported Addons“ verwendet jetzt den ICU-Day/Night-Service.
- Der bisherige `Autocolor`-Radiobutton mit `Skin.HasSetting(daynight.autocolor)` wurde entfernt.
- Unter „Furniture“ öffnet „Day / Night Colors“ jetzt direkt `Addon.OpenSettings(service.artic.zephyr.icu.daynight)`.
- Der Service bleibt ein separates Kodi-Add-on und wird nicht als feste Skin-Abhängigkeit in `addon.xml` eingetragen.

### Unverändert

- HDR10+-Erkennung aus 1.0.33 bleibt unverändert erhalten.
- EPG-Korrekturen und 1-Minuten-Skalierung aus 1.0.32 bleiben unverändert erhalten.
- Release-Paket verwendet weiterhin `media/Textures.xbt`.

### Basis

- Kodi Piers / v22
- `xbmc.gui` 5.18.0
- Skin Shortcuts 3.0.1

### Validierung

- XML-Struktur des Skins geprüft.
- ZIP-Integrität geprüft.
- Versionsangaben und Release-Metadaten auf 1.0.34 abgeglichen.
- Änderungen gegen 1.0.33 auf die geplanten Skin-/Release-Dateien begrenzt.
