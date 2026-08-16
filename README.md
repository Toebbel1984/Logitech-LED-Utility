# Logitech LED Utility

![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-0078D6)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB)
![Version](https://img.shields.io/badge/Version-0.3.0-2ea44f)

**Logitech LED Utility** ist eine Windows-Anwendung für per-key RGB-fähige Logitech-G-Tastaturen.  
Sie bietet reaktive Tasteneffekte, Screen-Sampling, CPU-/GPU-Temperaturvisualisierung, eigene Farbprofile, Hotkeys sowie Unterstützung für externe JSON- und Python-Effekte.

Die Ansteuerung erfolgt über das **Logitech LED SDK**.

---

## Features

- **23 integrierte Effekte**
  - 19 reaktive Keypress-Effekte
  - Screen Sampler
  - CPU Temperature
  - GPU Temperature
  - CPU + GPU Temperature
- Individuelle Farben und Parameter pro Effekt
- Globale Hotkeys für Effektwechsel, Geschwindigkeit, Helligkeit und Farben
- Tray-Menü und Einstellungsoberfläche
- Externe Effekte über **JSON**
- Optionale externe Effekte über **Python-Plug-ins**
- Unterstützung für **Logitech Effekt Editor / LGFX-v1**
- Rekursive Effekt-Unterordner im Tray-Menü
- Portable JSON-Konfiguration
- PyInstaller-Build für eine Windows-EXE
- Automatisierte Tests und Projektvalidierung

---

## Voraussetzungen

- Windows 10 oder Windows 11
- Per-key RGB-fähige Logitech-G-Tastatur
- Logitech G HUB oder Logitech Gaming Software
- Logitech LED SDK DLLs unter:
  - `SDK/x64/`
  - `SDK/x86/`

---

## Integrierte Effekte

### Reaktive Keypress-Effekte

- Ring Explosion
- Cross Shock
- Heat Bloom
- Domino Row
- Rebound Wave
- Random Pulse
- Random Key Color
- Lightning
- Rainbow Ring
- Magnetic Pulse
- Plasma Ripple
- Electric Arc
- Comet Trail
- Gravity Well
- Neon Splash
- Laser Scan
- Matrix Drop
- Pulse Grid
- Shockline

### Weitere Effekte

- Screen Sampler
- CPU Temperature
- GPU Temperature
- CPU + GPU Temperature

---

## Temperatur-Effekte

Die Temperatur-Effekte visualisieren CPU- und GPU-Sensordaten direkt auf der Tastatur.

### CPU

| Temperatur | Farbe |
|---|---|
| unter 65 °C | Grün |
| 65 bis unter 80 °C | Orange |
| ab 80 °C | Rot |

### GPU

| Temperatur | Farbe |
|---|---|
| unter 65 °C | Magenta |
| 65 bis unter 80 °C | Blau |
| ab 80 °C | Cyan |

Unter 80 °C pulsieren die Farben leicht.  
Ab 80 °C wechseln die Effekte zu einem schnellen Warnblinken.

Beim kombinierten Effekt **CPU + GPU Temperature** wird die CPU auf der linken und die GPU auf der rechten Tastaturhälfte dargestellt.

---

## Standard-Hotkeys

Die Standardbelegung befindet sich in `config/default.json`.

| Aktion | Hotkey |
|---|---|
| Zufälliger Effekt | `F12` |
| Vorheriger Effekt | `Ctrl + F11` |
| Nächster Effekt | `Ctrl + F12` |
| Geschwindigkeit erhöhen | `Num +` |
| Geschwindigkeit verringern | `Num -` |
| Helligkeit erhöhen | `Ctrl + Num +` |
| Helligkeit verringern | `Ctrl + Num -` |
| Farbe ändern + | `Alt + Num +` |
| Farbe ändern - | `Alt + Num -` |
| Farbstärke erhöhen | `Shift + Num +` |
| Farbstärke verringern | `Shift + Num -` |

Die Belegung kann über die Konfiguration angepasst werden.

---

## Externe Effekte

Benutzerdefinierte Effekte werden im Verzeichnis

```text
effects/
```

abgelegt.

Dort befinden sich die fest eingebauten Effektmodule der Anwendung.

### JSON-Effekte

Die Utility unterstützt externe JSON-Effekte und Keyframe-Animationen.

## Logitech Effekt Editor / LGFX-v1

Die Keyframe-Engine unterstützt Exporte des Logitech Effekt Editors mit:

```json
{
  "fx": 1,
  "engine": "keys"
}
```

Unter anderem werden unterstützt:

- `renderer_fps`
- Frame-Dauern in Renderer-Frames
- Effektgeschwindigkeit über `speed`
- `forward`
- `reverse`
- `bounce`
- `random`
- deutsche Aliasnamen der Loop-Modi
- `NONE` als harter Framewechsel
- kanonische LGFX-Keynamen
- Legacy- und deutsche Editor-Keynamen
- DE-QWERTZ-Zuordnung für `Y` und `Z`
- Unterordner als Tray-Untermenüs

---

## Konfiguration

Die portable Laufzeitkonfiguration befindet sich in:

```text
Logitech_LED_utility.json
```

Die Ausgangskonfiguration liegt unter:

```text
config/default.json
```

Darin werden unter anderem Hotkeys, Effektparameter, Farbprofile und Anwendungseinstellungen gespeichert.

---

## Hinweise

- Die Anwendung ist für Windows und das Logitech LED SDK ausgelegt.
- Nicht jede Logitech-Tastatur unterstützt per-key RGB.
- Für Temperaturdaten können Administratorrechte erforderlich sein.

---
