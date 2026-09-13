# Artic: Zephyr ICU 1.0.32
## EPG Focus Maintenance Release

Version 1.0.32 übernimmt den Kodi-22-/EPG-Stand aus 1.0.31 und korrigiert zwei Darstellungsfehler im EPG-Grid.

### EPG / PVR

- Überlagerung des fokussierten Programmeintrags in `MyPVRGuide.xml` (`epggrid` / Control 10) mit benachbarten Grid-Einträgen behoben.
- Den zusätzlichen `common/box21.png`-Focus-Rahmen entfernt, der durch Kodis Render-Reihenfolge des fokussierten EPG-Elements über Nachbareinträge gezeichnet werden konnte.
- Fade-/Scroll-Darstellung des fokussierten Programmtitels wieder aktiviert, damit auch sehr kurze Sendungen (z. B. 5 Minuten) lesbar dargestellt werden.
- Timer-/Recording-Darstellung sowie die 1-Minuten-Zeitskala (`170` Timeblocks, `minspertimeblock=1`, `rulerunit=6`) bleiben unverändert.

### Basis

- Enthält weiterhin sämtliche Kodi-22-„Piers“-Kompatibilitätsanpassungen aus Version 1.0.31.
- Release-Paket verwendet weiterhin `media/Textures.xbt`.

### Validierung

- XML-Struktur des Skins geprüft.
- ZIP-Integrität geprüft.
- Versionsangaben und Release-Metadaten auf 1.0.32 abgeglichen.
- `MyPVRGuide.xml` entspricht dem bestätigten Stand mit behobener Focus-Überlagerung und aktiver Fade-/Scroll-Darstellung.
