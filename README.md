# ESP32 Magnetometer Web Server

This project demonstrates how to set up an ESP32 microcontroller to read magnetic field data using the HMC5883L magnetometer sensor and serve the data via a web server. The ESP32 creates an access point if no WiFi connection is available, reads magnetic field values, and displays them on a web page that refreshes every five seconds.

## Features
- Reads magnetic field data (X, Y, Z) using the HMC5883L sensor.
- Uses WiFiManager to manage WiFi connections.
- Serves data through an embedded web server on the ESP32.
- Displays real-time data on a web page with automatic refresh.

## Components Used
- ESP32
- HMC5883L Magnetometer
- WiFiManager Library
- Adafruit Sensor and HMC5883L Libraries

## Circuit Diagram
Connect the HMC5883L sensor to the ESP32 as follows:
- SCL -> GPIO 25
- SDA -> GPIO 27
- DRDY -> GPIO 33

## How to Use
1. **Hardware Setup**: Connect the HMC5883L sensor to the ESP32 using the defined pins (SDA, SCL).
2. **Library Installation**: Ensure the following libraries are installed in your Arduino IDE:
   - `WiFi`
   - `Wire`
   - `Adafruit Sensor`
   - `Adafruit HMC5883L`
   - `WiFiManager`
3. **Code Upload**: Upload the provided code to the ESP32.
4. **Connect to WiFi**: If no known WiFi network is available, the ESP32 will create an access point named `ESP32_AP`. Connect to this network using your device.
5. **Access the Web Server**: Open a web browser and navigate to the IP address displayed in the Serial Monitor to view the magnetic field data.

## Code Overview

### Libraries
The following libraries are included at the beginning of the code:
```cpp
#include <WiFi.h>
#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_HMC5883_U.h>
#include <WiFiManager.h>
