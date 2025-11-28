![Flipper usage](https://user-images.githubusercontent.com/10090793/211182642-e41919c5-3091-4125-815a-2d6a77a859f6.png)

# Unitemp - Universal temperature sensor reader

[![GitHub release](https://img.shields.io/github/release/quen0n/unitemp-flipperzero?include_prereleases=&sort=semver&color=blue)](https://github.com/quen0n/unitemp-flipperzero/releases/)
[![GitHub](https://img.shields.io/github/license/quen0n/unitemp-flipperzero)](https://github.com/quen0n/unitemp-flipperzero/blob/dev/LICENSE.md)
[![Build dev](https://github.com/quen0n/unitemp-flipperzero/actions/workflows/build_dev.yml/badge.svg?branch=dev)](https://github.com/quen0n/unitemp-flipperzero/actions/workflows/build_dev.yml)  
[Flipper Zero](https://flipperzero.one/) application for reading temperature, humidity and pressure sensors like a DHT11/22, DS18B20, BMP280, HTU21 and more. 

## List of supported sensors


| Model            | Power range | Interface        | Temp Range  | Temp Acc | Temp Res | Hum Range  | Hum Acc | Hum Res | Extra Range     | Acc | Res |
|------------------|-------------|------------------|-------------|----------|----------|------------|---------|---------|------------------|-----------|-----------|
| DHT11 (AOSONG)   | 3.3...5.5 V | DHT      | 0...50 °C   | ±2 °C    | 1 °C     | 20...90 %  | ±5 %    | 1 %     |                  |           |           |
| DHT11 (ASAIR)    | 3.3...5.5 V | DHT      | -20...60 °C | ±2 °C    | 0.1 °C   | 5...95 %   | ±5 %    | 1 %     |                  |           |           |
| DHT12            | 2.7...5.5 V | DHT      | -20...60 °C | ±0.5 °C  | 0.1 °C   | 20...90 %  | ±5 %    | 0.1 %   |                  |           |           |
| DHT21/AM2301     | 3.3...5 V   | DHT      | -40...80 °C | ±1 °C    | 0.1 °C   | 0...100 %  | ±3 %    | 0.1 %   |                  |           |           |
| DHT22/AM2302     | 3.3...5.5 V | DHT      | -40...80 °C | ±0.5°C   | 0.1 °C   | 0...100 %  | ±2 %    | 0.1 %   |                  |           |           |
| DHT20/AM2108     | 2.2...5.5 V | I2C              | -40...80 °C | ±0.5 °C  | 0.1 °C   | 0...100 %  | ±3 %    | 0.1 %   |                  |           |           |
| AM2320           | 3.1...5.5 V | Single wire, I2C | -40...80 °C | ±0.5 °C  | 0.1 °C   | 0...100 %  | ±3 %    | 0.1 %   |                  |           |           |
| AHT10            | 1.8…3.6 V   | I2C              | -40...85 °C | ±0.3 °C  | 0.01 °C  | 0...100 %  | ±2 %    | 0.024 % |                  |           |           |
| AHT20            | 2…5.5 V     | I2C              | -40...85 °C | ±0.3 °C  | 0.01 °C  | 0...100 %  | ±2 %    | 0.024 % |                  |           |           |
| SHT30/GXHT30     | 2.2…5.5 V   | I2C              | -40…125 °C  | ±0.3 °C  | 0.06 °C  | 0...100 %  | ±2 %    | 0.01 %  |                  |           |           |
| SHT31/GXHT31     | 2.2…5.5 V   | I2C              | -40…125 °C  | ±0.2 °C  | 0.06 °C  | 0...100 %  | ±2 %    | 0.01 %  |                  |           |           |
| SHT35/GXHT35     | 2.2…5.5 V   | I2C              | -40…125 °C  | ±0.1 °C  | 0.06 °C  | 0...100 %  | ±1.5 %  | 0.01 %  |                  |           |           |
| LM75             | 2.8...5.5 V | I2C              | -55...125°C | ±2 °C    | 0.1 °C   |            |         |         |                  |           |           |
| BMP180           | 1.8...3.6 V | I2C              | -40...85 °C | ±0.5 °C  | 0.01 °C  |            |         |         | 300...1100 hPa   | ±1.0 hPa  | 0.01 hPa  |
| BMP280           | 1.7...3.6 V | I2C          | -40...85 °C | ±1 °C    | 0.01 °C  |            |         |         | 300...1100 hPa   | ±1.0 hPa  | 0.0016 hPa|
| BME280           | 1.7...3.6 V | I2C        | -40...85 °C | ±1 °C    | 0.01 °C  | 0...100 %  | ±3 %    | 0.008 % | 300...1100 hPa   | ±1.0 hPa  | 0.0016 hPa|
| BME680           | 1.7...3.6 V | I2C              | -40...85 °C | ±0.5 °C  | 0.01 °C  | 0...100 %  | ±3 %    | 0.008 % | 300...1100 hPa   | ±0.6 hPa  | 0.18 Pa   |
| HTU21D(F)        | 1.5...3.6 V | I2C              | -40...125 °C| ±0.3 °C  | ±0.1     | 0...100 %  | ±2 %    | 0.04 %  |                  |           |           |
| HDC1080          | 2.7...5.5 V | I2C              | -40...125 °C| ±0.2 °C  | ±0.1     | 0...100 %  | ±2 %    | 0.1 %   |                  |           |           |
| DS18B20          | 3...5.5 V   | [1WR](https://en.wikipedia.org/wiki/1-Wire)         | -55...125 °C| ±0.5 °C  | 0.5 °C   |            |         |         |                  |           |           |
| DS18S20 (DS1820) | 3...5.5 V   | [1WR](https://en.wikipedia.org/wiki/1-Wire)         | -55...125 °C| ±0.5 °C  | 0.25 °C  |            |         |         |                  |           |           |
| MAX31855         | 3.3...5.5 V | SPI              | -200...1800°C| ±2 °C   | 0.25 °C  |            |         |         |                  |           |           |
| MAX31725         | 3.3...3.6V  | I2C              | -40...150 °C| ±0.5 °C  | 0.004°C  |            |         |         |                  |           |           |
| MAX6675          | 3...5.5V    | SPI              | 0...1024°C  | ±9 °C    | 0.25 °C  |            |         |         |                  |           |           |
| SCD30           | 4.5...5.5 V | I2C               | 0...50 °C  | ±0.4 °C | 0.01 °C | 0...100 %    | ±3 %    | 0.04 % | 0...40000 ppm  CO2 | ±(30 ppm + 3 %) | 1 ppm |
| SCD40           | 2.4...5.5 V | I2C               | -10...60 °C| ±1.5 °C | 0.01 °C | 0...100 %    | ±9 %    | 0.04 % | 400...2000 ppm CO2 | ±(50 ppm + 5 %) | 1 ppm |
| SCD41           | 2.4...5.5 V | I2C               | -10...60 °C| ±0.8 °C | 0.01 °C | 0...100 %    | ±9 %    | 0.04 % | 400...5000 ppm CO2 | ±(40 ppm + 5 %) | 1 ppm |


## Installation

Download and install from application catalog https://lab.flipper.net/apps/unitemp or mobile application  
...or install the application manually:
1) Download [latest version](https://cloud.quenon.ru/index.php/s/h98rT9UnaOL4wxR/download?path=%2F&files=unitemp-latest.fap)
2) Copy `unitemp-latest.fap` to `SD card/apps/GPIO` with qFlipper or mobile application
3) Open application on your Flipper: `Applications->GPIO->Temp sensors reader`  
Note: If you get the message "API version mismatch" after updating the firmware, download and install Unitemp again

## Need help? Discussions?

Join the discussion, ask a question or just send a photo of the flipper with sensors to [Discord](https://discord.com/channels/740930220399525928/1056727938747351060). [Invite link](https://discord.com/invite/flipper)

## Gratitudes

Thanks to [@Svaarich](https://github.com/Svaarich) for the UI design and to the Unleashed firmware community for sensors testing and feedbacks.

## Some community photos

![image](https://user-images.githubusercontent.com/10090793/210120132-7ddbc937-0a6b-4472-bd1c-7fbc3ecdf2ad.png)
![image](https://user-images.githubusercontent.com/10090793/210120135-12fc5810-77ff-49db-b799-e9479e1f57a7.png)
![image](https://user-images.githubusercontent.com/10090793/210120143-a2bae3ce-4190-421f-8c4f-c7c744903bd6.png)
![image](https://user-images.githubusercontent.com/10090793/215224085-8099408e-b3de-4a0c-854e-fe4e4faa8ea3.png)
