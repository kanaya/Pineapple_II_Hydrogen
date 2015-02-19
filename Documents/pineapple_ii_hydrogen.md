# Pineapple II Hydrogen/0.6.0 Tech Doc

## Interface

### Panel and Ports

| Port            | Pin      | Cable  | Signal                       | Internal Bus  | BackPort     | Arduino Pin |
| --------------- | -------- | ------ | ---------------------------- | ------------- | ------------ | ----------- |
| **Panel**       | Max SW   |        | Max-set (DrivePort 3)        | CTRL 2        |              | D2INT       |
|                 | Min SW   |        | Min-set (DrivePort 4)        | CTRL 3        |              | D3~INT      |
|                 | Clear SW |        | Clear-Min/Max (DrivePort 5)  | CTRL 4        |              | D4          |
|                 | VR1      |        | Threshold                    | ANLG 0        |              | A6          |
|                 | Display  |        | Min/Max/Th/Level indicator   | LDIG, LSEG    |              |             |
| **Power**       | P1       | Red    | Vcc (+5V)                    |               | B1           |             |
|                 | P2       | Black  | GND [Black]                  |               | B[2,4,..,10] |             |
| **MIDI OUT**    | M1       |        | TX+ OR MIDI OUT SRC (DIN #4) | MIDI 5        | B22          |             |
|                 | M2       |        | TX- OR MIDI OUT SNK (DIN #5) | MIDI 6        | B24          |             |
|                 | M3       |        | MSW (GND OR NC)              | MIDI 7        | B26          |             |
|                 | M4       |        | GND (DIN #2)                 |               |              |             |
| **MIDI IN**     | m1       |        | RX+ OR MIDI IN SRC (DIN #4)  | MIDI 2        | B16          |             |
|                 | m2       |        | RX- OR MIDI IN SNK (DIN #5)  | MIDI 3        | B18          |             |
|                 | m3       |        | mdetect (GND OR NC)          | MIDI 4        | B20          | D8          |
|                 | m4       |        | GND                          |               |              |             |
| **EXT**         | X1       | Red    | Vcc (Red)                    |               |              |             |
|                 | X2       | Black  | GND (Black, Brown)           |               |              |             |
|                 | X3       | Orange | TX (Orange)                  | MIDI 1        | B14          | D1/TX       |
|                 | X4       | Yellow | RX (Yellow)                  | MIDI 0        | B12          | D0/RX       |
|                 | X5       | Green  | RTS (Green)                  | CTRL 0        | B23          | DTR         |
|                 | X6       | Brown  | xdetect (connect to Vcc)     | CTRL 1        | B25          |             |
| **GeekPort II** | G1       | Red    | Vcc (+5V)                    |               |              |             |
|                 | G2       | Black  | GND                          |               |              |             |
|                 | G3       | Brown  | gdetect (connect to GND)     | GEEK 0        | B3           | A0          |
|                 | G4       | Orange | In 0                         | GEEK 1        | B5           | A1          |
|                 | G5       | Yellow | In 1                         | GEEK 2        | B7           | A2          |
|                 | G6       | Green  | In 2                         | GEEK 3        | B9           | A3          |
|                 | G7       | Blue   | I2C SDA                      | GEEK 4        | B11          | A4/SDA      |
|                 | G8       | Purple | I2C SCL                      | GEEK 5        | B13          | A5/SCL      |
|                 | G9       | Gray   | gselect                      | GEEK 6        | B15          | D5~         |
|                 | G10      |        | Out 0                        | GEEK 7        | B17          | D6~         |
|                 | G11      |        | Out 1                        | GEEK 8        | B19          | D9~         |
|                 | G12      |        | Out 2                        | GEEK 9        | B21          | D10~        |
| **DrivePort**   | D1       |        | Vcc                          |               |              |             |
|                 | D2       |        | GND                          |               |              |             |
|                 | D3       |        | Max-set                      | (CTRL 2)      |              | (D2INT)     |
|                 | D4       |        | Min-set                      | (CTRL 3)      |              | (D3~INT)    |
|                 | D5       |        | Clear-Min/Max                | (CTRL 4)      |              | (D4)        |
|                 | D6       |        | MOSI                         | CTRL 5        |              | D11~/MOSI   |
|                 | D7       |        | LOAD                         | CTRL 6        |              | D12/MISO    |
|                 | D8       |        | SCLCK                        | CTRL 7        |              | D13/SCLCK   |
|                 | D9       |        | VR1                          | (ANLG 0)      |              | (A6)        |
|                 | D10      |        | VR2                          | ANLG 1        |              | A7          |
| **LightPort**   | L1       |        |                              | LSEG 0        |              |             |
|                 | L2       |        |                              | LSEG 1        |              |             |
|                 | L3       |        |                              | LSEG 2        |              |             |
|                 | L4       |        |                              | LSEG 3        |              |             |
|                 | L5       |        |                              | LSEG 4        |              |             |
|                 | L6       |        |                              | LSEG 5        |              |             |
|                 | L7       |        |                              | LSEG 6        |              |             |
|                 | L8       |        |                              | LSEG 7        |              |             |
|                 | L9       |        |                              | LDIG 0        |              |             |
|                 | L10      |        |                              | LDIG 1        |              |             |
|                 | L11      |        |                              | LDIG 2        |              |             |
|                 | L12      |        |                              | LDIG 3        |              |             |
|                 | L13      |        |                              | LDIG 4        |              |             |
|                 | L14      |        |                              | LDIG 5        |              |             |
|                 | L15      |        |                              | LDIG 6        |              |             |
|                 | L16      |        |                              | LDIG 7        |              |             |
| **Internal**    | C1       |        | Vcc                          |               |              |             |
|                 | C2       |        | GND                          |               |              |             |
|                 | C3       |        | NC                           |               |              |             |
|                 | C4       |        | SCL                          | (GEEK 5)      |              | (A5/SCL)    |
|                 | C5       |        | SDA                          | (GEEK 4)      |              | (A4/SDA)    |
| **Unconnected** |          |        | XBAR                         | CTRL 8        |              | D7          |
|                 |          |        | Reset                        | CTRL 9        |              | RST         |


## What's inside


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



