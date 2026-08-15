# Sports Digital Clock

> **Documentation:** [Device Setup](https://github.com/cw-flemmer/SportsClock/wiki/Device-Setup) · [OTA Updates](https://github.com/cw-flemmer/SportsClock/wiki/OTA-Updates) · [Troubleshooting](https://github.com/cw-flemmer/SportsClock/wiki/Troubleshooting)

A Wi-Fi-enabled digital clock for sports fans, built for the South African market. It runs on an **ESP32-C3 Super Mini** with a **128x64 SSD1306 OLED**, is configured once from a phone via its setup portal, and thereafter simply shows a personalized greeting followed by the current time whenever it is powered on.

## Status

Firmware v1.3.0 code is complete. Hardware integration & end-to-end verification (Phase 9) is still pending.

## Completed Features

- [x] First-boot setup portal (WiFiManager) to configure Wi-Fi SSID, password and device name; device advertises a temporary AP such as `SportsClock-A1B2`
- [x] Persistent configuration via ESP32 Preferences (device name, timezone; default `SPORTS CLOCK`, `Africa/Johannesburg`)
- [x] NTP time synchronization using the correct `Africa/Johannesburg` timezone (no manual UTC offset)
- [x] Non-blocking boot state machine: startup → connect → sync time → greeting → clock
- [x] Personalized ~5 second greeting ("GOOD MORNING <device name>")
- [x] Clock screen: device name, large HH:MM, seconds, and date/day-of-week in 24-hour format
- [x] Wi-Fi failure handling — falls back to the setup portal after a connect timeout
- [x] Runtime Wi-Fi reconnection — clock keeps running on local time, re-syncs NTP when Wi-Fi returns
- [x] Config button — hold low at boot to open the setup portal without clearing saved settings
- [x] Over-the-air updates — checks a GitHub Releases manifest on boot, with a `/update` page in the setup portal (check / install / manual `.bin` upload) and mDNS at `http://sportsclock.local`
- [x] Tagged, disable-able Serial logging (`[BOOT]`, `[WIFI]`, `[TIME]`, `[APP]`, `[OLED]`)

## Not Yet Done / Future

- [ ] Hardware verification of first boot, subsequent boot, and Wi-Fi interruption flows (Phase 9)
- [ ] Sports mode / match scoreboard, match timer, team selection, themes, weather, browser firmware installer (future expansion)