# WiFi-Controlled Hovercraft Browser

Fork of WiFi-controlled (from a browser) hovercraft on an ESP8266 (NodeMCU, Wemos D1 mini) or ESP32 modified and translated by VidenDjurs.dk, danish high school.

**Video:** [https://www.youtube.com/watch?v=TWfIe7EutRM](https://www.youtube.com/watch?v=TWfIe7EutRM)

## Communication

- **WiFiPoint / SoftAP**
- **SSID:** hover- + last 4 hexadecimal characters of the WiFi MAC address of the ESP8266 chip
- **WiFi password:** 12345678
- **App:** browser (Chrome, Firefox, Safari, ...)
- **URL:** [http://192.168.4.1](http://192.168.4.1) or [http://h.be](http://h.be)

## App User Interface

![Screenshot_browser_hovercraft.png](Screenshot_browser_hovercraft.png)

- **Top line:** connection status, and on ESP8266, voltage during connection
- **Top slider:** trim the servo
- **Second slider:** set maximum speed (left = half power, right = full power)
- **Joystick:** control servo (left-right) and motor (middle-up)

## Pin location Wemos D1 Lite (ESP8266)

To do this, you must uncomment the following line:

`// #define ENV_HOVERSERVO_ESP8266_LOLIND1MINILITE`

Function | Pin | GPIO
--- | --- | ---
LEDCONNECTION | GPIO2 |
SERVO | D5 | GPIO14
MOTOR | D8 | GPIO15

## Pin location NodeMCU

To do this, you must uncomment the following line:

`// #define ENV_HOVERSERVO_ESP8266_NODEMCU`

Function | Pin | GPIO
--- | --- | ---
LEDCONNECTION | D0 | GPIO16
SERVO | D5 | GPIO14
MOTOR | D8 | GPIO15

## Pin location ESP01

Depending on whether the LED pin is on GPIO1 or GPIO2, you must uncomment the following line:

`// #define ENV_HOVERSERVO_ESP8266_ESP01_LEDPIN1_V0`

Function | Pin | GPIO
--- | --- | ---
LEDCONNECTION | TX | GPIO1
SERVO |  | GPIO0
MOTOR | RX | GPIO3

or

`// #define ENV_HOVERSERVO_ESP8266_ESP01_LEDPIN2_V0`

Function | Pin | GPIO
--- | --- | ---
LEDCONNECTION |  | GPIO2
SERVO |  | GPIO0
MOTOR | RX | GPIO3

## Arduino ESP8266 board settings

- We continue to use the ESP8266 Arduino core 2.7.4, but there is now also a fix to make it run smoothly on 3.1.2
- You can also adjust the lwIP settings in the board settings: the default "v2 Lower Memory" is good, but "v2 Higher Bandwidth" is better
- Choose "All Flash Contents" for "Erase Flash"; otherwise, WiFi settings from a previous session (or other configurations) may persist.

## Arduino libraries

The following libraries are required:

**ESP8266:**

- ArduinoWebsockets by Gil Maimon, easy to install from the Arduino Library manager: [https://github.com/gilmaimon/ArduinoWebsockets](https://github.com/gilmaimon/ArduinoWebsockets)
- [https://github.com/me-no-dev/ESPAsyncTCP](https://github.com/me-no-dev/ESPAsyncTCP)
- [https://github.com/me-no-dev/ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer)

**ESP32:**

- AsyncTCP: install from [https://github.com/me-no-dev/AsyncTCP](https://github.com/me-no-dev/AsyncTCP)
- ESP32Servo from the Arduino library manager, this version: [https://github.com/madhephaestus/ESP32Servo](https://github.com/madhephaestus/ESP32Servo)
- ArduinoWebsockets by Gil Maimon, easy to install from the Arduino Library manager: [https://github.com/gilmaimon/ArduinoWebsockets](https://github.com/gilmaimon/ArduinoWebsockets)
- [https://github.com/me-no-dev/ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer)

## Inspiration

The following sources of inspiration were used in developing this software:

- ESP32-CAM_TANK by PepeTheFroggie
- RobotZero One: ESP32-CAM-rc-car with software on [https://github.com/robotzero1/esp32cam-rc-car](https://github.com/robotzero1/esp32cam-rc-car)
- Cellphone controlled RC car
- Joystick based on Kirupa: Create a Draggable Element in JavaScript

## Micropython

Prefer to use Micropython instead of Arduino? There is also a Micropython version for ESP32: [https://github.com/FedericoBusero/HoverMicropyton](https://github.com/FedericoBusero/HoverMicropyton)

## How to make a Hovercraft?

The build instructions for the hovercraft can be found at [https://drive.google.com/file/d/1SUZypw2QWQQqCWgGDMl3Ls_pUvmDDozy/view?usp=sharing](https://drive.google.com/file/d/1SUZypw2QWQQqCWgGDMl3Ls_pUvmDDozy/view?usp=sharing) For hovercraft building workshops, you can contact MasynMachien: [https://www.instructables.com/masynmachiens-workshops/](https://www.instructables.com/masynmachiens-workshops/)
```
