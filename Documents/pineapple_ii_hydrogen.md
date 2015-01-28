# Pineapple II Hydrogen/0.2.0 Tech Doc

## Exterior

### Panel

| SW/LED | Function |
| - | - |
| Reset SW | Reset |
| Min SW | Min-set |
| Max SW | Max-set |
| Main LED | Power Indicator, Note 1 is received |
| LED 1 | Min-value is set (Blue), Note 2 is received (Green) |
| LED 2 | TX signal (White), Note 3 is received (Green) |
| LED 3 | Max-value is set (Yellow), Note 4 is received (Green) |

### External Ports

| Port | Pin | Signal |
| - | - | - |
| **Power** | P1 | +7-12V |
| | P2 | GND |
| **MIDI OUT** | M0 | NC (SW) |
| | M1 | MIDI OUT SINK (DIN #5)|
| | M2 | MIDI OUT SOURCE (DIN #4) |
| | M3 | GND (DIN #2)|
| **MIDI IN** | m0 | mdetect |
| | m1 | MIDI IN KATHODE (DIN #5) |
| | m2 | MIDI IN ANODE (DIN #4) |
| | m3 | NC |
| **XMIDI** | X1 | xdetect |
| | X2 | GND |
| | X3 | RX+ |
| | X4 | RX- |
| | X5 | TX+ |
| | X6 | TX- |
| **GeekPort II** | G1 | +5V |
| | G2 | GND |
| | G3 | gdetect |
| | G4 | Sensor 1 |
| | G5 | Sensor 2 |
| | G6 | Sensor 3 |
| | G7 | Sensor 4 |
| | G8 | Reserved (Sensor 5 or I2C) |
| | G9 | Reserved (Sensor 6 or I2C) |
| | G10 | Light 1 |
| | G11 | Light 2 |
| | G12 | Light 3 |

## What's inside

### Internal Ports

| Port | Pin | Signal | Connection |
| - | - |
| **Front Port** | F1 | +5V | VR |
| | F2, F3, F4 | GND | Reset SW, VR, Main LED, Indicator LED |
| | F5 | Reset | Reset SW |
| | F6 | Arduino-D2 | Min SW |
| | F7 | Arduino-D3 | Max SW |
| | F8 | Arduino-A6 | VR |
| **Light Port** | L1 | TLC5940-OUT0 | B13/G10 |
| | L2 | TLC5940-OUT1 | B14/G11 |
| | L3 | TLC5940-OUT2 | B15/G12 |
| | L4 | TLC5940-OUT3 | Main LED |
| | L5 | TLC5940-OUT4 | LED1R |
| | L6 | TLC5940-OUT5 | LED1G |
| | L7 | TLC5940-OUT6 | LED1B |
| | L8 | TLC5940-OUT7 | LED2R |
| | L9 | TLC5940-OUT8 | LED2G |
| | L10 | TLC5940-OUT9 | LED2B |
| | L11 | TLC5940-OUT10 | LED3R |
| | L12 | TLC5940-OUT11 | LED3G |
| | L13 | TLC5940-OUT12 | LED3B|
| | L14 | TLC5940-OUT13 | |
| | L15 | TLC5940-OUT14 | |
| | L16 | TLC5940-OUT15 | |
| **Back Port** | B1 | +5V | Arduino Regulated Power |
| | B2 | GND | GND |
| | B3 | +7-12V | Arduino Power |
| | B4 | Arduino-D6 | TLC5940-Mode, D8 |
| | B5 | Arduino-D8 | Xbar |
| | B6 | Arduino-D9 | G3 (gdetect) |
| | B7 | Arduino-A0 | G4 |
| | B8 | Arduino-A1 | G5 |
| | B9 | Arduino-A2 | G6 |
| | B10 | Arduino-A3 | G7 |
| | B11 | Arduino-A4 | G8 |
| | B12 | Arduino-A5 | G9 |
| | B13 | TLC5940-OUT0 | L1, G10 |
| | B14 | TLC5940-OUT1 | L2, G11 |
| | B15 | TLC5940-OUT2 | L3, G12 |
| | B16 | Arduino-D10 | X1 (xdetect) |
| | B17 | RX+ | X3 |
| | B18 | RX- | X4 |
| | B19 | TX+ | X5 |
| | B20 | TX- | X6 |
| | B21 | Arduino-D12 | |
| | B22 | Arduino-A7 | mdetect/m0 |
| | B23 | +5V/R220 | M2 (MIDI OUT SOURCE) |
| | B24 | TX-OC | M1 (MIDI OUT SINK) |
| | B25 | RX-OK-A | m2 (MIDI IN ANNODE) |
| | B26 | RX-OK-K | m1 (MIDI IN KATHODE) |
| **Drive Port** | D1 | +5V | |
| | D2 | GND | |
| | D3 | TLC5940-SOUT | Ext TLC5940-SIN|
| | D4 | Arduino-D13/TLC5940-SCLCK | Ext TLC5940-SCLCK |
| | D5 | Arduino-D4/TLC5940-BLANK | Ext TLC5940-BLANK |
| | D6 | Arduino-D7/TLC5940-XLAT | Ext TLC5940-XLAT|
| | D7 | Arduino-D5/TLC5940-GSCLCK | Ext TLC5940-GSCLCK|
| | D8 | Arduino-D6/TLC5940-MODE | Ext TLC5940-MODE, B4 |
| | D9 | +7-12V | |
| | D10 | GND | |

### Arduino Pin Assignment

| Arduino Pro Mini | Signal |
| - | - |
| Arduino-Vin | +7-12V |
| Arduino-GND | GND |
| Arduino-5V | +5V Regurated Power |
| Arduino-RST | RST |
| Arduino-D0 | RX |
| Arduino-D1 | TX |
| Arduino-D2 | Min SW |
| Arduino-D3 | Max SW |
| Arduino-D4 | TLC5940-BLANK |
| Arduino-D5 | TLC5940-GSCLCK |
| Arduino-D6 | TLC5940-MODE |
| Arduino-D7 | TLC5940-XLAT |
| Arduino-D8 | Xbar |
| Arduino-D9 | gdetect |
| Arduino-D10 | xdetect |
| Arduino-D11 | TLC5940-SIN |
| Arduino-D12 | |
| Arduino-D13 | TLC5940-SCLCK |
| Arduino-A0 | Sensor 1 |
| Arduino-A1 | Sensor 2 |
| Arduino-A2 | Sensor 3 |
| Arduino-A3 | Sensor 4 |
| Arduino-A4 | Sensor 5 |
| Arduino-A5 | Sensor 6 |
| Arduino-A6 | VR |
| Arduino-A7 | mdetect |

### Parts

* Logic board
* Arduino Pro Mini 5V
* 74LS07
* 74LS157
* LTC1485 x2
* TLC5940
* TLP552 or TLP2962
* 1S1588
* C 0.1u
* C 0.01u x6
* R 120 x2
* R 220 x3
* R 4.7k
* Con PH 8p side
* Con PH 16p side
* Con Harting 10p
* Con Harting 26p side
* SW NKK G-13AP
* Pinheader 2p x2
* Pinheader 6p x1
* Pinheader 12p x2
* Case Takachi MX-2-13
* SW/LED NKK
* SW 
* VR B 10k
* Grip
* LED Kathode-common full-color x3
* Small board
* Con HR10A
* Con HR10A
* Con stereo mini pin jack w/ switch x2
* Con DC jack
* Con Harting 26p plug
* Con PH 8p plug
* Con PH 16p plug



