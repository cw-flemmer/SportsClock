# Sports Digital Clock

A Wi-Fi-enabled desk clock for sports fans, built for the South African market. It runs on an **ESP32-C3 Super Mini** with a **128x64 SSD1306 OLED** display. Configure it once from your phone via the built-in setup portal, and thereafter it simply shows a personalized greeting followed by the current time whenever it is powered on.

## Features

- ESP32 powered
- 128x64 OLED display
- Personalized greeting on boot ("GOOD MORNING <device name>")
- Large HH:MM clock with seconds and date/day-of-week
- Wi-Fi time synchronization (NTP, Africa/Johannesburg)
- Web-based configuration (WiFiManager setup portal)
- Over-the-air firmware updates from GitHub Releases
- Config button to reopen the setup portal without clearing settings

## Hardware

- ESP32-C3 Super Mini
- SSD1306 128x64 OLED (I2C)
- Config button

## Wiring

### SSD1306 OLED (I2C)

| OLED Pin | ESP32-C3 |
|---|---:|
| SDA | GPIO 8 |
| SCL | GPIO 9 |
| VCC | 3V3 |
| GND | GND |

### Config Button

| Component | ESP32-C3 |
|---|---:|
| Config Button (to GND) | GPIO 3 |

Hold the config button low while the device boots to force open the setup portal. Saved settings are kept.

## Getting Started

### Build it yourself

### 1. Clone this repository
```bash
git clone https://github.com/cw-flemmer/SportsClock.git
cd SportsClock
```

### 2. Open the project

Launch Visual Studio Code and open the SportsClock folder. Ensure you have the PlatformIO IDE extension installed.

### 3. Upload

Connect the ESP32-C3. Build and upload the firmware.

## First Boot

On first boot the clock has no Wi-Fi credentials, so it starts its own access point (e.g. `SportsClock-A1B2`). Connect your phone to it, open the captive portal, and enter your Wi-Fi SSID, password and a device name. The clock saves the settings and from then on connects automatically and shows your personalized clock whenever it is powered on.

## Controls

- **Config button** — hold it low at boot to open the setup portal (Wi-Fi, device name, timezone) without clearing saved settings.
- **Setup portal** — also hosts the firmware update page (check / install / manual `.bin` upload).

## Credits

Built with **PlatformIO** and the Arduino framework for the ESP32-C3, using the excellent open-source libraries:

- **tzapu/WiFiManager** — captive portal configuration
- **Adafruit GFX + SSD1306** — OLED display
- **ArduinoJson** — OTA manifest handling

