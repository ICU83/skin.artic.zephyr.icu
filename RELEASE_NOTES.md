# Artic: Zephyr ICU 1.0.33
## HDR10+ Maintenance Release

Version 1.0.33 übernimmt den bestätigten EPG-Stand aus 1.0.32 und korrigiert die Auswahl des HDR10+-Media-Flags unter Kodi 22.

### HDR / Media Flags

- `IsVideoHDR10Plus` erkennt Kodis nativen HDR-Typ `hdr10plus` jetzt direkt über `ListItem.HdrType` und `VideoPlayer.HdrType`.
- Dateinamen mit `hdr10plus` bleiben als Fallback-Erkennung erhalten.
- Die normale HDR10-Bedingung schließt HDR10+ weiterhin explizit aus, damit bei erkannten HDR10+-Titeln `hdr10plus.png` statt `hdr10.png` ausgewählt wird.
- Vorhandene HDR-, HLG- und Dolby-Vision-Erkennung bleibt unverändert.

### EPG / PVR

- Die in 1.0.32 bestätigten EPG-Korrekturen bleiben unverändert erhalten: keine Focus-Überlagerung bei Control 10 und aktive Fade-/Scroll-Darstellung für sehr kurze Sendungen.
- Die 1-Minuten-EPG-Skalierung bleibt unverändert.

### Basis

- Kodi Piers / v22
- `xbmc.gui` 5.18.0
- Skin Shortcuts 3.0.1
- Release-Paket verwendet weiterhin `media/Textures.xbt`.

### Validierung

- XML-Struktur des Skins geprüft.
- ZIP-Integrität geprüft.
- Versionsangaben und Release-Metadaten auf 1.0.33 abgeglichen.
- HDR10+-Erkennung gegen den bestätigten 1.0.32-Testfix abgeglichen.
