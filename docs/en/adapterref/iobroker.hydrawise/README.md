![Logo](admin/hydrawise.jpg)

# ioBroker.hydrawise

[![NPM version](https://img.shields.io/npm/v/iobroker.hydrawise.svg?style=flat-square)](https://www.npmjs.com/package/iobroker.hydrawise)
[![Downloads](https://img.shields.io/npm/dm/iobroker.hydrawise.svg?label=npm%20downloads&style=flat-square)](https://www.npmjs.com/package/iobroker.hydrawise)
![node-lts](https://img.shields.io/node/v-lts/iobroker.hydrawise?style=flat-square)
![Libraries.io dependency status for latest release](https://img.shields.io/librariesio/release/npm/iobroker.hydrawise?label=npm%20dependencies&style=flat-square)

![GitHub](https://img.shields.io/github/license/sentiq/iobroker.hydrawise?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/sentiq/iobroker.hydrawise?logo=github&style=flat-square)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/sentiq/iobroker.hydrawise?logo=github&style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/sentiq/iobroker.hydrawise?logo=github&style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/sentiq/iobroker.hydrawise?logo=github&style=flat-square)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/sentiq/iobroker.hydrawise/test-and-release.yml?branch=master&logo=github&style=flat-square)

## Versions

![Beta](https://img.shields.io/npm/v/iobroker.hydrawise.svg?color=red&label=beta)
![Stable](http://iobroker.live/badges/hydrawise-stable.svg)
![Installed](http://iobroker.live/badges/hydrawise-installed.svg)

Integrate your Hydrawise controller into iobroker.
You can see all controller information, schedules and sensors. It is also possible to suspend planned watering by x seconds.

## Documentation

-   log into https://app.hydrawise.com/config/account-details
-   generate API Key by clicking "Generate API Key" under "Account Settings"
-   paste key into adapter settings

> **Note**  
> After updating from 0.0.15 you have to re-enter your API key

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### 0.0.19 (2023-08-05)

-   (SentiQ) fixed button roles

### 0.0.18 (2023-08-05)

-   (SentiQ) fixed timeout

### 0.0.17 (2023-08-03)

-   (SentiQ) fixed adapter crash

### 0.0.16 (2023-08-02)

-   (SentiQ) added more information to README
-   (SentiQ) encrypted apiKey
-   (SentiQ) removed logging of apiKey
-   (SentiQ) added filtering of invalid characters in ids
-   (SentiQ) added check of ack flag
-   (SentiQ) fixed roles
-   (SentiQ) fixed error message
-   (SentiQ) removed usage of clearTimeout

### 0.0.15 (2023-06-29)

-   (SentiQ) updated dependencies

### 0.0.14 (2023-06-29)

-   (SentiQ) fixing version

### 0.0.12 (2023-06-29)

-   (SentiQ) changed value of `last_contact` to date string format

### 0.0.11 (2023-06-28)

-   (SentiQ) raised timeouts
-   (SentiQ) fixed types

### 0.0.10 (2023-06-27)

-   (SentiQ) fixed adapter crash
-   (SentiQ) changed value of `timestr` to date string format

### 0.0.9 (2023-05-25)

-   (SentiQ) added more translations

### 0.0.8 (2023-05-25)

-   (SentiQ) improved log messages

### 0.0.7 (2023-05-25)

-   (SentiQ) fixed author

### 0.0.6 (2023-05-24)

-   (SentiQ) lowered min node version to 14.5.0

### 0.0.5 (2023-05-24)

-   (SentiQ) updated packages

### 0.0.4 (2023-05-24)

-   (SentiQ) testing

### 0.0.3 (2023-05-24)

-   (SentiQ) added zone controls and Ukrainian language

### 0.0.2 (2023-05-23)

-   (SentiQ) refactoring code

### 0.0.1 (2023-01-26)

-   (aDabbelju) Initial commit by adapter creator

## License

MIT License

Copyright (c) 2023 SentiQ <fischer.yves@web.de>

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
