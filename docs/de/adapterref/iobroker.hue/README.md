---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.hue/README.md
title: ioBroker Philips Hue Bridge-Adapter
hash: iJT+orqAnBFHf5VwoZ9V0eNwVozQnYCbZSECUmkv9Bs=
---
![Logo](../../../en/adapterref/iobroker.hue/admin/hue.jpeg)

![Anzahl der Installationen](http://iobroker.live/badges/hue-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.hue.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.hue.svg)

# IoBroker Philips Hue Bridge-Adapter
![Test und Freigabe](https://github.com/iobroker-community-adapters/iobroker.hue/workflows/Test%20and%20Release/badge.svg) [![Übersetzungsstatus](https://weblate.iobroker.net/widgets/adapters/-/hue/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

**Dieser Adapter nutzt den Dienst [Sentry.io](https://sentry.io), um mir als Entwickler automatisch Ausnahmen und Codefehler und neue Geräteschemata zu melden.** Weitere Details siehe unten!

## Was ist Sentry.io und was wird an die Server dieses Unternehmens gemeldet?
Sentry.io ist ein Dienst für Entwickler, um einen Überblick über Fehler in ihren Anwendungen zu erhalten. Genau das ist in diesem Adapter umgesetzt.

Wenn der Adapter abstürzt oder ein anderer Codefehler auftritt, wird diese Fehlermeldung, die auch im ioBroker-Protokoll erscheint, an Sentry übermittelt.
Wenn Sie der ioBroker GmbH erlaubt haben, Diagnosedaten zu sammeln, ist auch Ihre Installations-ID (dies ist nur eine eindeutige ID **ohne** zusätzliche Informationen über Sie, E-Mail, Name oder ähnliches) enthalten. Dadurch kann Sentry Fehler gruppieren und anzeigen, wie viele einzelne Benutzer von einem solchen Fehler betroffen sind. All dies hilft mir, fehlerfreie Adapter bereitzustellen, die im Grunde nie abstürzen.

## Englisch :gb:
Dieser Adapter verbindet Ihre Philips Hue Bridges mit ioBroker, um Philips Hue LED-Lampen, Friends of Hue LED-Lampen, Streifen, Stecker wie von Osram und andere SmartLink-fähige Geräte (wie LivingWhites und einige LivingColors) zu steuern.

### Aufstellen
Nachdem Sie diesen Adapter in ioBroker installiert haben, erstellen Sie eine entsprechende Adapterinstanz. Als nächstes müssen Sie Ihre Hue-Bridge in den Adaptereinstellungen mit ioBroker verbinden:

1. Wenn Sie eine andere Bridge als Version 2 verwenden, konfigurieren Sie den Port auf 80 (nicht https), andernfalls sollte 443 (https) die richtige Wahl sein.
2. Klicken Sie auf die Schaltfläche „Bridge suchen“, um die IP-Adresse Ihrer Bridge zu erhalten. Dadurch wird nach allen Bridges in Ihrer Umgebung gesucht. Wählen Sie dann die Bridge aus, mit der Sie eine Verbindung herstellen möchten. Das Feld „Bridge-Adresse“ wird mit der IP-Adresse der von Ihnen gewählten Hue-Bridge gefüllt.
3. Klicken Sie anschließend in den Einstellungen auf die Schaltfläche „Benutzer erstellen“ und gehen Sie dann zu Ihrem Hue-Bridge-Gerät, also Ihrer Hardware, um dessen runde Taste zu drücken. Sie haben 30 Sekunden Zeit, um fortzufahren. Sobald Sie die Schaltfläche gedrückt haben, sollte das Feld „Bridge-Benutzer“ mit einer generierten Zeichenfolge gefüllt sein.
4. Ändern Sie alle anderen Optionen in den Adaptereinstellungen und wählen Sie dann „Speichern und schließen“.
5. Schließlich sollten Sie bereit sein: Der Adapter generiert alle Objekte, um Ihre Hue-Geräte entsprechend zu steuern.

Bitte beachten Sie: Die Schaltfläche „Bridge suchen“ in den Adaptereinstellungen ist inaktiv, wenn das Feld „Bridge-Adresse“ ausgefüllt ist, und die Schaltfläche „Benutzer erstellen“ ist inaktiv, wenn das Feld „Bridge-Benutzer“ ausgefüllt ist.

### Einstellungen
| Name | Beschreibung |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| __Bridge-Adresse__ | Wenn Sie die IP-Adresse Ihrer Hue-Bridge haben, können Sie versuchen, diese zu ermitteln, indem Sie die Taste `Find Bridge` drücken. |
| __Port__ | Port Ihrer Hue-Bridge, normalerweise 443 (SSL) und 80 (nicht SSL). |
| __Benutzer__ | Benutzername Ihres Bridge-Benutzers. Sie können es erstellen, indem Sie die Taste `Create User` drücken und den Anweisungen auf dem Bildschirm folgen. |
| __Benutzer__ | Benutzername Ihres Bridge-Benutzers. Sie können es erstellen, indem Sie auf die Schaltfläche „Benutzer erstellen“ klicken und den Anweisungen auf dem Bildschirm folgen. |
| __Szenen ignorieren__ | Wenn diese Option aktiviert ist, werden Szenen nicht vom Adapter angezeigt/gesteuert. |
| __"Legacy"-Struktur__ | Um die Abwärtskompatibilität zu unterstützen, ist es möglich, eine alte Objektstruktur in ioBroker zu behalten. Diese alte Struktur ist `hue.<instance_number>.<bridge_name_channel>.<light_or_group_channel>.<state>`. Die neue Struktur entfernt `<bridge_name_channel>` und macht somit die Anpassung alter Skripte etc. erforderlich. Wird vom Adapter eine bestehende alte Struktur erkannt, wird die Struktur ohne Ankreuzen der Checkbox verwendet. Wenn jedoch eine Migration von der alten zur neuen Struktur gewünscht wird, löschen Sie einmal den gesamten `hue.<instance_number>`-Namespace. |
| __"Legacy"-Struktur__ | Um die Abwärtskompatibilität zu unterstützen, ist es möglich, eine alte Objektstruktur in ioBroker zu behalten. Diese alte Struktur ist „hue.<instance_number>.<bridge_name_channel>.<light_or_group_channel>.<state>“. Die neue Struktur entfernt „<bridge_name_channel>“ und macht somit die Anpassung alter Skripte etc. erforderlich. Wird vom Adapter eine bestehende alte Struktur erkannt, wird die Struktur ohne Ankreuzen der Checkbox verwendet. Wenn jedoch eine Migration von der alten zur neuen Struktur gewünscht wird, löschen Sie einmal den gesamten „hue.<instance_number>“-Namespace. |
| __Software-Sensoren synchronisieren__ | Synchronisieren Sie auch Softwaresensoren. Dabei handelt es sich um virtuelle Sensoren, z.B. erstellt von Hue Labs Szenen. Durch die Steuerung des `status` Datenpunkts eines solchen Sensors können Sie Szenen starten/stoppen, die dieser Logik folgen. In den meisten Fällen schaltet `0` die Szene aus und `1` aktiviert sie. |
| __Mit anderen anmachen__ | Lichter auch mit CT-Status, Farbstatus usw. einschalten. Auf `false` einstellen und nur mit Strom- und Helligkeitsstatus einschalten. |
| __Mit anderen anmachen__ | Lichter auch mit CT-Status, Farbstatus usw. einschalten. Auf „false“ setzen und nur mit Strom- und Helligkeitsstatus einschalten. |
| __Umfrage__ | Wenn diese Option aktiviert ist, fragt der Adapter Zustandsänderungen ab, andernfalls kann er nur zur Steuerung von Lampen und nicht zur Anzeige ihres Status verwendet werden. |
| __Abfrageintervall__ | Definiert, wie oft die Zustände abgefragt und somit in ioBroker aktualisiert werden. Niedrige Abfrageintervalle können in einigen Einstellungen zu Leistungsproblemen führen. Daher beträgt das minimal zulässige Abfrageintervall 2 Sekunden. Wenn das Abfrageintervall auf weniger als 2 Sekunden eingestellt ist, wird es zur Laufzeit auf 2 Sekunden eingestellt. |

### Befehle
Befehlszustände (z. B. `hue.0.All.command`) können verwendet werden, um mehrere Befehle an die Bridge zu senden.
Dies ermöglicht es, eine Gruppe oder ein Licht in einen bestimmten Zustand zu versetzen, z.B. eine Übergangszeit.

```javascript
setState('hue.0.All.command', { "bri": 50, "transitiontime": 30 }, false);
```

Für Gruppen, die Szenen enthalten, wie `hue.0.Wohnzimmer.scene_hell`, können die Szenen auch mit einer Übergangszeit aktiviert werden.
Übergeben Sie dazu das Szenenargument an den entsprechenden Befehl.

```javascript
setState('hue.0.All.Wohnzimmer', { "scene": "hell", "transitiontime": 30 }, false);
```

### Weitere Informationen
Mit Version 3.3.0 wurden die Gruppenzustände `anyOn` und `allOn` steuerbar. Beachten Sie, dass sie sich bei Steuerung genauso wie der `on`-Zustand verhalten. In manchen Fällen kann es wünschenswert sein, einen kontrollierbaren `anyOn`-Zustand in Ihrer Visualisierung zu haben.

## Deutsch :de:
Bindet Philips Hue / LivingColors / LivingWhites Lampen ein.
In den Adapter-Einstellungen muss die IP der Hue Bridge sowie ein Benutzername konfiguriert werden. Um einen Benutzer zu aktivieren, drücken Sie einmal auf „Benutzer erstellen“ und drücken Sie dann innerhalb von 30 Sekunden den Button an der Hue Bridge. Dann wird der Benutzer automatisch übergeben.

## Roadmap/Todo
* Automatische Brückenerkennung
* Automatische Benutzereinrichtung über die Bridge-Link-Schaltfläche

## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### __WORK IN PROGRESS__
-->
### 3.9.0 (2023-06-11)
* (foxriver76) implemented poll API (closes #227, #343)
* (foxriver76) fix polling not working (closes #408, #410)

### 3.8.0 (2023-06-09)
* (Schmakus) Possibility to disable turn on lights with states other than `on` and `brightness` [#386]

### 3.7.1 (2022-07-12)
* (Eistee82) also update state for `CLIPGenericFlag` sensors

### 3.7.0 (2022-05-30)
* (foxriver76) support software sensor `CLIPGenericFlag` (closes #328)

### 3.6.5 (2022-01-11)
* (foxriver76) correctly identify third party switches (closes #273)

### 3.6.3 (2022-01-09)
* (foxriver76) added `info.connection` state (closes #268)

### 3.6.1 (2022-01-09)
* (foxriver76) ct values of groups can be even lower due to third party lights

### 3.6.0 (2021-12-30)
* (foxriver76) allow triggering scenes via `command` state, this allows to start a scene with `transitiontime`

### 3.5.31 (2021-11-20)
* (foxriver76) ct value fix of #234 ported for 0 (All) group

### 3.5.30 (2021-11-14)
* (foxriver76) we fixed Sentry IOBROKER-HUE-1K, IOBROKER-HUE-A, IOBROKER-HUE-1J

### 3.5.29 (2021-11-14)
* (bluefox) Caught SENTRY error.

### 3.5.28 (2021-11-04)
* (foxriver76) another fix for invalid ct values (fixes #234)

### 3.5.27 (2021-11-01)
* (foxriver76) we fixed missing object type of some scenes (closes #255)

### 3.5.26 (2021-10-20)
* (foxriver76) fixed an issue with the username set in Hue API (fixes 249)
* (klein0r) fixed translation of search popup (fixes #247)

### 3.5.25 (2021-09-15)
* (foxriver76) if we cannot determine correct ct value, we won't set it (fixes #234)

### 3.5.23 (2021-08-26)
* (Pmant) fix for third party devices delivering wrong ct values

### 3.5.22 (2021-08-12)
* (foxriver76) fixed several sentry issues (closes #217, closes #218, closes #219, closes #220)

### 3.5.20 (2021-08-10)
* (foxriver76) we now define minimum ct of groups to 2000 instead of 2179 (fixes #216)

### 3.5.19 (2021-06-02)
* (foxriver76) fix crash case if we cannot get min/max ct values

### 3.5.18 (2021-06-01)
* (foxriver76) get the correct min/max ct values from api for lights (closes #192)

### 3.5.17 (2021-05-26)
* (foxriver76) prevent edge case crash (fixes #196)

### 3.5.16 (2021-05-07)
* (foxriver76) make buttons type `boolean` (closes #189)

### 3.5.15 (2021-05-05)
* (foxriver76) fixed some default type values, which produced warnings once

### 3.5.14 (2021-05-04)
* (foxriver76) protect the user token from access by foreign adapters
* (foxriver76) fixed types of default values on groups

### 3.5.13 (2021-05-03)
* (foxriver76) we fixed some more types

### 3.5.12 (2021-05-02)
* (foxriver76) we give skipped switches common.type 'mixed' instead of none
* (foxriver76) we have corrected the min max of color temperature (empirically found)

### 3.5.11 (2021-05-02)
* (foxriver76) we now update objects if type has changed

### 3.5.10 (2021-04-30)
* (foxriver76) we removed the common.max from lightlevel, was 17,000 but can be much higher
* (foxriver76) we added common.type for states where the attribute was missing

### 3.5.9 (2021-04-30)
* (foxriver76) start this adapter in TIER 2

### 3.5.8 (2021-04-17)
* (foxriver76) minor changes

### 3.5.5 (2021-04-07)
* (foxriver76) fixed a bug where an error on user creation crashed the adapter instance

### 3.5.4 (2021-03-25)
* (foxriver76) fixing several edge case crashes

### 3.5.2 (2021-02-24)
* (foxriver76) fix crashes if wrong data type or invalid value passed for ct and hue, now logging an error
* (foxriver76) fix crashes if rgb where outside allowed range or wrong type
* (foxriver76) fix potential crashes on bridge discovery, due to unnecessary stringify/parse logic
* (foxriver76) fix graphical issue with the label of bridge user when newly created, due to missing call of updateTextFields

### 3.5.1 (2021-02-20)
* (foxriver76) avoid crash cases on invalid xy, setting state for non-existing device and on failing user creation

### 3.5.0 (2021-02-18)
* (foxriver76) use official js-controller regex for replacing forbidden chars (fixes #165)
* (foxriver76) use release-script
* (foxriver76) sentry added

### 3.4.0 (2021-01-20)
* (foxriver76) we now restart the adapter automatically to add new devices if they have been added to bridge

### 3.3.11 (2021-01-12)
* (foxriver76) fixed updating `anyOn` and `allOn` if legacy structure used

### 3.3.9 (2021-01-11)
* (foxriver76) we do not set states of non-existing states anymore

### 3.3.8 (2020-10-11)
* (foxriver76) marked read-only states accordingly

### 3.3.7 (2020-10-04)
* (Apollon77) do not catch undhandeledRejections anymore, because controller can handle and report now
* (foxriver76) dependencies updated
* (foxriver76) temperature is now correctly read-only
* (foxriver76) fix duplicate filtering on browse

### 3.3.5 (2020-06-03)
* (foxriver76) fixed issue on frontend validation of polling intervals starting with 1

### 3.3.4 (2020-06-02)
* (foxriver76) implemented fix for problems with switches and handling id conflicts

### 3.3.3 (2020-05-31)
* (foxriver76) we now handle potential id conflicts, when adding devices from different type with same name over time

### 3.3.2 (2020-05-15)
* (foxriver76) internal optimizations - polling after change timeout removed, was 150 ms now instant

### 3.3.0 (2020-05-14)
* (foxriver76) introduce `allOn` state for groups
* (foxriver76) `anyOn` and `allOn` are now controllable and act like the `on` state
* (foxriver76) when native turn on/off behaviour is used, the brightness change of partially turned on groups will not turn
the whole group on, like the hue app does instead it will only change the brightness of the currently turned on lamps

### 3.2.9 (2020-05-12)
* (foxriver76) fixed issues on user creation
* (foxriver76) minor frontend (admin config) optimizations

### 3.2.8 (2020-04-26)
* (foxriver76) replace dots in light/group/sensor/.. names by underscores
* (foxriver76) fix potential state update delay after state change on lights/groups containing blanks

### 3.2.4 (2020-04-08)
* (xXBJXx) changed role of battery to `value.battery` and made unit `%`

### 3.2.3 (2020-02-20)
* (Apollon77) minor fix regarding handleParam called with non-existing id

### 3.2.2 (2020-02-12)
* (foxriver76) fix potential issues when error type is not HueError

### 3.2.1 (2020-01-26)
* (foxriver76) if lights/groups/sensors are deleted during runtime, restart of adapter is no longer necessary
* (foxriver76) if controller supports recursive deletion, device will be deleted automatically

### 3.1.1 (2020-01-15)
* (foxriver76) added additional frontend validation of polling interval
* (foxriver76) if errors are hue errors, log message instead of Error

### 3.1.0 (2020-01-12)
* (foxriver76) added new indicators for entertainment groups (class and activeStream)
* (foxriver76) added possibility to enable/disable streaming of entertainment group

### 3.0.3 (2020-01-11)
* (foxriver76) fixed turning on/off switchs like Osram Plug

### 3.0.1 (2020-01-10)
* (foxriver76) removed queue, because handled by dependency now
* (foxriver76) improved error handling
* __Nodejs >= 10 required__

### 2.5.0 (2019-12-23)
* (foxriver76) implemented a mechanic to prevent regular polling of recently changed state
* (foxriver76) this prevents fluctuating of buttons on low polling intervals + possible strange triggers in scripts

### 2.4.7 (2019-12-14)
* (foxriver76) do not set default values on every adapter start
* (foxriver76) this is now done only on object creation

### 2.4.6 (2019-12-06)
* (foxriver76) log unhandeld promise rejections
* (foxriver76) fix potential issue for negative temperature values

### 2.4.4 (2019-11-27)
* (foxriver76) only stringify huge jsons if necessary
* (foxriver76) prevent possible double polling at adapter start
* (foxriver76) use timeouts instead of interval
* (foxriver76) improved performance

### 2.4.3 (2019-11-19)
* (foxriver76) increased version of node-hue-api to fix authentication for old bridge

### 2.4.2 (2019-11-16)
* (foxriver76) we now use nupnp + upnp to discover bridges (previously only upnp)

### 2.4.1 (2019-11-13)
* (foxriver76) added possibility to control zones and entertainment areas
* (foxriver76) log queue retires on debug instead warn
* (foxriver76) __BETA__: added possibility to control software sensors (Note: this may be handled in a more suitable fashion soon)

### 2.3.1 (2019-11-02)
* (foxriver76) fixed controlling `on` state of sensors

### 2.2.3 (2019-10-21)
* (foxriver76) migrate everything to Hue v3
* (foxriver76) add possibility to turn on/off sensor
* (foxriver76) add anyOn state for all group
* (foxriver76) different kinds of fixes for v3 (Osram Plugs, SSL connection, etc)

### 2.1.0 (2019-10-15)
* (foxriver76) usage and adaptions for node-hue-api v3
* (foxriver76) ability to turn lights on with last settings
* (foxriver76) polling interval minimum is now 2 sec

### 2.0.1 (2019-10-04)
* (foxriver76) fixed bug, that prevented some sensor states getting updated during runtime

### 2.0.0 (2019-09-23)
__ATTENTION: Remove all objects once, ids have changed__
* (foxriver76) internal optimizations
* (foxriver76) usage of iobroker testing
* (foxriver76) add possibility to sync scenes
* (foxriver76) restart adapter when room is deleted in app
* (foxriver76) fix .hue value, user had to set 0-360° but adapter set 0-65535
* (foxriver76) fix .color.temperature
* (foxriver76) remove unnecessary bridge channel, adapter namespace is the bridge
* (foxriver76) add "update available" indicator for light bulbs
* (foxriver76) we now poll the root endpoint instead of (|lights| + |groups| + |sensors|) endpoints every pollingInterval seconds
* (foxriver76) min poll interval now 3 seconds instead of 5 seconds
* (foxriver76) add new indicator state 'anyOn'

### 1.2.4 (2019.09.18)
* (Apollon77) Make compatible with js-controller 2.0

### 1.2.3 (2019.03.11//2019.07.07)
* (jens-maus) Refactored command queue handling to use 'bottleneck' package so that command execution are processed with minimum delay.

### 1.1.2 (2019.01.25)
* (BasGo) Added compact mode

### 1.1.1 (2018.08.17)
* (bluefox) Ignoring of groups was implemented

### 1.1.0 (2018.08.17)
* (bluefox) The command queue was optimized

### 1.0.1 (2018.08.14)
* (bluefox) Roles were adjusted
* (bluefox) temperature changed from 153-cold, 500-warm to 2200-warm, 6500-cold
* (bluefox) hue changed from 0-65535 to 0-360°

### 1.0.0 (2018.04.12)
* (arteck) Enable/Disable OSRAM check from HUE Bridge
* (arteck) polling ZLLSwitch and ZGPSwitch     
* (bluefox) admin3
* (bluefox) do not send commands ofter than 10 in 10 seconds

### 0.6.9 (2017.05.18)
* (bluefox) Enable adapter by default

### 0.6.8 (2017.04.22)
* (bluefox) Poll groups

### 0.6.7 (2017.04.21)
* (bluefox) Fix error with turn on the lamp on start
* (bluefox) configurable port

### 0.6.6 (2017.04.20)
* (bluefox) Use new version of npm library

### 0.6.0 (2016.11.30)
* (pmant) support new lamps
* (pmant) add light name to log

### 0.5.9 (2016.10.11)
* (pmant) fix error with null values

### 0.5.8 (2016.06.05)
* (bluefox) fix typo

### 0.5.7 (2016.06.05)
* (soef) write back known states for group/room
* (soef) Integer conversion for bri_inc command

### 0.5.6
* (Pmant) (experimental) support for power switches

### 0.5.5
* (Pmant) fix error with xy state
* (Pmant) support level in command state

### 0.5.4
* (Pman) Lightset 0 fixed
* (Pman) support for diffent gamuts
* (Pman) support Rooms (new HUE App)

### 0.5.3
* (soef) Default Lightset 0 added

### 0.5.2
* (Pman) fix jscs warnings
* (Pman) improve RGB conversion
* (Pman) add update rgb color

### 0.5.1
* (Pman) fix find bridge popup

### 0.5.0
* (Pman) update to node-hue-api 1.2.x
* (Pman) add level state (bri percentage)

### 0.4.4
* (bluefox) fix config edit

### 0.4.3
* (Pmant) fix adapter crash

### 0.4.2
* (Pmant) add find bridge (experimental)
* (Pmant) add create user (experimental)
* (Pmant) fix enable polling

### 0.4.1
* (Pmant) calculate and write back inc values

### 0.4.0
* (Pmant) add command state

### 0.3.2
* (Pmant) add groups as channels (write only)
* (Pmant) fix prevent duplicate channel names

### 0.3.1
* (Pmant) fix another bug with spaces
* (Pmant) fix hue/sat bug
* (Pmant) fix effect bug
* (Pmant) fix xy colormode

### 0.3.0
* (Pmant) fix rgb states only for color lights
* (Pmant) change set known state changes immediately
* (Pmant) change on/off sets brightness to 254/0
* (Pmant) change changing any color (hs,ct,xy) while light is off sets brightness to max
* (Pmant) fix set brightness to zero if light is off
* (Pmant) change set bri to zero if lamp is not reachable
* (Pmant) fix bridges and lamps with spaces in name

### 0.2.1
* (Pmant) add rgb states (write only)
* (Pmant) fix parent/children warnings
* (Pmant) add switch light off if brightness is zero

### 0.1.4
* (bluefox) fix some null objects

### 0.1.3
* (hobbyquaker) config UI
* (hobbyquaker) added children

### 0.1.2
* (hobbyquaker) fixes

### 0.1.1

* (hobbyquaker) fixed min/max attributes
* (hobbyquaker) added common.oper.read/write attributes

### 0.1.0

* (hobbyquaker) first release

## License

Apache 2.0

Copyright (c) 2017-2023 Bluefox <dogafox@gmail.com>
Copyright (c) 2014-2016 hobbyquaker