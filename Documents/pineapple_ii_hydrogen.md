# Pineapple II Hydrogen/0.6.0 Tech Doc

## Interface

| Panel/Port      | Pin      | Cable  | Signal                       | Internal Bus  | BackPort     | Pro Mini Pin |
| --------------- | -------- | ------ | ---------------------------- | ------------- | ------------ | ------------ |
| **Panel**       | Max SW   |        | Max-set (DrivePort 3)        | CTRL 2        |              | D2INT*       |
|                 | Min SW   |        | Min-set (DrivePort 4)        | CTRL 3        |              | D3~INT       |
|                 | Clear SW |        | Clear-Min/Max (DrivePort 5)  | CTRL 4        |              | D7*          |
|                 | VR1      |        | Threshold (DrivePort 9)      | ANLG 0        |              | A6           |
|                 | Display  |        | Min/Max/Th/Level indicator   | LDIG, LSEG    |              |              |
| **Power**       | P1       | Red    | Vcc (+5V)                    |               | B1           |              |
|                 | P2       | Black  | GND [Black]                  |               | B[2,4,..,10] |              |
| **XMIDI OUT**   | M1       |        | TX+ OR MIDI OUT SRC (DIN #4) | MIDI 5        | B22          |              |
|                 | M2       |        | TX- OR MIDI OUT SNK (DIN #5) | MIDI 6        | B24          |              |
|                 | M3       |        | MSW (GND OR NC)              | MIDI 7        | B26          |              |
|                 | M4       |        | GND (DIN #2)                 |               |              |              |
| **XMIDI IN**    | m1       |        | RX+ OR MIDI IN SRC (DIN #4)  | MIDI 2        | B16          |              |
|                 | m2       |        | RX- OR MIDI IN SNK (DIN #5)  | MIDI 3        | B18          |              |
|                 | m3       |        | mdetect (GND OR NC)          | MIDI 4        | B20          | D8           |
|                 | m4       |        | GND                          |               |              |              |
| **EXT**         | X1       | Red    | Vcc (Red)                    |               |              |              |
|                 | X2       | Black  | GND (Black, Brown)           |               |              |              |
|                 | X3       | Orange | TX (Orange)                  | MIDI 1        | B14          | D1/TX        |
|                 | X4       | Yellow | RX (Yellow)                  | MIDI 0        | B12          | D0/RX        |
|                 | X5       | Green  | RTS (Green)                  | CTRL 0        | B23          | DTR          |
|                 | X6       | Brown  | xdetect (connect to Vcc)     | CTRL 1        | B25          |              |
| **GeekPort II** | G1       | Red    | Vcc (+5V)                    |               |              |              |
|                 | G2       | Black  | GND                          |               |              |              |
|                 | G3       | Brown  | gdetect (connect to GND)     | GEEK 0        | B3           | A0           |
|                 | G4       | Orange | In 0                         | GEEK 1        | B5           | A1           |
|                 | G5       | Yellow | In 1                         | GEEK 2        | B7           | A2           |
|                 | G6       | Green  | In 2                         | GEEK 3        | B9           | A3           |
|                 | G7       | Blue   | I2C SDA                      | GEEK 4        | B11          | A4/SDA       |
|                 | G8       | Purple | I2C SCL                      | GEEK 5        | B13          | A5/SCL       |
|                 | G9       | Gray   | gselect                      | GEEK 6        | B15          | D5~          |
|                 | G10      |        | Out 0                        | GEEK 7        | B17          | D6~          |
|                 | G11      |        | Out 1                        | GEEK 8        | B19          | D9~          |
|                 | G12      |        | Out 2                        | GEEK 9        | B21          | D10~         |
| **DrivePort**   | D1       |        | Vcc                          |               |              |              |
|                 | D2       |        | GND                          |               |              |              |
|                 | D3       |        | Max-set                      | (CTRL 2)      |              | (D2INT)      |
|                 | D4       |        | Min-set                      | (CTRL 3)      |              | (D3~INT)     |
|                 | D5       |        | Clear-Min/Max                | (CTRL 4)      |              | (D4)         |
|                 | D6       |        | MOSI                         | CTRL 5        |              | D11~/MOSI    |
|                 | D7       |        | LOAD                         | CTRL 6        |              | D12/MISO     |
|                 | D8       |        | SCLCK                        | CTRL 7        |              | D13/SCLCK    |
|                 | D9       |        | VR1                          | (ANLG 0)      |              | (A6)         |
|                 | D10      |        | VR2                          | ANLG 1        |              | A7           |
| **LightPort**   | L1       |        |                              | LSEG 0        |              |              |
|                 | L2       |        |                              | LSEG 1        |              |              |
|                 | L3       |        |                              | LSEG 2        |              |              |
|                 | L4       |        |                              | LSEG 3        |              |              |
|                 | L5       |        |                              | LSEG 4        |              |              |
|                 | L6       |        |                              | LSEG 5        |              |              |
|                 | L7       |        |                              | LSEG 6        |              |              |
|                 | L8       |        |                              | LSEG 7        |              |              |
|                 | L9       |        |                              | LDIG 0        |              |              |
|                 | L10      |        |                              | LDIG 1        |              |              |
|                 | L11      |        |                              | LDIG 2        |              |              |
|                 | L12      |        |                              | LDIG 3        |              |              |
|                 | L13      |        |                              | LDIG 4        |              |              |
|                 | L14      |        |                              | LDIG 5        |              |              |
|                 | L15      |        |                              | LDIG 6        |              |              |
|                 | L16      |        |                              | LDIG 7        |              |              |
| **Internal**    | C1       |        | Vcc                          |               |              |              |
|                 | C2       |        | GND                          |               |              |              |
|                 | C3       |        | NC                           |               |              |              |
|                 | C4       |        | SCL                          | (GEEK 5)      |              | (A5/SCL)     |
|                 | C5       |        | SDA                          | (GEEK 4)      |              | (A4/SDA)     |
| **Unconnected** |          |        | XBAR                         | CTRL 8        |              | D4           |
|                 |          |        | Reset                        | CTRL 9        |              | RST          |

*Not available on Pro Trinket.


## Parts

* Logic board
* U1: Arduino Pro Mini 5V [Switch-Science](https://www.switch-science.com/catalog/946/)
* U2: MAX7219
* IC1: 4051N
* IC2 and IC4: LTC1485 x2
* IC3: 74LS07N
* OK1: TLP552 or TLP2962
* T1: 2SC1815Y
* D1 to D3: 1S1588 or similar
* LED1 and LED2: Green and Red LEDs
* C1: 0.1u
* C2 to C7: 0.01u x6
* R1: 22k
* R2: 10k
* R3: 3.3k
* R4, R8, and R9: 220
* R5 and R6: 330 x2
* R7 and R10: 120
* K1 and K2: G5V-2
* CN1: JST PH 16p side
* CN2: JST PH 10p side
* JP1: Pinheader 5p
* JP2: Pinheader 1p
* SV1: Harting 26p side
* Case Takachi MX2-8-13
* SW: Nidech Copal-8A
* SW: Miyama MS-402
* VR: B 10k Supertech VR
* Knob
* LED: Kathode-common matrix LED LTP-305G
* LED: 3mm Green LED PY3407S
* Con: HR10A-7R-6P
* Con: HR10A-10R-12S
* Con: 4p mini pin jack EST MJ-079 x2
* Con: DC jack EST MJ-17
* Con: Harting 26p plug
* Con: JST PH 10p plug
* Con: JST PH 16p plug
* Flat cable


# Note for NXP1768 edition

| Panel/Port      | Pin      | Cable  | Signal                       | Internal Bus  | BackPort     | Arduino Pin |
| --------------- | -------- | ------ | ---------------------------- | ------------- | ------------ | ----------- |
| **Panel**       | Max SW   |        | Max-set (DrivePort 3)        | CTRL 2        |              | p29         |
|                 | Min SW   |        | Min-set (DrivePort 4)        | CTRL 3        |              | p30         |
|                 | Clear SW |        | Clear-Min/Max (DrivePort 5)  | CTRL 4        |              | p11         |
|                 | VR1      |        | Threshold (DrivePort 9)      | ANLG 0        |              | p19/AD      |
|                 | Display  |        | Min/Max/Th/Level indicator   | LDIG, LSEG    |              |             |
| **Power**       | P1       | Red    | Vcc (+5V)                    |               | B1           |             |
|                 | P2       | Black  | GND [Black]                  |               | B[2,4,..,10] |             |
| **XMIDI OUT**   | M1       |        | TX+ OR MIDI OUT SRC (DIN #4) | MIDI 5        | B22          |             |
|                 | M2       |        | TX- OR MIDI OUT SNK (DIN #5) | MIDI 6        | B24          |             |
|                 | M3       |        | MSW (GND OR NC)              | MIDI 7        | B26          |             |
|                 | M4       |        | GND (DIN #2)                 |               |              |             |
| **XMIDI IN**    | m1       |        | RX+ OR MIDI IN SRC (DIN #4)  | MIDI 2        | B16          |             |
|                 | m2       |        | RX- OR MIDI IN SNK (DIN #5)  | MIDI 3        | B18          |             |
|                 | m3       |        | mdetect (GND OR NC)          | MIDI 4        | B20          | p8          |
|                 | m4       |        | GND                          |               |              |             |
| **XUSB**        | U1       | Red    | Vcc                          |               |              |             |
|                 | U2       | Black  | GND                          |               |              |             |
|                 | U3       |        | _D+_                         |               |              |             |
|                 | U4       |        | _D-_                         |               |              |             |
|                 | U5       |        | _Reset_                      | CTRL 9        | B23          | _nR_        |
|                 | U6       |        | _Reserved_                   | CTRL 1        | B25          |             |
| **GeekPort II** | G1       | Red    | Vcc (+5V)                    |               |              |             |
|                 | G2       | Black  | GND                          |               |              |             |
|                 | G3       | Brown  | gdetect (connect to GND)     | GEEK 0        | B3           | p15/AD      |
|                 | G4       | Orange | In 0                         | GEEK 1        | B5           | p16/AD      |
|                 | G5       | Yellow | In 1                         | GEEK 2        | B7           | p17/AD      |
|                 | G6       | Green  | In 2                         | GEEK 3        | B9           | p18/AD/DA   |
|                 | G7       | Blue   | I2C SDA _(3.3V)_             | GEEK 4        | B11          | p28/SDA/TX  |
|                 | G8       | Purple | I2C SCL _(3.3V)_             | GEEK 5        | B13          | p27/SCL/RX  |
|                 | G9       | Gray   | gselect _(3.3V)_             | GEEK 6        | B15          | p21/PWM     |
|                 | G10      |        | Out 0 _(3.3V)_               | GEEK 7        | B17          | p22/PWM     |
|                 | G11      |        | Out 1 _(3.3V)_               | GEEK 8        | B19          | p23/PWM     |
|                 | G12      |        | Out 2 _(3.3V)_               | GEEK 9        | B21          | p24/PWM     |
| **DrivePort**   | D1       |        | Vcc                          |               |              |             |
|                 | D2       |        | GND                          |               |              |             |
|                 | D3       |        | Max-set                      | (CTRL 2)      |              | (p29)       |
|                 | D4       |        | Min-set                      | (CTRL 3)      |              | (p30)       |
|                 | D5       |        | Clear-Min/Max                | (CTRL 4)      |              | (p11)       |
|                 | D6       |        | MOSI                         | CTRL 5        |              | p5/MOSI     |
|                 | D7       |        | LOAD                         | CTRL 6        |              | p6/MISO     |
|                 | D8       |        | SCLCK                        | CTRL 7        |              | p7/SCLCK    |
|                 | D9       |        | VR1                          | (ANLG 0)      |              | (p19/AD)    |
|                 | D10      |        | VR2                          | ANLG 1        |              | p20/AD      |
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
| **Unconnected** |          |        | XBAR                         | CTRL 8        |              | p12         |



