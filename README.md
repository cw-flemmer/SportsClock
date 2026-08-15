# Sports Digital Clock

A Wi-Fi-enabled digital clock for sports fans, built for the South African market. It runs on an **ESP32-C3 Super Mini** with a **128x64 SSD1306 OLED**, is configured once from a phone via its setup portal, and thereafter simply shows a personalized greeting followed by the current time whenever it is powered on.

## Status

Firmware v1.3.0 code is complete.

## Completed Features

- [x] Clock works. Time is synced with NTP server using `Africa/Johannesburg` timezone (no manual UTC offset)
- [x] OTA Updates via HTTP. Checks for new firmware everytime the device is powered on.

## Planned / Future

- [ ] Leaderboard API integration. Example: Show where your team is currently ranked on the global stage. Still being planned out.
