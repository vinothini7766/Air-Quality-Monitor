# IoT-Based Air Quality Monitoring System

## Overview

This project is an IoT-based Air Quality Monitoring System designed to measure and report air pollution levels in real-time. It uses gas sensors and microcontrollers to collect air quality data and sends it to a cloud platform for storage, visualization, and alerts.

---

## Features

- Real-time air quality monitoring
- Wi-Fi connectivity using ESP32/NodeMCU
- Data visualization on ThingSpeak or Blynk
- Alerts for critical pollution levels
- Local display via OLED/LCD
- Portable and cost-effective design

---

## Components Used

| Component         | Description                       |
|------------------|-----------------------------------|
| ESP32 / NodeMCU   | Microcontroller with Wi-Fi        |
| MQ-135           | Gas sensor (CO2, NH3, Benzene)     |
| DHT11            | Temperature and Humidity sensor    |
| PMS5003 (optional) | PM2.5 and PM10 particle sensor   |
| OLED Display (optional) | For real-time local display |
| ThingSpeak/Blynk | Cloud dashboard                    |
| Power Supply     | 5V USB or battery                   |

---

## How It Works

1. Sensors detect air pollutants and environmental conditions.
2. The microcontroller reads sensor values and sends the data to a cloud server over Wi-Fi.
3. The cloud platform logs and visualizes data.
4. Alerts can be triggered if pollution exceeds safe levels.

---

## Circuit Diagram

> Coming soon – or you can design using Fritzing.

---

## Installation and Setup

### Hardware Connections

- MQ135 → Analog pin of ESP32 (e.g., GPIO34)
- DHT11 → Digital pin (e.g., GPIO14)
- Connect power and ground lines accordingly.

### Software Setup

1. Install Arduino IDE
2. Add ESP32/NodeMCU board via Board Manager
3. Install required libraries:
   - `WiFi.h`
   - `ThingSpeak.h`
   - `DHT.h` (for DHT11)
4. Upload the code from `main.ino`
5. Enter your Wi-Fi credentials and ThingSpeak API key

---

## Sample Code Snippet

```cpp
int mq135Pin = 34;
int airQuality = analogRead(mq135Pin);
ThingSpeak.writeField(channelID, 1, airQuality, writeAPIKey);