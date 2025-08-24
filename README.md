| Supported Targets | ESP32-S3 |
| ----------------- | -------- |

| Supported LCD Controller    | ST7701 |
| ----------------------------| -------|

| Supported Touch Controller  |  GT911 |
| ----------------------------| -------|

# ESP32-S3 RGB LCD + LVGL Template

A complete, production-ready template for ESP32-S3 projects with RGB LCD displays and LVGL GUI framework. This template demonstrates how to avoid tearing when using LVGL with RGB interface screens and provides multiple demo options.

## Features

- ✅ **High-Performance RGB LCD**: 16-bit parallel interface for smooth graphics
- ✅ **Touch Support**: GT911 capacitive touch controller with I2C communication  
- ✅ **LVGL Integration**: Thread-safe implementation with hardware acceleration
- ✅ **Multiple Demos**: Widgets, stress tests, benchmarks, and custom UIs
- ✅ **ESP-IDF 6.0 Compatible**: Modern API usage and optimizations
- ✅ **PSRAM Optimized**: Efficient memory usage for complex graphics
- ✅ **Anti-Tearing**: Advanced synchronization for flicker-free display

## Hardware Support

### **Target Board**
* **MCU**: ESP32-S3R8 (with 8MB PSRAM)
* **Board**: Waveshare ESP32-S3 RGB LCD 4.3"
* **Display**: 4.3" RGB LCD (480x272 resolution)
* **Touch**: GT911 capacitive touch controller
* **Interface**: 16-bit parallel RGB + I2C touch

### **Hardware Connection**

The connection between ESP32-S3 Board and the RGB LCD Panel:

```
       ESP32-S3 Board                      RGB LCD Panel
+-----------------------+              +-------------------+
|                   GND +--------------+GND                |
|                       |              |                   |
|                   3V3 +--------------+VCC                |
|                       |              |                   |
|             GPIO_21   +--------------+PCLK               |
|                       |              |                   |
|     GPIO_4-GPIO_19    +--------------+DATA[15:0]         |
|                       |              |                   |
|             GPIO_46   +--------------+HSYNC              |
|                       |              |                   |
|             GPIO_3    +--------------+VSYNC              |
|                       |              |                   |
|             GPIO_47   +--------------+DE                 |
|                       |              |                   |
|             GPIO_2    +--------------+BLK                |
+-----------------------+              |                   |
                               3V3-----+DISP_EN            |
                                       |                   |
                                       +-------------------+

      Touch Controller (GT911) - I2C Connection:
+-----------------------+              +-------------------+
|             GPIO_8    +--------------+SDA                |
|             GPIO_9    +--------------+SCL                |
|             GPIO_4    +--------------+INT                |
|                   GND +--------------+GND                |
|                   3V3 +--------------+VCC                |
+-----------------------+              +-------------------+
```

## Quick Start

### **Option 1: Use the Setup Script (Recommended)**

````bash
# Clone or copy this template
git clone <your-template-repo> ESP32-S3-RGB-LCD-Template
cd ESP32-S3-RGB-LCD-Template

# Create a new project
./create_project.sh MyAwesomeProject

# Navigate to your new project
cd ../MyAwesomeProject

# Build and flash
esp32s3-dev build
esp32s3-dev flash
esp32s3-dev monitor
````
