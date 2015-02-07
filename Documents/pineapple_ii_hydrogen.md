# Pineapple II Hydrogen/0.2.0 Tech Doc

## Exterior

### Panel

| SW/LED   | Function                   |
| -------- | -------------------------- |
| Min SW   | Min-set                    |
| Max SW   | Max-set                    |
| Clear SW | Clear-Min/Max              |
| VR       | Threshold                  |
| Display  | Min/Max/Th/Level indicator |


### External Ports

| Port            | Pin  | Signal                   |
| --------------- | ---- | ------------------------ |
| **Power**       | P1   | Vin (+7-12V)             |
|                 | P2   | GND                      |
| **MIDI OUT**    | M1   | MIDI OUT SINK (DIN #5)   |
|                 | M2   | MIDI OUT SOURCE (DIN #4) |
|                 | M2SW | mdetect                  |
|                 | M3   | GND (DIN #2)             |
| **MIDI IN**     | m1   | MIDI IN KATHODE (DIN #5) |
|                 | m2   | MIDI IN ANODE (DIN #4)   |
|                 | m3   | GND                      |
| **XMIDI**       | X1   | xdetect                  |
|                 | X2   | GND                      |
|                 | X3   | RX+                      |
|                 | X4   | RX-                      |
|                 | X5   | TX+                      |
|                 | X6   | TX-                      |
| **GeekPort II** | G1   | Vcc (+5V)                |
|                 | G2   | GND                      |
|                 | G3   | gdetect                  |
|                 | G4   | gselect                  |
|                 | G5   | Sensor 1                 |
|                 | G6   | Sensor 2                 |
|                 | G7   | Sensor 3                 |
|                 | G8   | I2C SDA                  |
|                 | G9   | I2C SCL                  |
|                 | G10  | Light 1                  |
|                 | G11  | Light 2                  |
|                 | G12  | Light 3                  |

## What's inside

### Internal Buses

| Bus              | Signal                                     | Connection             |
| ---------------- | ------------------------------------------ | ---------------------- |
| LIGHTPORT[1..16] | DIG[0..7], SEG[0..7]                       | Light Port             |
| MIDI[0..5]       | RXA, RXK, TXSRC, TXSNK, RX+, RX-, TX+, TX- | MIDI, XMIDI            |
| A[0..2]          | A[0..2]                                    | GeekPort II            |
| I2C[0..1]        | A4/SDA, A5/SCL                             | GeekPort II            |
| L[0..2]          | D5~, D6~, D9~                              | GeekPort II            |
| S[0..5]          | D11/MOSI, D13/SCLCK, D7, D2#, D3~#, D4     | LED Driver, Front Port |
| DETECT[0..3]     | vdetect, gdetect, mdetect, xdetect         |                        |



### Internal Ports


| Port           | Pin      | Signal                | Connection                             |
| -------------- | -------- | --------------------- | ---------------------------------------| 
| **Front Port** | F1       | Vcc                   | VR-Top                                 |
|                | F2       | GND                   | Reset SW, Min/Max SW Common, VR-Bottom |
|                | F3       | D2#                   | SW Max                                 |
|                | F4       | D3~#                  | SW Min                                 |
|                | F5       | D4                    | SW Clear                               |
|                | F6       | D11~/MOSI             | Reserved for LED Driver                |
|                | F7       | D13/SCLCK             | Reserved for LED Driver                |
|                | F8       | vdetect               | VR-Center                              |
| **Light Port** | L[1..16] | DIG[0..7], SEG[DP..G] | LED                                    |
| **Back Port**  | B1       | Vcc                   | G1                                     |
|                | B2       | GND                   | G2                                     |
|                | B3       | A0                    | G5                                     |
|                | B4       | GND                   | M3 (DIN #3)                            |
|                | B5       | A1                    | G6                                     |
|                | B6       | GND                   | X1                                     |
|                | B7       | A2                    | G7                                     |
|                | B8       | GND                   | P2                                     |
|                | B9       | A4/SDA                | G8                                     |
|                | B10      | Vin                   | P1                                     |
|                | B11      | A5/SCL                | G9                                     |
|                | B12      | gdetect               | G3                                     |
|                | B13      | gselect               | G4                                     |
|                | B14      | D5~/L0                | G10                                    |
|                | B15      | D6~/L1                | G11                                    |
|                | B16      | D9~/L2                | G12                                    |
|                | B17      | mdetect               | M2SW                                   |
|                | B18      | xdetect               | X1                                     |
|                | B19      | RXA                   | m2 (DIN #4)                            |
|                | B20      | RXK                   | m1 (DIN #5)                            |
|                | B21      | TXSRC                 | M2 (DIN #4)                            |
|                | B22      | TXSNK                 | M1 (DIN #5)                            |
|                | B23      | RX+                   | X3                                     |
|                | B24      | RX-                   | X4                                     |
|                | B25      | TX+                   | X5                                     |
|                | B26      | TX-                   | X6                                     |


### Arduino Pin Assignment

| Arduino Pro Mini | Signal                        |
| ---------------- | ----------------------------- |
| Vin              | +7-12V                        |
| GND              | GND                           |
| 5V               | +5V Regulated Power Out (Vcc) |
| RST              |                               |
| D0/RX            | RX                            |
| D1/TX            | TX                            |
| D2#              | SW Main (S3)                  |
| D3~#             | SW Max  (S4)                  |
| D4               | SW Min  (S5)                  |
| D5~              | L0                            |
| D6~              | L1                            |
| D7               | LOAD (S2)                     |
| D8               | XBAR                          |
| D9~              | L2                            |
| D10~             | gselect                       |
| D11~/MOSI        | DIN  (S0)                     |
| D12/MISO         |                               |
| D13/SCLCK        | DCLCK (S1)                    |
| A0               | A0                            |
| A1               | A1                            |
| A2               | A2                            |
| A3               | _detect                       |
| A4/SDA           | SDA (I2C0)                    |
| A5/SCL           | SCL (I2C1)                    |
| A6               | SELECT0                       |
| A7               | SELECT1                       |

### Parts

Obsolete

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



