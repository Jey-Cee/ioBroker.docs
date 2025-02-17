---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.vis-2-widgets-material/README.md
title: Material-Widgets für ioBroker.vis 2.0
hash: QAyGBv5DI9AcG2zSTLWUThe/okJ2NS3QBokkg0UUGlU=
---
![Logo](../../../en/adapterref/iobroker.vis-2-widgets-material/admin/vis-2-widgets-material.png)

![Anzahl der Installationen](http://iobroker.live/badges/vis-2-widgets-material-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.vis-2-widgets-material.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.vis-2-widgets-material.svg)
![NPM](https://nodei.co/npm/iobroker.vis-2-widgets-material.png?downloads=true)

# Material-Widgets für ioBroker.vis 2.0
## Widgets
### Knöpfe und Schalter
![Schalter](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-switches.png)

![Schalter](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-switches-buttons.png)

![Schalter](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-switches-buttons-2.png)

### Uhr
- Analog

![Uhr Analog](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-clock-analog-1.png)

- Analoge Variante

![Uhr Analog 2](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-clock-analog-2.png)

- Digital

![Digital](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-clock-digital-1.png)

- Digital2 (SVG-Text)

![Digital2](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-clock-digital-2.png)

### Einfacher Zustand
Mit diesem Widget können Sie ein Gerät steuern. Boolescher Wert oder Zahl.

- Nummer

![Einfacher Zustand](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-simple-state-1.png)

- Kontrolle

![Einfacher Staat](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-simple-state-2.png)

### Im Widget anzeigen
![Im Widget anzeigen](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-view-in-widget-1.png)

Nicht als Schaltfläche: Die Ansicht kann in voller Größe angezeigt werden und Sie können Elemente in der Ansicht steuern.

![Im Widget anzeigen – Schaltfläche](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-view-in-widget-2.png)

Als Schaltfläche: Sie können eine kleine Miniaturansicht der Ansicht anzeigen und durch Drücken darauf wird sie in voller Größe angezeigt.

### Thermostat
![Thermostat](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-thermostat-1.png)

Darüber hinaus kann ein Verlauf angezeigt werden, wenn Sie ihn aktiviert haben.

### Tatsächlicher Wert mit Diagramm
![Tatsächlicher Wert](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-actual-value-1.png)

![Tatsächlicher Wert mit Diagramm](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-actual-value-2.png)

### Sicherheitskontrolle
![Sicherheitskontrolle](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-security-0.png)

![Sicherheitskontrolle](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-security-1.png)

Sie können die Verzögerung in Sekunden definieren.

Durch die Aktivierung wird die definierte ID mit der Anzahl der Verzögerungssekunden geschrieben und nach Ablauf der Verzögerung wird die definierte ID auf 0 und die Alarm-ID auf „true“ gesetzt.

![Sicherheitskontrolle](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-security-2.png)

### Spieler
![Spieler](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-player.png)

### Karte
![Spieler](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-map-1.png)

### Kamera
![Spieler](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-camera-1.png)

### HTML-Vorlage
![Spieler](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-html-1.png)

Mit der HTML-Vorlage kann jeder beliebige HTML-Code angezeigt werden.
Darüber hinaus können Sie mit diesem Widget auch Bilder oder Iframes anzeigen.

### Jalousien
![Jalousie](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-blinds-1.png)

![Spieler](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-blinds-2.png)

### Farblampe
![RGB](../../../en/adapterref/iobroker.vis-2-widgets-material/img/material-rgb.png)

### Zeitauswahl
## Assistentenzuordnung
### Eine Aussicht – ein Raum
- Thermostat → Widget-Thermostat (Ist, Soll, Luftfeuchtigkeit) mit Gerätename
- Licht Ein/Aus → Einfacher Status Ein/Aus mit Gerätename
- Dimmer → Einfacher Zustand
- Rollladen → Jalousien mit Namen
- Temperatur → tatsächlicher Wert mit Diagramm (wenn möglich, Feuchtigkeit hinzufügen)
- Bewegung → Einfacher Zustand mit spezifischem Symbol (Junge), schreibgeschützt, aktive Farbe rgba(52,170,68,1)
- Feuer → Einfacher Zustand mit spezifischem Symbol (Feuer), schreibgeschützt, aktive Farbe „Rot“
- Überschwemmung → Einfacher Zustand mit spezifischem Symbol (Wasser), schreibgeschützt, aktive Farbe „blau“
- Tür → Einfacher Zustand mit spezifischem Symbol (Tür), schreibgeschützt, aktive Farbe „Rot“
- Schieberegler → Einfacher Zustand
- Sperren → Einfacher Zustand
- Socket → Einfacher Status mit spezifischem Symbol
- Mediaplayer → Mediaplayer
- Lautstärke → einfacher Zustand mit spezifischem Symbol (Lautstärke)
- Wettervorhersage → Openweathermap (nur wenn installiert)
- Fenster → Einfacher Zustand mit bestimmten Symbolen (geöffnet → wahr, geschlossen → falsch)

### Eine Ansicht – alle Räume
- Thermostat → Widget-Thermostat (Ist, Soll, Luftfeuchtigkeit) mit Gerätename
- Licht ein/aus → Schalter und Tastenschalter
- Dimmer → Schalter und Tasten-Schieberegler
- Rollladen → Schalter und Tasten Jalousien
- Temperatur → Schalter- und Tasteninformationen mit Diagramm

-- Luftfeuchtigkeit → Informationen zu Schaltern und Tasten mit Diagramm

- Bewegung → Schalter- und Schaltflächen-Info-spezifisches Symbol, schreibgeschützt, aktive Farbe rgba(52,170,68,1)
- Feuer → ISwitch und Buttons nfo-spezifisches Symbol (Feuer), schreibgeschützt, aktive Farbe „Rot“
- Überschwemmung → Schalter- und Schaltflächeninfo mit spezifischem Symbol (Wasser), schreibgeschützt, aktive Farbe „blau“
- Tür → Schalter- und Tasteninfo mit spezifischem Symbol (Tür), schreibgeschützt, aktive Farbe „Rot“
- Schieberegler → Schalter- und Tastenschieberegler
- Sperren → Schalter und Tastenschalter
- Steckdose → Schalter und Tasten wechseln mit spezifischem Symbol
- Mediaplayer → Mediaplayer (als Karte) mit Raumname
- Lautstärke → Schalter und Tasten-Schieberegler mit spezifischem Symbol (Lautstärke)
- Wettervorhersage → Openweathermap als Karte (nur wenn installiert)
- Fenster → Schalter- und Schaltflächeninformationen mit spezifischen Symbolen (geöffnet → wahr, geschlossen → falsch)

## Machen
- RGBW-Farbcontroller
- Untersuchen Sie die Verzögerung für Widgets

<!-- Platzhalter für die nächste Version (am Anfang der Zeile):

### **ARBEIT IN ARBEIT** -->

## Changelog
### **WORK IN PROGRESS**
* (bluefox) Added RGB widget

### 0.8.5 (2023-08-11)
* (bluefox) Improvement of the widget loading

### 0.8.4 (2023-08-10)
* (bluefox) Improvement of wizard

### 0.8.3 (2023-07-30)
* (bluefox) Font styles are applied to all buttons

### 0.8.2 (2023-07-19)
* (bluefox) Corrected small layout problems

### 0.8.0 (2023-07-18)
* (bluefox) Added wizard for widgets

### 0.7.1 (2023-07-02)
* (bluefox) Added washer widget

### 0.6.2 (2023-06-29)
* (bluefox) Allowed usage without a frame for all widgets

### 0.6.0 (2023-06-28)
* (bluefox) Added blinds to switches widget
* (bluefox) Allowed to place widgets in widgets

### 0.5.3 (2023-06-21)
* (bluefox) Corrected errors with view in widget

### 0.5.1 (2023-06-20)
* (bluefox) Added widget to switch the theme
* (bluefox) Improved HTML widget to show iframe and image

### 0.4.0 (2023-06-16)
* (bluefox) Added button texts for switches widget
* (bluefox) Removed static widget, as it was replaced by switches widget

### 0.3.1 (2023-06-14)
* (bluefox) Improved buttons widget

### 0.2.13 (2023-03-22)
* (bluefox) BREAKING CHANGE: The names of widgets must be entered anew 
* (bluefox) update packages

### 0.2.9 (2023-02-27)
* (bluefox) Made this adapter singleton

### 0.2.2 (2023-02-22)
* (bluefox) Update packages

### 0.2.1 (2022-11-26)
* (bluefox) Implemented the blinds widget

### 0.1.5 (2022-10-27)
* (bluefox) First beta version

### 0.1.2 (2022-10-21)
* (bluefox) initial commit

## License
The MIT License (MIT)

Copyright (c) 2022-2023 bluefox <dogafox@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.