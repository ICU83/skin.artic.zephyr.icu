# Installation und Update

## Voraussetzungen

Artic: Zephyr ICU 1.0.27 ist für **Kodi Piers / v22** ausgelegt. `addon.xml` verlangt:

- `xbmc.gui` 5.18.0
- `script.skinshortcuts` 3.0.2~beta16
- `script.globalsearch` 5.0.0
- `script.image.resource.select` 0.0.5
- `resource.images.weathericons.white` 0.0.6
- `script.embuary.info` 0.0.1
- `script.embuary.helper` 1.2.14
- `plugin.video.themoviedb.helper` 0.0.1

Kodi installiert verfügbare Abhängigkeiten normalerweise automatisch. Falls die benötigte Skin-Shortcuts-V3-Version in der verwendeten Quelle nicht verfügbar ist, muss eine kompatible V3-Version vor dem Skin installiert werden.

## Erstinstallation aus ZIP

1. Kodi öffnen.
2. **Einstellungen → System → Add-ons** öffnen und bei Bedarf die Installation aus unbekannten Quellen erlauben.
3. **Add-ons → Aus ZIP-Datei installieren** öffnen.
4. `skin.artic.zephyr.icu-<version>.zip` auswählen.
5. Installation und Abhängigkeiten abwarten.
6. Den Skin aktivieren, wenn Kodi danach fragt.

## Update über eine bestehende ICU-Version

Eine neuere ICU-ZIP kann direkt über die installierte ICU-Version installiert werden. Die Add-on-ID bleibt `skin.artic.zephyr.icu`.

Nach einem Update empfiehlt sich:

1. Skin einmal neu laden oder Kodi neu starten.
2. Hauptmenü und Widgets öffnen.
3. Bei Änderungen an Skin Shortcuts die Skin-Einstellungen einmal öffnen und wieder verlassen; dadurch wird `buildxml` ausgeführt.

Ein allgemeiner **Skin-Shortcuts-Reset ist nicht erforderlich** und sollte nur zur Fehlerdiagnose verwendet werden.

## Umstieg vom alten V2-Skin

Die ICU-Portierung verändert vorhandene Skin-Shortcuts-V2-Benutzerdaten des alten `skin.arctic.zephyr.mod` absichtlich nicht. Das V3-Format wird unabhängig aufgebaut.

Das bedeutet:

- alte V2-Daten bleiben erhalten,
- sie werden nicht automatisch importiert,
- Hauptmenü/Widgets müssen im ICU-Skin bei Bedarf neu eingerichtet werden.

## Sicherung

Vor größeren Änderungen an Menüs, Widgets oder Skin-Einstellungen empfiehlt sich die im Skin vorhandene Kategorie **Sicherung / Wiederherstellung**. Bei manuellen Kodi-Backups sollte zusätzlich das Kodi-Benutzerprofil gesichert werden.

## Deinstallation

Beim Entfernen des Skins entscheidet Kodi, ob Add-on-Daten mit entfernt werden. Wer seine ICU-Konfiguration behalten möchte, sollte vorher eine Sicherung anlegen und Benutzerdaten nicht manuell löschen.
