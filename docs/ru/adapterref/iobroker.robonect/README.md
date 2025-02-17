---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.robonect/README.md
title: ioBroker.robonect
hash: /RwCGnFEBJcLPzocUpMkNyEI8dPgxD4aX2NmAItkyNU=
---
![Логотип](../../../en/adapterref/iobroker.robonect/admin/robonect.png)

![НПМ](https://nodei.co/npm/iobroker.robonect.png?downloads=true)
![Количество установок](http://iobroker.live/badges/robonect-stable.svg)
![версия NPM](https://img.shields.io/npm/v/iobroker.robonect.svg)

# IoBroker.robonect
[![Тестирование и выпуск] (https://github.com/Grizzelbee/ioBroker.robonect/actions/workflows/test-and-release.yml/badge.svg)](https://github.com/Grizzelbee/ioBroker.robonect/actions/workflows/test-and-release.yml) [![CodeQL] (https://github.com/Grizzelbee/ioBroker.robonect/actions/workflows/codeql.yml/badge.svg)](https://github.com/Grizzelbee/ioBroker.robonect/actions/workflows/codeql.yml)

Это адаптер ioBroker для газонокосилки с поддержкой Robonect HX.

* Было протестировано с Robonect v1.1b (с ZeroConf v1.4) и Gardena R70Li.
* Кроме того, он был протестирован с Robonect v1.3b (с ZeroConf v1.9) и Gardena R40Li.

## Настройки
* Требуется ввести IP-адрес (например, 192.168.x.x) или имя хоста (например, robonect-D247BF) или полное доменное имя (например, robonect-D247BF.fritz.box) модуля Robonect. Если имя пользователя и пароль установлены, они также необходимы.
* ioBroker.robonect опрашивает данные через разные промежутки времени: по умолчанию информация о состоянии опрашивается каждые 60 секунд (1 минута), а другая информация опрашивается каждые 900 секунд (15 минут).
* Можно настроить два периода отдыха, чтобы предотвратить опрос, например. в полдень и ночью. Информация, которая может быть опрошена без пробуждения газонокосилки (и подачи звукового сигнала), все равно будет опрошена.
* Для каждого API-запроса можно выбрать интервал опроса (статус или информация) или вообще не опрашивать.
* служба push: при активации выберите IP-адрес и порт, которые адаптер должен прослушивать.

### Push-сервис:
Модуль robonect имеет параметр конфигурации под названием «Push Service» — он отправляет информацию о состоянии в зависимости от некоторых настраиваемых событий.
При активации адаптер будет получать push-уведомления, если произойдет одно из событий. Если эта опция активирована, вы можете использовать гораздо более длинные интервалы опроса, чем значения по умолчанию (например, 6-12 часов для статуса и 24 часа для информации).
Эти данные также должны быть настроены в модуле Robonect. Даже при прослушивании всех IP-адресов (0.0.0.0) вам необходимо настроить реальный IP-адрес в robonect. Используемый формат IP похож на 192.168.x.x:Port +. Вы можете выбрать GET или POST в Robonect — он работает и то, и другое.
+ Имя пользователя или пароль не требуются.

Поскольку передается только подмножество информации о состоянии (сигнал WLAN, состояние, остановлено, режим, продолжительность, часы, расстояние и батарея), извлечение по-прежнему необходимо, например. чтобы получить статус лезвия.

Конфигурация администратора: ![изображение](../../../en/adapterref/iobroker.robonect/admin/Push-Service-Adapter.png)

Конфигурация Робонекта: ![изображение](../../../en/adapterref/iobroker.robonect/admin/Push-Service-Robonect.png)

## Контроль
### Режим
Режим газонокосилки можно контролировать, изменяя robonect.0.status.mode. Возможные режимы: «Авто», «Дом», «Ручной», «Конец дня» и «Работа» (на данный момент реализованы не полностью).

### Расширения
Возможно управление расширениями GPIO 1, GPIO 2, OUT 1 и OUT 2 модуля Robonect. Требование состоит в том, чтобы режим расширения был настроен как «API» через веб-интерфейс Robonect. Если, например, светодиоды подключены к OUT1, их можно включать ночью и выключать утром, установив для Robonect.0.extension.out1.status значение «true» или «false».

## Changelog

### Work in progress
* to use timePickers in admin at least admin version 6.4.3 is required - will implement as soon as admin >= 6.4.3 is in stable repo.

### 1.0.3 (2023-08-21)
* (grizzelbee) Upd: Improved error handling
* (grizzelbee) Fix: some bug fixes
* (grizzelbee) Upd: Renamed jsonConfig.json5 to jsonConfig.json to get better compatibility

### 1.0.2 (2023-08-18)
* (grizzelbee) Fix: Updated package.json to deliver jasonConfig.json5

### 1.0.1 (2023-08-18)
* (grizzelbee) Upd: Documentation got updated
 
### 1.0.0 (2023-08-17) 
* (grizzelbee) Upd: Dependencies got updated
* (grizzelbee) Upd: Some fixes to make adapter-checker happy
* (grizzelbee) Upd: Updated git workflows
* (grizzelbee) New: Dropped request.js since it's deprecated
* (grizzelbee) New: Replaced request.js by axios.js for http requests
* (grizzelbee) New: Add Webserver for Push-Service API
* (grizzelbee) New: Add adapter-dev support
* (grizzelbee) New: Added snyk plugin
* (grizzelbee) New: Swapped Admin UI to V5

### 0.1.4
* (braindead1) changed polling log level from info to debug
* (braindead1) implemented polling of garage door status

### 0.1.3
* (braindead1) implemented JsonLogic & refactoring

### 0.1.2
* (braindead1) fixed GPS

### 0.1.1
* (braindead1) fixed typo

### 0.1.0
* (braindead1) implemented rest times

### 0.0.12
* (braindead1) improved polling

### 0.0.11
* (braindead1) implemented weather and GPS polls

### 0.0.10
* (braindead1) first stable version

### 0.0.9
* (braindead1) adapter improvements

### 0.0.8
* (braindead1) fixed some issues caused by different configurations

### 0.0.7
* (braindead1) prepared adapter for latest repository

### 0.0.6
* (braindead1) fixed minor issues

### 0.0.5
* (braindead1) updated to work with Robonect HX version 1.1b

### 0.0.4
* (braindead1) updated to work with Robonect HX version 1.0 Beta5

### 0.0.3
* (braindead1) support of Admin3

### 0.0.2
* (braindead1) updated to work with Robonect HX version 1.0 Beta2

### 0.0.1
* (StefSign) initial commit

## License
The MIT License (MIT)

Copyright (c) 2023 braindead1, grizzelbee

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