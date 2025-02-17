![Logo](admin/bsblan.png)
# ioBroker.bsblan

[![NPM version](http://img.shields.io/npm/v/iobroker.bsblan.svg)](https://www.npmjs.com/package/iobroker.bsblan)
[![Downloads](https://img.shields.io/npm/dm/iobroker.bsblan.svg)](https://www.npmjs.com/package/iobroker.bsblan)
[![Dependency Status](https://img.shields.io/david/hacki11/iobroker.bsblan.svg)](https://david-dm.org/hacki11/iobroker.bsblan)
[![Known Vulnerabilities](https://snyk.io/test/github/hacki11/ioBroker.bsblan/badge.svg)](https://snyk.io/test/github/hacki11/ioBroker.bsblan)

[![NPM](https://nodei.co/npm/iobroker.bsblan.png?downloads=true)](https://nodei.co/npm/iobroker.bsblan/)

**Tests:**: [![Travis-CI](http://img.shields.io/travis/hacki11/ioBroker.bsblan/master.svg)](https://travis-ci.org/hacki11/ioBroker.bsblan)

## bsb_lan adapter for ioBroker

This adapter connects the [BSB_LAN Interface](https://github.com/fredlcore/bsb_lan) to ioBroker.
The BSB_LAN Interface brings the BSB (Boiler System Bus) to LAN. This adapter connects it to ioBroker.

[BSB_LAN Interface User manual](https://github.com/1coderookie/BSB-LPB-LAN)

## Supported devices
- BSB/LPB compatible devices (e.g. Brötje, Elco, MHG, Fujitsu)
- see for details: [Supported Devices](https://github.com/1coderookie/BSB-LPB-LAN)

## Usage
- BSB_LAN Interface is up and running
- Install Adapter
- Configure 
    - IP
    - User and password (if basic auth activated)
    - Poll interval in seconds (10 is minimum)
    - IDs which should be polled or changed (comma- or newline separated, see Webinterface of BSB_LAN for available ids)

## Writing Values
- Activate all or specific IDs as Writable in 
  * en: [Readonly or read/write access](https://1coderookie.github.io/BSB-LPB-LAN_EN/chap05.html)
  * de: [Zugriff des Adapters auf den Regler](https://1coderookie.github.io/BSB-LPB-LAN/kap05.html)
  * for all: `bsb_lan_config.h: #define DEFAULT_FLAG 0`
  * compile & upload 
- Add IDs which should be written to Adapter instance config (see Usage)
- Numbers, Enums and hr:min types are now writable (of course only writable IDs can be written)

## Changelog

### 0.3.0
* Add support for BSB_LAN 2.x
* BREAKING: Names of 24h Average values changed (e.g. Außentemperatur_(8700) => 24h Durchschnittswert. Außentemperatur_(20050))


### 0.2.2
* Replace invalid characters: https://github.com/ioBroker/ioBroker.js-controller/issues/198

### 0.2.1
* Fix write issue with new bsb_lan2 firmware

### 0.2.0
* Add 24h averages (needs BSB_LAN FW 1.1)

### 0.1.2
* Support INF interface for setting external room temperatures

### 0.1.1
* Support unit micro
* Made robust against invalid or non existing IDs

### 0.1.0
* Support write access

### 0.0.3
* dynamically create states
* IDs without whitespaces
* add textarea for configuration

### 0.0.1
* (hacki11) initial release

## Credits
- Icon made by [Freepik](https://www.freepik.com/home) from www.flaticon.com