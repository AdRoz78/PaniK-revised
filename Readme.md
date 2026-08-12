# PaniK

## POC App for Spoofing of WEA Messages at the API UI level

<img align="right" src="paniK.gif" width="250" />

For use case see [Alertify](https://github.com/MaxwellDPS/Alertify) which uses a gotify server for real-time headless alerts

### API Support
API 23 Android 6 onward is supported

#### Alerts Types

| Type | Message Type                  | Type | Message Type                     |
|------|-------------------------------|------|----------------------------------|
| CMAS | Presidential alert            | ETWS | ETWS Tsunami alert               |
| CMAS | Extreme alert                 | ETWS | ETWS Earthquake alert            |
| CMAS | Severe alert                  | ETWS | ETWS Earthquake & Tsunami  alert |
| CMAS | Amber / Child Abduction alert | ETWS | ETWS Other Message               |
| CMAS | Public Safety alert           | ETWS | ETWS Test Message                |
| CMAS | Required Monthly Test         | 
| CMAS | Local/State Test              |
| CMAS | Broadcast Operator alert      |


### Examples

[See Example Messages](./Images.md)

![Images](./img/image.png)

## Features

* Spoof WEA via [CMAS](https://en.wikipedia.org/wiki/Wireless_Emergency_Alerts) & [ETWS](https://www.technologyreview.com/2011/03/11/260021/how-japans-earthquake-and-tsunami-warning-systems-work/)
* Mute alert sound
* Delay alerts by a set amount
* No internet required


## Installation

Download the APK or build via Android studio.

After installation, you will have to allow "Display over other apps". The specific steps differ based on the ROM, though usually this can be done in the app info page for PaniK under settings. You should also disable Battery optimization, though some manufacturers *cough Xiaomi cough* make it much harder.

## Building

Execute the following command to build the APK.
```bash
$ ./gradlew build
```

## Update client

* Run `./gradlew generateSwaggerCode`
* Discard changes to `client/build.gradle` (newer versions of dependencies)
* Fix compile error in `client/src/main/java/com/github/gotify/client/auth/OAuthOkHttpClient.java` (caused by an updated dependency)
* Delete `client/settings.gradle` (client is a gradle sub project and must not have a settings.gradle)
* Commit changes



