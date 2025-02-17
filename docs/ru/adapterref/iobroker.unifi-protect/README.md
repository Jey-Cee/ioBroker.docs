---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.unifi-protect/README.md
title: ioBroker.unifi-защита
hash: QANKqdkfOjhoVCrxVCEXj04jEbvXlS9y2vBQjNABsrA=
---
![Логотип](../../../en/adapterref/iobroker.unifi-protect/admin/unifi-protect.png)

![версия NPM](http://img.shields.io/npm/v/iobroker.unifi-protect.svg)
![Загрузки](https://img.shields.io/npm/dm/iobroker.unifi-protect.svg)
![Количество установок (последние)](http://iobroker.live/badges/unifi-protect-installed.svg)
![Количество установок (стабильно)](http://iobroker.live/badges/unifi-protect-stable.svg)
![Статус зависимости](https://img.shields.io/david/peterbaumert/iobroker.unifi-protect.svg)
![Известные уязвимости](https://snyk.io/test/github/peterbaumert/ioBroker.unifi-protect/badge.svg)
![НПМ](https://nodei.co/npm/iobroker.unifi-protect.png?downloads=true)

# IoBroker.unifi-защита
**Этот адаптер использует службу [Sentry.io](https://sentry.io), чтобы автоматически сообщать мне как разработчику об исключениях и ошибках кода, а также о новых схемах устройств.** Подробнее см. ниже!

## Адаптер unifi-protect для ioBroker
Подключается к контроллеру Unifi Protect и извлекает все данные с добавленных камер.

Стандартные порты, если не изменены самостоятельно:

 - Облачный ключ Plus Gen2: 7443
 - УДМ Про: 443

## Примеры для getThumbnail и getSnapshot
```
// Settings
const path = '/opt/iobroker/tmp/temp.jpg';
const threshold = 50;

// Send to Telegram ( or what you prefer )
function sendImage(path) {
    sendTo('telegram.0', path);
}

//Trigger Script
on({ id: 'unifi-protect.0.motions.lastMotion.thumbnail', change: "ne" }, function () {
    const thumb = getState('unifi-protect.0.motions.lastMotion.thumbnail'/*thumbnail*/).val;
    const end = getState('unifi-protect.0.motions.lastMotion.end'/*thumbnail*/).val;
    const cameraid = getState('unifi-protect.0.motions.lastMotion.camera'/*thumbnail*/).val;
    const score = getState('unifi-protect.0.motions.lastMotion.score'/*thumbnail*/).val;
    if (score < threshold) { return; }
    // if Event has ended send the Thumbnail otherwise get current Snapshot
    if (end != null) {
        sendTo('unifi-protect.0', 'getThumbnail', { "thumbnail": thumb, "path": path }, function (res) {
            sendImage(path);
        });
    } else {
        sendTo('unifi-protect.0', 'getSnapshot', { "cameraid": cameraid, "path": path }, function (res) {
            sendImage(path);
        });
    }
});
```

```
sendTo('unifi-protect.0', 'getSnapshot', { "cameraid": "5e4a861c01d12503870003f9", "path": path }, function (res) {
    sendImage(path);
});
```

## Что такое Sentry.io и что передается на серверы этой компании?
Sentry.io — это сервис для разработчиков, позволяющий получить обзор ошибок их приложений. И именно это реализовано в данном адаптере.

Когда адаптер выходит из строя или возникает другая ошибка кода, это сообщение об ошибке, которое также появляется в журнале ioBroker, отправляется в Sentry. Когда вы разрешаете iobroker GmbH собирать диагностические данные, также включается ваш идентификатор установки (это просто уникальный идентификатор **без** какой-либо дополнительной информации о вас, электронной почте, имени и т. д.). Это позволяет Sentry группировать ошибки и показывать, сколько уникальных пользователей затронуто такой ошибкой. Все это помогает мне создавать безошибочные адаптеры, которые практически никогда не дают сбоев.

## Использование кода
Код в [Protect_api](./protect_api) в основном скопирован из [hjdhjd's homebridge-unifi-protect](https://github.com/hjdhjd/homebridge-unifi-protect).
Большое спасибо за предоставление этого кода. Его коды лицензии вы можете найти [здесь](https://github.com/hjdhjd/homebridge-unifi-protect/blob/master/LICENSE.md).

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ## **WORK IN PROGRESS**
-->
### 0.0.13 (2023-01-23)
* dependencies updates
* first implementation of realtime updates api
* lastMotion, lastRing, lcdMessage and smartDetectZone in realTimeEvents
* (Scrounger) Button to take manual snapshot added
* (Scrounger) real time events datapoints for every cam added
* (Scrounger) take snapshot and thumbnail for real time events added (base64 images)
* (Scrounger) thumbnail image for list of motion events added (base64 images)
* (Scrounger) small thumbnail image for list of motion events and real time events added (base64 images)
* (Scrounger) camera name for list of motion events added

### 0.0.12 (2021-03-14)
* added smart detections
* fixed some lastMotion stuff
* added UnifiOs Support for CloudKey

### 0.0.11 (2020-02-27)
* changed Admin interface a little
* added description for port
* fixed UDM Pro writeable states

### 0.0.10 (2020-02-26)
* travis ci for integration tests fixed
* actually use last x motion setting

### 0.0.9 (2020-02-21)
* lastMotion of camera only updating if neccessary
* first UDM integrations, changing settings NOT working yet

### 0.0.8 (2020-02-17)
* made motion Events optional (Last Motion is always stored)
* made interval and "last x seconds of motions" adjustable
* properly delete old motions

### 0.0.7 (2020-02-09)
* continuosly refresh motion events
* changed data structur
* added lastMotion Datapoint to each camera

### 0.0.6 (2020-02-08)
* make some settings changeable (name, osdSettings.*, recordingSettings.mode, ledSettings.isEnabled)

### 0.0.5 (2020-02-07)
* new logo
* added motion event data points

### 0.0.4 (2020-02-05)
* release-script test and some Readme changes

### 0.0.3 (03.02.2020)
* (Peter Baumert) first working rls on npm

### 0.0.1
* (Peter Baumert) initial release

## License
MIT License

Copyright (c) 2020-2022 Peter Baumert

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.