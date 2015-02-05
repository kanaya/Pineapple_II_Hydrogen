# Pineapple II Hydrogen/0.2.0 Tech Doc

## Exterior

### Panel

| SW/LED | Function |
| - | - |
| Reset SW | Reset |
| Min SW | Min-set |
| Max SW | Max-set |
| VR | Threshold |
| Display | Min/Max/Th/Level indicator |


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
| **XMIDI** | X1 | xdetect |
| | X2 | GND |
| | X3 | RX+ |
| | X4 | RX- |
| | X5 | TX+ |
| | X6 | TX- |
| **GeekPort II** | G1 | Vcc (+5V) |
| | G2 | GND |
| | G3 | gdetect |
| | G4 | gselect |
| | G5 | Sensor 1 |
| | G6 | Sensor 2 |
| | G7 | Sensor 3 |
| | G8 | I2C SDA |
| | G9 | I2C SCL |
| | G10 | Light 1 |
| | G11 | Light 2 |
| | G12 | Light 3 |

## What's inside

### Internal Ports

| Port | Pin | Signal | Connection |
| - | - |
| **Front Port** | F1 | Vcc | VR-Top |
| | F2, F3, F4 | GND | Reset SW, Min/Max SW Common, VR-Bottom |
| | F5 | Reset | Reset SW |
| | F6 | Arduino-D2 | Min SW |
| | F7 | Arduino-D3 | Max SW |
| | F8 | Arduino-A3 | VR-Center |
| **Light Port** | L1 | DIG0 | |
| | L2 | DIG1 | |
| | L3 | DIG2 | |
| | L4 | DIG3 | |
| | L5 | DIG4 | |
| | L6 | DIG5 | |
| | L7 | DIG6 | |
| | L8 | DIG7 | |
| | L9 | SEG0 | |
| | L10 | SEG1 | |
| | L11 | SEG2 | |
| | L12 | SEG3 | |
| | L13 | SEG4 | |
| | L14 | SEG5 | |
| | L15 | SEG6 | |
| | L16 | SEG7 | |
| **Back Port** | B1 | Vcc | G01 |
| | B2 | GND | |
| | B3 | Sensor 1 | G05 |
| | B4 | GND | |
| | B5 | Sensor 2 | G06 |
| | B6 | GND | |
| | B7 | Sensor 3 | G07 |
| | B8 | GND | |
| | B9 | I2C SDA | G08 |
| | B10 | Vin | |
| | B11 | I2C SDL | G09 |
| | B12 | mdetect | M2SW |
| | B13 | gdetect | G03 |
| | B14 | xdetect | X01 |
| | B15 | gselect | G04 |
| | B16 | RXA | m2 |
| | B17 | Light 1 | G10 |
| | B18 | RXK | m1 |
| | B19 | Light 2 | G11 |
| | B20 | TXV | M2 |
| | B21 | Light3 | G12 |
| | B22 | TX | M1 |
| | B23 | RX+ | X3 |
| | B24 | RX- | X4 |
| | B25 | TX+ | X5 |
| | B26 | TX- | X6 |
| **Drive Port** | D1 | Vcc | |
| | D2 | GND | |
| | D3 | MOSI | |
| | D4 | DOUT | |
| | D5 | SCLCK | |
| | D6 | LOAD | |
| | D7 | BLANK | |
| | D8 | XLAT | |
| | D9 | GSCLCK | |
| | D10 | I2C SDA | |
| | D11 | I2C SCL | |
| | D12 | Vin | |

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



