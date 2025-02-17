---
chapters: {"pages":{"de/adapterref/iobroker.shelly/README.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/README.md"},"de/adapterref/iobroker.shelly/protocol-coap.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/protocol-coap.md"},"de/adapterref/iobroker.shelly/protocol-mqtt.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/protocol-mqtt.md"},"de/adapterref/iobroker.shelly/restricted-login.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/restricted-login.md"},"de/adapterref/iobroker.shelly/state-changes.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/state-changes.md"},"de/adapterref/iobroker.shelly/faq.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/faq.md"},"de/adapterref/iobroker.shelly/debug.md":{"title":{"de":"ioBroker.shelly"},"content":"de/adapterref/iobroker.shelly/debug.md"}}}
translatedFrom: de
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.shelly/protocol-mqtt.md
title: ioBroker.шелли
hash: zx/CkTtJq07j9yFUExLGe86qHeZY5gyHvxkhoPMC9nU=
---
![логотип](../../../de/admin/shelly.png)

# IoBroker.шелли
##MQTT
![iobroker_general_mqtt](../../../de/adapterref/iobroker.shelly/img/iobroker_general_mqtt.png)

### Важные инструкции
- Невозможно подключить адаптер Shelly к уже существующему брокеру MQTT.
- Адаптер Shelly запускает своего собственного брокера MQTT, который запускается на порту 1882, чтобы избежать конфликта с другими брокерами MQTT в той же системе (порт по умолчанию для MQTT — 1883).
- Невозможно подключить клиент MQTT (например, MQTT Explorer) к внутреннему брокеру MQTT.
- Стандартный порт внутреннего MQTT-брокера можно настроить в конфигурации адаптера
- **Знание протокола MQTT не требуется** - вся коммуникация осуществляется внутри компании

Вопросы? Сначала взгляните на [Часто задаваемые вопросы](faq.md)!

### Конфигурация
1. Откройте конфигурацию адаптера Shelly в ioBroker.
2. Выберите ```MQTT (и HTTP)``` как *Протокол* в *Общих настройках*.
3. Откройте вкладку **Настройки MQTT**.
4. Выберите имя пользователя и безопасный пароль (вы должны хранить эту информацию на всех устройствах Shelly).

> Адаптер Shelly запускает собственный брокер MQTT (внутренний). Настроенные имя пользователя и пароль должны храниться на всех устройствах Shelly, которые должны подключаться к этому посреднику.

![iobroker_mqtt](../../../de/adapterref/iobroker.shelly/img/iobroker_mqtt.png)

Активируйте MQTT на своих устройствах Shelly.

### Устройства поколения 2 (Plus и Pro)
1. Откройте веб-конфигурацию Shelly в браузере (не в приложении Shelly!)
2. Перейдите в ```Сети -> Mqtt```
3. Активируйте MQTT и введите только что настроенные данные пользователя и IP-адрес системы, на которой установлен ioBroker, а затем настроенный порт (например, ```192.168.1.2:1882```)
4. Сохраните конфигурацию — Shelly перезапустится автоматически.

- **Не изменяйте «идентификатор клиента» в этой конфигурации**
- **Для устройств 2-го поколения (Gen2) должны быть активированы все опции RPC (см. скриншоты)!**
- SSL/TLS не должны быть активированы

![Шелли Gen2](../../../de/adapterref/iobroker.shelly/img/shelly_mqtt-gen2.png)

![Шелли gen2 старый](../../../de/adapterref/iobroker.shelly/img/shelly_mqtt-gen2-old.png)

### Устройства первого поколения
1. Откройте веб-конфигурацию Shelly в браузере (не в приложении Shelly!)
2. Перейдите в «Настройки Интернета и безопасности» -> «Дополнительно» — «Настройки разработчика».
3. Активируйте MQTT и введите только что настроенные данные пользователя и IP-адрес системы, на которой установлен ioBroker, а затем настроенный порт (например, ```192.168.1.2:1882```)
4. Сохраните конфигурацию — Shelly перезапустится автоматически.

![Шелли gen1](../../../de/adapterref/iobroker.shelly/img/shelly_mqtt-gen1.png)

### Качество обслуживания (QoS)
TODO (см. en)