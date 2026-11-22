# ESP32-S3 AI Box – Hardware Setup

## 1. Project Overview

This project uses the **ESP32-S3** microcontroller as the central control unit, integrated with several peripheral modules to build an AI Box system capable of servo motor control, audio playback, and visual display through a TFT screen.

The system consists of the following main components:

- **ESP32-S3:** Main microcontroller.
- **TFT Display 240x240:** Displays information and visual content.
- **2 Servo Motors:** Control horizontal and vertical movements.
- **MAX98357A:** I2S audio amplifier module.
- **Speaker:** Outputs audio.
- **6-pin Module:** Connects to the ESP32-S3 through GPIO pins.

## 2. Hardware Components

| No. | Component | Quantity |
|---|---|---:|
| 1 | ESP32-S3 Development Board | 1 |
| 2 | TFT Display 240x240 | 1 |
| 3 | Servo Motor | 2 |
| 4 | MAX98357A I2S Amplifier | 1 |
| 5 | Speaker | 1 |
| 6 | 6-pin Module | 1 |
| 7 | 5V Power Supply | 1 |

## 3. Hardware Connections

### 3.1. TFT Display 240x240

The TFT display uses the SPI communication interface to connect to the ESP32-S3.

| TFT Pin | ESP32-S3 Pin |
|---|---|
| GND | GND |
| VCC | 3.3V |
| SCL | GPIO 42 |
| SDA | GPIO 41 |
| RST | GPIO 40 |
| DC | GPIO TX (GPIO 43) |
| BLK | GPIO RX (GPIO 44) |

### 3.2. Servo Motors

The system uses two servo motors to control horizontal and vertical movements.

**Horizontal Servo:**

| Servo Wire | Connection |
|---|---|
| Signal (Orange) | GPIO 11 |
| VCC (Red) | 5V |
| GND (Brown) | GND |

**Vertical Servo:**

| Servo Wire | Connection |
|---|---|
| Signal (Orange) | GPIO 12 |
| VCC (Red) | 5V |
| GND (Brown) | GND |

### 3.3. MAX98357A Audio Amplifier

The MAX98357A module uses the I2S communication protocol to receive audio data from the ESP32-S3 and amplify the signal for speaker output.

| MAX98357A Pin | ESP32-S3 Connection |
|---|---|
| VIN | 5V |
| GND | GND |
| LRC | GPIO 7 |
| BCLK | GPIO 16 |
| DIN | GPIO 15 |
| SPK+ / SPK- | Speaker terminals |

### 3.4. 6-pin Module

Connect the module according to the hardware diagram.

| Module Pin | ESP32-S3 Connection |
|---|---|
| GND | GND |
| VCC | 3.3V |
| GPIO 1 | GPIO 4 |
| GPIO 2 | GPIO 5 |
| GPIO 3 | GPIO 6 |

*Note: The exact module name and pin functions should be verified against the actual hardware model.*

## 4. Power Supply

The system uses two main voltage levels:

- **3.3V:** Supplies power to the 6-pin module and TFT display.
- **5V:** Supplies power to the audio amplifier and two servo motors.

All modules must share a common GND connection to ensure stable signal communication.

**Important:** Use an external 5V power supply with sufficient current capacity for both servo motors and the audio amplifier. Avoid powering the servos directly from the ESP32 board's 5V pin if the power source cannot provide enough current.

## 5. Assembly Instructions

1. Connect the ESP32-S3 to the power supply.
2. Connect the TFT display according to the GPIO connection table.
3. Connect the MAX98357A module to the speaker and ESP32-S3.
4. Connect the two servo motors to GPIO 11 and GPIO 12.
5. Connect the 6-pin module according to the hardware diagram.
6. Check all 3.3V, 5V, and GND connections.
7. Upload the firmware to the ESP32-S3 and test each component.

## 6. Firmware and Server

- **Firmware:** https://ai-box-plus.com
- **Server:** https://ai-box.vn

## 7. Technical Notes

- Double-check the pin connections before powering on the system.
- Never apply 5V directly to the ESP32-S3 GPIO pins.
- Check the speaker polarity and servo power connections.
- Ensure that the external power supply and ESP32-S3 share a common GND.
- Verify the SPI configuration for the TFT display and the I2S configuration for the audio amplifier in the firmware.

## 8. References

The hardware connection diagram is used as the reference for assembling the system and configuring the ESP32-S3 GPIO pins.
