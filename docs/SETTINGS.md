# Anleitung: Skin-Einstellungen

Diese Anleitung beschreibt die wichtigsten Einstellungsbereiche von **Artic: Zephyr ICU 1.0.25**. Je nach Kodi-Sprache können einzelne Bezeichnungen leicht abweichen.

## Einstellungen öffnen

Öffne in Kodi die **Skin-Einstellungen**. Die Hauptnavigation des Einstellungsfensters enthält folgende Bereiche:

- **Arctic: Zephyr - Reloaded** — geerbte globale/grundlegende Optionen des Upstream-Skins.
- **Home** — Hauptmenü, Widgets und Home-Darstellung.
- **Hintergrund** — globale und bereichsspezifische Hintergrundoptionen.
- **Ausstattung** — sichtbare Skin-Elemente, Flags, Header und ähnliche „Furniture“-Elemente.
- **Gerade läuft** — Now-Playing-Darstellung.
- **Farben** — Farbthema, Akzent- und Darstellungsfarben.
- **Video- / Musik-OSD** — Player-OSD, Live TV und Music OSD.
- **Video- / Musik-Infodialog** — Infofenster für Filme, Serien und Musik.
- **Extras** — zusätzliche Funktionen, Startverhalten und weitere Komfortoptionen.
- **Ressourcen** — externe Bild-/Icon-Ressourcen und Pfade.
- **Unterstützte Addons** — Integrationen mit unterstützten Kodi-Add-ons.
- **Sicherung / Wiederherstellung** — Backup-/Restore-Funktionen.

---

## Home

### Hauptmenü anpassen

**Home → Hauptmenü anpassen** öffnet den nativen Skin-Shortcuts-V3-Editor.

Dort kannst du pro Hauptmenüeintrag typischerweise Titel, Aktion/Ziel, Icon, Aktivstatus, Reihenfolge, Untermenü, Hintergrund und Widgets konfigurieren.

ICU nutzt dafür `script.skinshortcuts` V3. Der Hauptmenü-Include heißt intern `skinshortcuts-mainmenu`, das zusammengefasste Untermenü `skinshortcuts-mainmenu-submenu`.

### Widgets

ICU erhält **sechs unabhängige Widget-Slots**. Jeder Slot kann getrennt konfiguriert werden. Unterstützt werden unter anderem Widgetquelle, Sortierung, Ziel/Target, Darstellung und ein eigener Widget-Titel.

Die Widget-Titel können direkt im Editor geändert werden. Intern werden `widgetLabel`, `widgetLabel.2` bis `widgetLabel.6` verwendet.

Nach Änderungen den Editor sauber schließen. Beim Verlassen der Skin-Einstellungen wird die V3-Konfiguration neu generiert.

### Custom Hubs

Der Skin enthält neun Custom-Hub-Fenster: `1111` bis `1119`. Die zugehörigen generierten Skin-Shortcuts-Includes heißen `skinshortcuts-x1111` bis `skinshortcuts-x1119`.

### Hauptmenü-Stil

Unter **Hauptmenü-Stil** wird die Home-Darstellung gewählt. Welche Zusatzoptionen sichtbar werden, hängt vom ausgewählten Stil ab. Bei Multi-Widget-Layouts können weitere Einstellungen zu Widgetanimationen, Abständen, Vorschaufenstern und Informationsbereichen erscheinen.

---

## Hintergrund

Hier werden Standard- und Fallback-Hintergründe sowie optionale Fanart-/Slideshow-Pfade gesteuert.

Wichtig für ICU:

- Ein im Menüeditor gewähltes **Background=None** fällt auf den normalen Skin-Hintergrund zurück und erzeugt keinen absichtlich schwarzen/null Hintergrund.
- Für den Startbildschirm gibt es einen eigenen Fallback `media/common/startup_icu.png`; dadurch wird `common/bg.jpg` nicht global ersetzt.

Bei Add-ons oder Emby-Nodes können Artwork-Pfade vom Add-on geliefert werden. ICU besitzt Fallbacks für temporäre oder ungültige Menü-Icons.

---

## Ausstattung

Dieser Bereich steuert zusätzliche visuelle Bestandteile („Furniture“). Je nach aktiver Ansicht können hier Einstellungen für Header, Medieninformationen, Ratings, Flags, Indikatoren und ähnliche Elemente verfügbar sein.

### Media Flags

Audio- und Video-Flags werden in ICU für Kodi Piers normalisiert. Die Normalisierung ist automatisch; dafür gibt es keinen separaten Schalter.

Beispiele:

- `truehd_atmos`, `eac3_ddp_atmos` → Atmos
- `dtshd_ma_x`, `dtshd_ma_x_imax` → DTS:X
- `aac_lc`, `he_aac`, weitere AAC-Varianten → AAC
- `h265`, `hvc1`, `hev1`, `x265` → HEVC/H.265-Flag
- `avc`, `avc1`, `x264` → H.264-Flag

Weiße und farbige Video-Source-Flag-Sätze sind im ICU-Stand auf denselben Dateibestand gebracht.

---

## Gerade läuft

Hier wird die allgemeine Now-Playing-Darstellung konfiguriert. Die Optionen betreffen eingeblendete Wiedergabeinformationen außerhalb bzw. zusätzlich zum eigentlichen OSD.

Das **Music-OSD** besitzt zusätzlich einen eigenen Konfigurationsdialog; siehe weiter unten.

---

## Farben

In diesem Bereich werden Farbthema, Highlight-/Akzentfarben und weitere vom Upstream-Skin geerbte Farbanpassungen gesteuert. Einige Farbeingaben verwenden Kodis integrierte Farbauswahl.

Wenn ein Skin-Theme eigene Farben vorgibt, können einzelne Optionen abhängig vom Theme deaktiviert oder überschrieben sein.

---

## Video- / Musik-OSD

Der Bereich enthält getrennte Optionen für Video- und Musik-Wiedergabe sowie Live TV.

### Video-OSD

Hier lassen sich die vom Upstream-Skin angebotenen OSD-Elemente, Informationsanzeigen und Darstellungsoptionen konfigurieren. Media Flags im OSD verwenden die ICU-Codec-Normalisierung.

### Live TV: laufende Sendung statt Sendername

ICU 1.0.18 hat die Option **„Laufende Sendung statt Sendername im Live-TV-OSD anzeigen“** hinzugefügt.

- **Aus:** `VideoPlayer.ChannelName`.
- **An:** `VideoPlayer.Title`.
- Ist `VideoPlayer.Title` leer, fällt der Skin auf den Sendernamen zurück.

Beispiel: Aus `WELT`, An `Newsroom`.

### Music-OSD: CD und Hülle

Der bestehende Schalter **CD und Hülle** (`ShowMusicCD`) aktiviert die kombinierte Cover-/Disc-Darstellung.

### Music-OSD: Nur Albumcover

ICU 1.0.20 ergänzt **„Nur Albumcover anzeigen (CD/DiscArt im Music-OSD ausblenden)“**.

Wenn aktiviert, bleibt das Albumcover sichtbar, während echte DiscArt, Fake-CD, Vinyl-Fallback und Default-CD ausgeblendet werden. Die Option betrifft gezielt das **Music-OSD**; Home bzw. Extended Now Playing werden dadurch nicht umgestellt.

### Fake-CD / Vinyl / DiscArt

Solange **Nur Albumcover** ausgeschaltet und **CD und Hülle** aktiv ist, kann die vorhandene DiscArt-Auswahl verwendet werden. Im Cover-only-Modus ist diese Auswahl absichtlich deaktiviert.

---

## Video- / Musik-Infodialog

Hier wird festgelegt, welche Informationen und Artwork-Typen in den Detaildialogen erscheinen. Der Upstream-Skin unterstützt unterschiedliche Poster-/Keyart-/Fanart-Verwendungen und weitere Informationsblöcke; sichtbare Optionen hängen vom Medientyp und installierten Helper-Add-ons ab.

---

## Extras

### Startvideo / Startup-Playlist

Der Skin kann beim Start eine benutzerdefinierte Video- oder Musikdatei/Playlist abspielen. Der gewählte Pfad wird in `Skin.String(StartupPlaylist)` gespeichert. Ist ein Startup-Medium gesetzt, ruft `Custom_Startup.xml` es über `PlayMedia(...)` auf.

Ist **kein** Startup-Medium gesetzt, zeigt ICU den statischen Startbildschirm `media/common/startup_icu.png`. Der statische Startdialog wechselt nach ungefähr vier Sekunden zum Kodi-Startfenster.

### Sonstige Extras

Weitere Optionen in diesem Bereich stammen überwiegend aus dem Upstream-Skin. Dazu können Trailer-/Cinema-Erlebnis-Funktionen, Indikatoroptionen und zusätzliche Darstellungsfunktionen gehören. Welche Einträge aktiv sind, hängt teilweise von installierten Helper-Add-ons ab.

---

## Ressourcen

Hier werden externe Ressourcen und Pfade für Artwork-/Icon-Pakete eingestellt, zum Beispiel Wettericons, Genre-Bilder oder Studio-/Label-Logos, soweit die entsprechende Skin-Funktion genutzt wird.

---

## Unterstützte Addons

Dieser Bereich bündelt Integrationen mit optionalen Add-ons. In `addon.xml` sind unter anderem Global Search, Embuary Info, Embuary Helper, TheMovieDb Helper und Image Resource Select als Abhängigkeiten definiert.

---

## Sicherung / Wiederherstellung

Nutze diesen Bereich vor größeren Änderungen an Home-Menü, Widgets und Skin-Optionen.

### Skin Shortcuts zurücksetzen

Im Skin-Shortcuts-Editor existiert eine **Restore shortcuts**-/Zurücksetzen-Funktion. Sie sollte nicht routinemäßig nach jedem Update verwendet werden. Ein Reset kann selbst angelegte V3-Menüs und Widgets zurücksetzen.

### V2 → V3

ICU migriert alte Skin-Shortcuts-V2-Daten **nicht automatisch**. Das ist absichtlich so, damit die Konfiguration des alten Skins unangetastet bleibt.

---

## Fehlerdiagnose

Wenn eine Einstellung scheinbar nicht übernommen wird:

1. Skin-Einstellungen schließen, damit `buildxml` ausgeführt wird.
2. Skin neu laden oder Kodi neu starten.
3. Bei Widgets prüfen, ob Quelle, Target und Widget-Titel gespeichert sind.
4. Bei Emby-/Library-Nodes kontrollieren, ob der Node in Kodi selbst erreichbar ist.
5. Kodi-Log auf Skin-XML- oder `script.skinshortcuts`-Fehler prüfen.
6. Erst danach einen Skin-Shortcuts-Reset erwägen.

Für eine strukturierte Prüfung siehe [PIERS_V3_SMOKE_TEST.md](PIERS_V3_SMOKE_TEST.md).
