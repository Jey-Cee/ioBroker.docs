---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.samsung/README.md
title: kein Titel
hash: fMqJKEXdLxR/Yz6PqBYEwadR+vbNNnWrf9oAuEToQ3Y=
---
![Logo](../../../en/adapterref/iobroker.samsung/admin/samsung.png)

![Anzahl der Installationen](http://iobroker.live/badges/samsung-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.samsung.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.samsung.svg)

### IoBroker.samsung
![Testen und freigeben](https://github.com/iobroker-community-adapters/ioBroker.samsung/workflows/Test%20and%20Release/badge.svg) <!-- [![Übersetzungsstatus](https://weblate.iobroker.net/widgets/adapters/-/samsung/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget) -->

**Dieser Adapter verwendet Sentry-Bibliotheken, um Ausnahmen und Codefehler automatisch an die Entwickler zu melden.** Weitere Details und Informationen zum Deaktivieren der Fehlerberichterstattung finden Sie unter [Sentry-Plugin-Dokumentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry-Berichte werden ab js-controller 3.0 verwendet.

#### Beschreibung
Adapter für Samsung Fernseher

### Ersterstellung
Dieser Adapter wurde ursprünglich von @soef unter https://github.com/soef/ioBroker.samsung erstellt, aber nicht mehr gepflegt, also haben wir ihn in die iobroker-community verschoben, damit Fehler behoben werden können. Danke @soef für seine Arbeit.
Adapter wurde seitdem von jogibear9988 und mwp007 mit weiteren Api erweitert.

#### Aufbau
Geben Sie die IP Ihres Samsung-Fernsehers ein.
Wählen Sie Ihre API: Samsung Remote - Fernseher vor 2014 Nach der Installation müssen Sie die neue Verbindung auf Ihrem Fernseher bestätigen Samsung HJ - 2014 und 2015 Nach der ersten Verbindung müssen Sie die auf Ihrem Fernseher angezeigte PIN eingeben.
Samsung2016 - selbsterklärendes SamsungTV - Tizen TVs nach 2016

#### Installation
über ioBroker Admin.

Andernfalls führen Sie den folgenden Befehl im ioBroker-Stammverzeichnis aus (z. B. in /opt/iobroker)

```
iobroker install samsung
```

oder

```
npm install iobroker.samsung
```

#### Anforderungen
Samsung-Fernseher<br> HJ-Serie von mir auf UE55HU7200 getestet. Support für Geräte ab 2016 experimentell falls etwas nicht funktioniert, im Log nachschauen.

## Changelog

### __WORK IN PROGRESS__
* (Apollon77) Only Wake-On-Lan SamsungTVs on adapterstart if no token is configured

### 0.5.11 (2022-06-02)
* (Apollon77) Optimize checkOnOff logic on adapter start

### 0.5.10 (2022-05-27)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.9 (2022-05-27)
* (Apollon77) fix crash when initializing a SamsungTV (Tizen)

### 0.5.8 (2022-04-23)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.7 (2022-04-19)
* (Apollon77) Adjust logic to detect if TV is on or off

### 0.5.6 (2022-03-31)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.5 (2022-03-30)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.4 (2022-03-30)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.3 (2022-03-29)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.2 (2022-03-29)
* (Apollon77) Fix crash cases reported by Sentry

### 0.5.1 (2022-03-25)
* (Apollon77) General updates
* (Apollon77) Add Sentry for Crash reporting

### 0.5.0
* New api Type for H and J Series (2014 + 2015)

### 0.4.0
* New api Type, removed node 4 check

### 0.2.9
* Update utils.js and usage, CI Testing and deps (Apollon77)",

## License
The MIT License (MIT)

Copyright (c) 2015-2017 soef <soef@gmx.net>, 2018-2022 ioBroker Community