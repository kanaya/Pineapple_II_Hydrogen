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
| **Power** | P1 | Vin (+7-12V) |
| | P2 | GND |
| **MIDI OUT** | M1 | MIDI OUT SINK (DIN #5)|
| | M2 | MIDI OUT SOURCE (DIN #4) |
| | M2SW | mdetect |
| | M3 | GND (DIN #2)|
| **MIDI IN** | m1 | MIDI IN KATHODE (DIN #5) |
| | m2 | MIDI IN ANODE (DIN #4), vdetect |
| | m3 | GND |
| **XMIDI** | X1 | Vin |
| | X2 | GND |
| | X3 | RX+ |
| | X4 | RX- |
| | X5 | TX+ |
| | X6 | TX- |
| **GeekPort II** | G1 | Vcc (+5V) |
| | G2 | GND |
| | G3 | gdetect |
| | G4 | GPIO |
| | G5 | Sensor 1 |
| | G6 | Sensor 2 |
| | G7 | Sensor 3 |
| | G8 | Reserved for I2C |
| | G9 | Reserved for I2C |
| | G10 | Light 1 |
| | G11 | Light 2 |
| | G12 | Light 3 |

## What's inside

### Internal Ports

| Port | Pin | Signal | Connection |
| - | - |
| **Front Port** | F1 | Vcc | VR-Top, LED Kathodes |
| | F2, F3, F4 | GND | Reset SW, Min/Max SW Common, VR-Bottom |
| | F5 | Reset | Reset SW |
| | F6 | Arduino-D2 | Min SW |
| | F7 | Arduino-D3 | Max SW |
| | F8 | Arduino-A3 | VR-Center |
| **Light Port** | L1 | TLC5940-OUT0 | |
| | L2 | TLC5940-OUT1 | |
| | L3 | TLC5940-OUT2 | |
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
| **Back Port** | B1 | Vcc | Arduino Regulated Power |
| | B2 | GND | |
| | B3 | Vin | Arduino Power |
| | B4 | GND | |
| | B5 | Vin | |
| | B6 | GND | |
| | B7 | Arduino-D9 | G3 |
| | B8 | GND | |
| | B9 | Arduino-D10 | G4 |
| | B10 | TLC5940-OUT0 | G10, L1 |
| | B11 | Arduino-A0 | G5 |
| | B12 | TLC5940-OUT1 | G11, L2 |
| | B13 | Arduino-A1 | G6 |
| | B14 | TLC5940-OUT2 | G12, L3 |
| | B15 | Arduino-A2 | G7 |
| | B16 | RX+ | X3 |
| | B17 | Arduino-A4 | G8 |
| | B18 | RX- | X4 |
| | B19 | Arduino-A5 | G9 |
| | B20 | TX+ | X5 |
| | B21 | Arduino-A6 | M2SW |
| | B22 | TX- | X6 |
| | B23 | Vcc/R220 | M2 |
| | B24 | MIDIRXA | m2 |
| | B25 | MIDITX | M1 |
| | B26 | MIDIRXK | m1 |
| **Drive Port** | D1 | Vcc | |
| | D2 | GND | |
| | D3 | TLC5940-SOUT | Ext TLC5940-SIN|
| | D4 | Arduino-D13/TLC5940-SCLCK | Ext TLC5940-SCLCK |
| | D5 | Arduino-D4/TLC5940-BLANK | Ext TLC5940-BLANK |
| | D6 | Arduino-D7/TLC5940-XLAT | Ext TLC5940-XLAT|
| | D7 | Arduino-D5/TLC5940-GSCLCK | Ext TLC5940-GSCLCK|
| | D8 | Arduino-D6/TLC5940-MODE | Ext TLC5940-MODE, B4 |
| | D9 | Vin | |
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
| Arduino-D10 | GPIO |
| Arduino-D11 | TLC5940-SIN |
| Arduino-D12 | |
| Arduino-D13 | TLC5940-SCLCK |
| Arduino-A0 | Sensor 1 |
| Arduino-A1 | Sensor 2 |
| Arduino-A2 | Sensor 3 |
| Arduino-A3 | VR |
| Arduino-A4 | I2C |
| Arduino-A5 | I2C |
| Arduino-A6 | mdetect |
| Arduino-A7 | vdetect |

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
* R 22k
* Con PH 8p side
* Con PH 16p side
* Con Harting 10p or Pinheader 2x5p
* Con Harting 26p side
* SW NKK G-13AP
* Pinheader 1x2p x2
* Pinheader 1x6p x1
* Pinheader 1x12p x2
* Case Takachi MX2-8-13
* SW/LED NKK HB-15CKS2-4MBMS
* SW Nidech Copal-8A
* VR B 10k Supertech VR
* Knob
* LED Kathode-common full-color OSTA5131A x3
* Small board
* Con HR10A-7R-6P
* Con HR10A-10R-12S
* Con stereo mini pin jack EST MJ-074N
* Con stereo mini pin jack w/ switch EST MJ-352W-C
* Con DC jack EST MJ-17
* Con Harting 26p plug
* Con PH 8p plug
* Con PH 16p plug
* Flat cable
* PH Housing 8p
* PH Housing 16p
* PH Harnes 8p
* PH Harnes 16p
* Con stereo mini pin plug x2
* Con DIN 5p jack connector
* Con HR10A 12p plug
* Cable 4p
* Flat cable 26p
* Sensor for testing



