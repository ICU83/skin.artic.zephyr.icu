# Skin Shortcuts V3 in Artic: Zephyr ICU

## Ziel

ICU verwendet `script.skinshortcuts` **nativ in der V3-Struktur**. Der Port vermeidet eine automatische Manipulation alter V2-Benutzerdaten und erhält gleichzeitig den Zephyr-Menüeditor, Untermenüs, Widgets und Hubs.

## Abhängigkeit

`addon.xml` verlangt derzeit `script.skinshortcuts` **3.0.2~beta16**. Dieser Mindeststand wurde gewählt, weil frühere V3-Stände Probleme mit verschachtelten Library-/Addon-Pickern hatten, die insbesondere bei Emby-Nodes sichtbar werden konnten.

## V3-Konfigurationsdateien

- `shortcuts/menus.xml`
- `shortcuts/widgets.xml`
- `shortcuts/backgrounds.xml`
- `shortcuts/properties.xml`
- `shortcuts/templates.xml`

Veraltete V2-Konfigurationsdateien wie `*.DATA.xml`, `overrides.xml` oder das frühere monolithische `template.xml` gehören nicht mehr zur ICU-V3-Konfiguration.

## Generierte Includes

- Hauptmenü: `skinshortcuts-mainmenu`
- Untermenü: `skinshortcuts-mainmenu-submenu`
- Custom Hubs: `skinshortcuts-x1111` bis `skinshortcuts-x1119`

Die generierte Laufzeitdatei `script-skinshortcuts-includes.xml` wird nicht als statische Projektdatei gepflegt. Sie entsteht aus der Benutzerkonfiguration.

## Build-Aufrufe

Beim Laden von Home sowie beim Verlassen der Skin-Einstellungen wird Skin Shortcuts angewiesen, die XML-Includes zu bauen. ICU verwendet z. B. `RunScript(script.skinshortcuts,type=buildxml)`. Der Menüeditor nutzt die V3-kompatible `manage,menu=...`-Syntax.

## Sechs Widget-Slots

ICU erhält sechs getrennte Widgets. Slot 1 verwendet die Basiseigenschaften; Slot 2–6 die Suffixe `.2` bis `.6`. Das gilt auch für den editierbaren Widget-Titel (`widgetLabel`, `widgetLabel.2` … `widgetLabel.6`).

## Widget-Targets und Quellen

Die V3-Portierung speichert Pfad, Typ, Target und Source getrennt. Für Video-/Library-Nodes ist das wichtig, da Kodi/Emby Quellen wie `library://video/...` liefern können. Die Widget-Templates enthalten Fallbacks für gültige List-/Fixedlist-Controltypen.

## Untermenüs und Hubs

ICU verwendet `skinshortcuts-mainmenu-submenu` für das gemeinsame Untermenü. Die Hub-Fenster `1111` bis `1119` beziehen ihre generierten Listen aus `skinshortcuts-xNNNN`.

## Reset und alte V2-Daten

ICU versucht **nicht**, die V2-Daten des alten `skin.arctic.zephyr.mod` automatisch umzuschreiben oder zu importieren. Dadurch kann der alte Skin parallel bestehen bleiben.

## Debugging

1. Skin-Einstellungen öffnen und wieder schließen (`buildxml`).
2. Kodi-Log auf `script.skinshortcuts`-Fehler prüfen.
3. Quelle/Path/Target im Editor kontrollieren.
4. Library-/Emby-Node zuerst direkt in Kodi öffnen.
5. Erst als letzten Schritt V3-Shortcuts zurücksetzen.

Siehe auch [PIERS_V3_SMOKE_TEST.md](PIERS_V3_SMOKE_TEST.md).
