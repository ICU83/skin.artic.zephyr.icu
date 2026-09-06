# Kodi Piers / Skin Shortcuts V3 Smoke Test

## Testumgebung

- sauberes Kodi-Piers-/v22-Profil,
- `script.skinshortcuts` **3.0.2~beta16 oder kompatibler neuerer V3-Stand**,
- ICU aus dem zu prüfenden ZIP installiert.

## Grundinstallation

1. ICU installieren und aktivieren.
2. Keine Abhängigkeits- oder „skin not updated“-Fehler.
3. `addon.xml`-Version und Add-on-ID kontrollieren.
4. Kodi-Log auf XML-/Include-Fehler prüfen.

## Home und Skin Shortcuts

1. Standard-Hauptmenü auf Anzahl, Reihenfolge, Labels, Icons und Aktionen prüfen.
2. Hauptmenü-Editor öffnen; Hinzufügen, Löschen, Verschieben, Umbenennen, Icon, Aktion und Deaktivieren testen.
3. Untermenü bearbeiten und `skinshortcuts-mainmenu-submenu` prüfen.
4. Widget-Slots 1–6 unabhängig konfigurieren; Quelle, Sortierung, Richtung, Aspect/Ansicht, Target und Widget-Titel prüfen.
5. Editor schließen/öffnen und Persistenz prüfen.
6. Hintergrund setzen und wieder auf „None“/Standard zurückstellen.
7. Skin-Einstellungen verlassen und danach Home erneut öffnen (`buildxml`).

## Hubs

Custom Hubs 1111 bis 1119 öffnen und prüfen, dass `skinshortcuts-x1111` bis `skinshortcuts-x1119` die bestehenden Fenster befüllen.

## Widget-Layouts

Classic, Featured und vertikale Widget-Layouts testen. Weather Daily/Hourly, System Info und Settings-Inhalte prüfen, sofern genutzt. Fallback-, Hub- und Spotlight-Widget-Picker auf Path/Label/Type/Target prüfen.

## Emby / Library Nodes

Repräsentative Film-/Serien-Nodes als Menü-/Widgetquelle auswählen. Temporäre/ungültige Menüicons sollen auf einen sichtbaren Fallback fallen. Widgets müssen als echte `list`-/`fixedlist`-Controls generiert werden.

## Audio-Flags

AC3/EAC3, TrueHD, TrueHD Atmos, EAC3 Atmos, DTS, DTS-HD MA/HRA, DTS:X und AAC/HE-AAC testen. Listen, Hubs und OSD sollen dieselbe Normalisierung verwenden.

## Video-Flags

H.264/AVC/x264, HEVC/H.265/hvc1/hev1/x265, MPEG-2, MPEG-4 Visual, VP8 und VP9 testen. Weiße und farbige Source-Flags sollen denselben unterstützten Dateibestand besitzen.

## Live TV / PVR

1. Live TV starten und Video-OSD öffnen.
2. Mit deaktivierter ICU-Option Sendername prüfen.
3. **„Laufende Sendung statt Sendername im Live-TV-OSD anzeigen“** aktivieren.
4. `VideoPlayer.Title` prüfen; bei leerem Titel Sender-Fallback prüfen.
5. PVR TV/Radio, EPG und PVR-Dialoge öffnen.

## Music OSD

1. Musik mit Albumcover abspielen.
2. **CD und Hülle** aktivieren und DiscArt/Fake-CD prüfen.
3. **„Nur Albumcover anzeigen“** aktivieren.
4. Cover bleibt sichtbar; DiscArt/Fake-CD/Vinyl/Default-CD verschwindet.
5. Cover-only deaktivieren und DiscArt-Auswahl erneut prüfen.
6. Music-Visualisation-Fanart prüfen: Album-Fanart soll vor allgemeinem Fanart verwendet werden, wenn der Fallback aktiv ist.

## Startbildschirm

1. `StartupPlaylist` leeren und Kodi/Skin starten.
2. ICU-Startbildschirm `media/common/startup_icu.png` prüfen.
3. Startup-Mediendatei konfigurieren und prüfen, dass diese statt des statischen Fallbacks abgespielt wird.

## Backup / Reset

ICU-Konfiguration sichern, V3-Shortcuts zurücksetzen, ICU-Defaults prüfen und sicherstellen, dass alte `skin.arctic.zephyr.mod`-V2-Daten nicht verändert werden. Danach Sicherung wiederherstellen.

## Abschluss

Skin Settings, File Manager, Video-/Music-Info, OSD und zentrale Ansichten öffnen und Kodi-Log auf XML-, Include- und Skin-Shortcuts-Fehler prüfen.

### Bewusster Unterschied zum alten V2-Skin

Bestehende Skin-Shortcuts-V2-Benutzerdaten werden nicht automatisch in V3 importiert. Dieses Verhalten ist beabsichtigt.
