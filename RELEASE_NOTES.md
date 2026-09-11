# Artic: Zephyr ICU 1.0.31
## Kodi 22 “Piers” Compatibility Release

Diese Version konzentriert sich auf die Anpassung und Optimierung des Skins für Kodi 22 “Piers”. Neben neuen PVR-, Wetter- und Video-Funktionen wurden insbesondere EPG-Darstellung, Rendering und Release-Paketierung überarbeitet.

### Highlights

- Kodi-22-kompatibler EPG mit 1-Minuten-Auflösung
- Verbesserte Darstellung sehr kurzer Sendungen und gesetzter Timer
- Neue PVR-Provider-Ansicht inklusive Kodi-22-Labels und zusätzlicher Widgets
- Neuer Video-/Audio-/Untertitel-Stream-Selector für Kodi 22
- Wetterbereich auf die neue `Weather.Data(...)`-API migriert, inklusive Legacy-Fallbacks
- Unterstützung für Filmversionen und Extras über `DialogVideoManager.xml`
- Fullscreen-Rendering für Kodi 22 abgesichert
- Release-Build mit `media/Textures.xbt` statt einzelner Media-Dateien
- Bereinigung veralteter InfoLabels und Conditions

### EPG / PVR

- EPG auf `170` Timeblocks mit `minspertimeblock=1` und `rulerunit=6` umgestellt.
- Dynamische Programmbreiten an die Kodi-22-EPG-Skalierung angepasst.
- Lesbarkeit von 5-/10-Minuten-Sendungen verbessert.
- Timer-Darstellung überarbeitet, sodass Titel nicht mehr aus sehr kurzen Programmblöcken herauslaufen.
- Fokusdarstellung, Zeitraster und „Jetzt“-Linie optisch verfeinert.
- `MyPVRProviders.xml` ergänzt.
- Provider-Navigation für TV und Radio hinzugefügt.
- Unterstützung für `PVR.ClientCount`, `ListItem.PVRClientName`, `ListItem.PVRInstanceName` und `ListItem.MediaProviders` ergänzt.
- Widgets für zuletzt hinzugefügte TV- und Radiosender ergänzt.
- PVR-Sortierung nach `dateadded` freigegeben.

### Stream-Auswahl

- `DialogSelect.xml` um Kodi-22-spezifische Stream-Ansichten erweitert.
- Separate Darstellung für Video-, Audio- und Untertitelstreams.
- Anzeige von Codec, Sprache, Auflösung, HDR, FPS, Bitrate und Audiokanälen, soweit von Kodi bereitgestellt.
- Statuskennzeichen für Default, Forced, Original, Hearing Impaired, Visual Impaired, External und 3D ergänzt.
- Vorhandene Zephyr-Codec- und Sprachgrafiken werden weiterverwendet.

### Wetter

- Wetterdaten schrittweise von `Window(Weather).Property(...)` auf `Weather.Data(...)` migriert.
- Neue Kompatibilitätsschicht mit Fallback auf Legacy-Properties ergänzt.
- Current-, Daily-, Hourly- und Map-Daten an Kodi 22 angepasst.
- `Weather.LastUpdated` integriert.
- „Now“-Wettericon korrigiert: bevorzugt `Weather.ConditionsIcon`, danach `Weather.Data(Current.ConditionIcon)` und Legacy-Fallback.
- Fehlerhafte `animated`-Bedingung im fokussierten „Now“-Element korrigiert.

### Filmversionen und Extras

- `DialogVideoManager.xml` ergänzt.
- Kodi-Core-Steuerungen für Filmversionen und Extras in `DialogVideoInfo` integriert.
- Verwaltung von Versionen und Extras im vorhandenen Zephyr-Design umgesetzt.
- Vorhandene Skin-Grafiken wiederverwendet; keine zusätzlichen Assets erforderlich.

### Rendering und Skinning

- Explizite Fullscreen-Hintergrundfarbe für relevante Fenster ergänzt, um das Rendering-Verhalten von Kodi 22 robuster abzudecken.
- `ListItem.Thumb` durch `ListItem.Art(thumb)` ersetzt.
- Veraltete `DialogFavourites.xml`-Referenzen auf `MyFavourites.xml` umgestellt.
- Audit auf bekannte entfernte bzw. veraltete Kodi-InfoLabels und Conditions durchgeführt.

### Release-Paketierung

- Release-Build verwendet `media/Textures.xbt` im Kodi-22-XBTF-v2-Kompatibilitätsformat.
- Die 1.979 einzelnen Media-Dateien sind im Release-ZIP nicht mehr enthalten.
- Separater Development-Build mit losen Media-Dateien bleibt für Skin-Entwicklung verfügbar.

### Validierung

- 200 XML-Dateien erfolgreich geparst.
- ZIP-Integrität geprüft.
- Regressionstests für EPG, PVR Providers, Stream-Selector, Weather.Data/Now-Icon und VideoManager durchgeführt.
- Release- und Development-Build unterscheiden sich primär in der Media-Paketierung.

### Hinweise

Kodi 22 “Piers” befindet sich während der Entwicklung dieser Version noch im Vorab-/Beta-Zyklus. Kleinere Änderungen an Skinning-APIs bis zur finalen Kodi-22-Version sind daher weiterhin möglich.
