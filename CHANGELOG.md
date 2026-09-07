# Changelog

Dieses Dokument trennt die **ICU-Entwicklung** von der geerbten Upstream-Historie. Für die hier entstandenen 1.0.x-Builds wurden in der Entwicklung keine Veröffentlichungsdaten festgehalten; deshalb werden bewusst keine Daten erfunden.

## ICU-Releases

### 1.0.25

- Fehlenden Text bei SkinSettings-Button 9221 behoben.
- Der englische Basis-Sprachkatalog trennt den PO-Eintrag `#31723` nun korrekt vom vorherigen Eintrag, sodass Kodi die Lokalisierungs-ID `31723` lädt.

### 1.0.24

- Projekt-Infotext in den Skin-Einstellungen auf ein echtes mehrzeiliges Textfeld umgestellt, damit `[CR]`-Zeilenumbrüche korrekt dargestellt werden.
- SkinSettings-Projektbereich (Button 9108) und optionales Settings-Logo vollständig auf **Artic: Zephyr ICU** umgestellt; geerbte Reloaded-/AZR-Bezeichnungen, Infotext und `misc/matrix.png`-Branding aus SkinSettings entfernt.
- AURO-3D-Audioerkennung für Kodi-Listen, Hubs und OSD ergänzt.
- Erkennung bevorzugt explizite Codec-Werte `auro3d` / `auro_3d` und nutzt zusätzlich Dateinamen-Muster wie `auro-3d`, `auro3d`, `auro_3d` und `auro 3d`.
- Neue AURO-3D-Flag-Assets für weiße, farbige und OSD-Icon-Sätze hinzugefügt.
- Bei Dateinamen mit AURO-3D wird das AURO-3D-Logo als zusätzliches Audio-Flag angezeigt; Atmos/DTS:X bzw. der von Kodi gemeldete Trägercodec bleiben parallel sichtbar.
- AURO-3D-Flag-Grafiken auf die visuelle Höhe des Dolby-Atmos-Logos abgestimmt.

### 1.0.23

- ICU-Startdialog bereinigt: das geerbte `misc/matrix.png`-/„Reloaded“-Overlay wird beim Start nicht mehr über dem ICU-Startbild eingeblendet.
- Live-TV-OSD verwendet für den laufenden EPG-Sendungstitel unter Kodi Piers/v22 `Player.Title`; bei leerem EPG-Titel bleibt der Sendername als Fallback erhalten.
- Live-TV-Titelumschaltung an die tatsächlich verwendeten OSD-Pfade inklusive `PlayerBigTitle` angebunden.
- Neue OSD-Einstellungen wieder vollständig über die Lokalisierungs-IDs `31723` und `31724` eingebunden; beide IDs sind in allen vorhandenen Sprachkatalogen registriert.
- Deutsche Übersetzungen für beide ICU-OSD-Optionen enthalten; andere noch nicht übersetzte Sprachen verwenden den englischen Quelltext als Fallback.

### 1.0.22

- Music-OSD-Option **„Nur Albumcover anzeigen“** bleibt in den Skin-Einstellungen lesbar und schaltbar, auch wenn **„CD und Hülle“** aktuell deaktiviert ist.
- ICU-Startbildschirm wird ohne die starke `Background`-Farbdiffusion dargestellt; der alte „Arctic Zephyr“-Textoverlay wurde vom dedizierten ICU-Startbild entfernt.
- Live-TV-OSD-Umschaltung auf den laufenden Sendungstitel an die tatsächlich gerenderte Variable `PlayerBigTitle` angebunden.

### 1.0.21

- Eigenen ICU-Startbildschirm als dedizierte Grafik `media/common/startup_icu.png` hinzugefügt.
- `StartupFanart` verwendet diese Grafik als Standard-Fallback, ohne den globalen Skin-Hintergrund zu verändern.

### 1.0.20

- Neue Music-OSD-Option **„Nur Albumcover anzeigen (CD/DiscArt im Music-OSD ausblenden)“**.
- Echte DiscArt, Fake-CD, Vinyl- und Default-CD können gemeinsam ausgeblendet werden, während das Albumcover sichtbar bleibt.
- Fake-CD-/Vinyl-Auswahl wird im Cover-only-Modus deaktiviert.

### 1.0.19

- Ältere gewünschte Music-Visualisation-Anpassung wieder eingepflegt.
- Beim Fanart-Fallback wird `Player.Art(album.fanart)` vor `Player.Art(fanart)` verwendet.

### 1.0.18

- Neue Live-TV-OSD-Option **„Laufende Sendung statt Sendername im Live-TV-OSD anzeigen“**.
- Aktiv: Anzeige von `VideoPlayer.Title`.
- Fallback auf `VideoPlayer.ChannelName`, falls kein Sendungstitel vorhanden ist.

### 1.0.17

- Video-Codec-Flag-Erkennung für Kodi Piers normalisiert.
- Aliaswerte wie `h265`, `hvc1`, `hev1`, `x265`, `avc`, `avc1`, `x264` und MPEG-4-Varianten werden auf vorhandene Flag-Namen abgebildet.
- Weiße und farbige Video-Source-Flag-Sätze auf denselben Bestand gebracht; fehlende Flags wie VP8/VP9 ergänzt.
- Normalisierung für Listen, Hubs und Player/OSD vereinheitlicht.

### 1.0.16

- Audio-Flag-Erkennung für neue Kodi-Piers-/v22-Codecwerte erweitert.
- Atmos-Werte wie `truehd_atmos` und `eac3_ddp_atmos` auf Atmos-Flags abgebildet.
- DTS:X-Werte wie `dtshd_ma_x` und `dtshd_ma_x_imax` auf DTS:X abgebildet.
- Neue AAC- und DTS-Untervarianten normalisiert.
- Hub-Ansichten verwenden dieselbe normalisierte Audio-Erkennung.

### 1.0.15

- Projekticon durch die vom Projektinhaber ausgewählte Arctic-Zephyr-ICU-Logo-Version ersetzt.

### 1.0.14

- Erstes ICU-Projekticon eingeführt.
- „Zephyr“ auf leuchtendes Blau umgestellt und „Reloaded“ durch „ICU“ ersetzt.

### 1.0.13

- Widget-Editor-Überlagerung endgültig behoben.
- Der Haupteditor-Control für **Background** wird in Widget-Subdialogen ausgeblendet, damit er nicht die erste Widget-Zeile überlagert.

### 1.0.12

- Alte Widget-Label-/Fullscreen-Fallback-Verweise in den Haupt-Widget-Zeilen bereinigt, um Überschneidungen im Editor zu reduzieren.

### 1.0.11

- Textbreite im Widget-Editor angepasst, um Label-Überlappungen zu reduzieren.

### 1.0.10

- Widget-Titel im Skin-Shortcuts-Editor editierbar gemacht.
- `widgetLabel` sowie die Suffixe `.2` bis `.6` für alle sechs Widget-Slots unterstützt.

### 1.0.9

- Fallback für ungültige bzw. temporäre externe Hauptmenü-Icons ergänzt.
- Insbesondere Emby-/temporäre Icon-Pfade können auf `DefaultFolder.png` zurückfallen.
- Dadurch wurde das fehlende Movies-Menü in der betroffenen Konfiguration wieder sichtbar.

### 1.0.8

- `buildxml` beim Verlassen der Skin-Einstellungen wiederhergestellt, damit Skin-Shortcuts-Änderungen zuverlässig neu generiert werden.

### 1.0.7

- Verhalten für `Background=None` korrigiert: Verwendung des normalen Skin-Hintergrunds `pvr/background.jpg` statt schwarzem/null Hintergrund.

### 1.0.6

- Erste Anpassung des `Background=None`-Verhaltens vorgenommen; dieses Verhalten wurde in 1.0.7 nochmals korrigiert.

### 1.0.5

- Beschriftung **„Restore shortcuts“** im Skin-Shortcuts-Editor auf die V3-Addon-Übersetzung umgestellt (`$ADDON[script.skinshortcuts ...]`).

### 1.0.4

- V3-Property-Fallbacks in den Skin-Shortcuts-Templates korrigiert.
- Generierte Widget-Controls erhalten wieder gültige `list`-/`fixedlist`-Typen statt leerer Typwerte.

### 1.0.3

- Untermenü-Include auf `skinshortcuts-mainmenu-submenu` korrigiert.
- Frühere V2-`<other>`-Template-Logik in V3-kompatible, auf `mainmenu` begrenzte Templates überführt.
- „My Submenu“ an die V3-Struktur angepasst.

### 1.0.2

- Leere **Choose item**-Zeile unter Status im Skin-Shortcuts-Editor behoben.
- Veraltete `$LOCALIZE[32xxx]`-Verweise für Skin Shortcuts durch `$ADDON[script.skinshortcuts ...]` ersetzt.
- Dadurch werden Widget-/Node-Picker-Beschriftungen nicht mehr als rohe `$LOCALIZE[...]`-Texte angezeigt.

### 1.0.1

- Eindeutige V3-Widget-IDs und gemeinsame Custom-Widget-Behandlung korrigiert.
- Dynamische Videoquellen und EPG-Widgetquelle angepasst.
- V3-Targets für Widget-Picker korrigiert.
- Mindestabhängigkeit auf `script.skinshortcuts 3.0.2~beta16` angehoben, da ältere V3-Stände Probleme mit verschachtelten Library-/Addon-Pickern hatten.

### 1.0.0 — Artic: Zephyr ICU

- Kodi-Piers-Baseline mit `xbmc.gui 5.18.0` erstellt.
- Add-on-ID auf `skin.artic.zephyr.icu` umgestellt.
- Native Migration von `script.skinshortcuts` V2 auf V3.
- V3-Konfiguration aufgeteilt in `shortcuts/menus.xml`, `widgets.xml`, `backgrounds.xml`, `properties.xml` und `templates.xml`.
- Veraltete V2-Dateien wie `*.DATA.xml`, `overrides.xml` und `template.xml` aus der Skin-Konfiguration entfernt.
- Bestehenden Zephyr-Menüeditor, Untermenüs, sechs Widget-Slots und neun Hubs (`1111`–`1119`) erhalten.
- Mainmenu-/Submenu-/Hub-Includes auf die V3-Namen umgestellt.
- V3-Aufrufsyntax für `buildxml` und `manage,menu=...` übernommen.
- Bestehende V2-Benutzerdaten werden absichtlich nicht automatisch migriert oder verändert.

## Upstream-Historie

Die vollständige geerbte Historie des direkten Vorgängerprojekts ist weiterhin in [`changelog.txt`](changelog.txt) enthalten. Sie umfasst die Arctic-Zephyr-Mod-/Reloaded-Versionen und die dort genannten Beiträge früherer Mitwirkender. Diese Upstream-Einträge werden nicht ICU83 zugeschrieben.
