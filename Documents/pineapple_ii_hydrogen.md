# Pineapple II Hydrogen/0.6.0 Tech Doc

## Interface

| Panel/Port      | Pin      | Cable  | Signal                       | Internal Bus  | BackPort     | Pro Mini Pin |
| --------------- | -------- | ------ | ---------------------------- | ------------- | ------------ | ------------ |
| **Panel**       | Max SW   |        | Max-set (DrivePort 3)        | CTRL 2        |              | D3~INT       |
|                 | Min SW   |        | Min-set (DrivePort 4)        | CTRL 3        |              | D5~          |
|                 | Clear SW |        | Clear-Min-Max (DrivePort 5)  | CTRL 4        |              | A1           |
|                 | VR       |        | Threshold (DrivePort 9)      | CTRL 8        |              | A0           |
|                 | Display  |        | Min/Max/Th/Level indicator   | LDIG, LSEG    |              |              |
| **Power**       | P1       | Red    | Vcc (+5V)                    |               | B1           |              |
|                 | P2       | Black  | GND [Black]                  |               | B[2,4,..,10] |              |
| **XMIDI OUT**   | M1       |        | TX+ OR MIDI OUT SRC (DIN #4) | MIDI 5        | B22          |              |
|                 | M2       |        | TX- OR MIDI OUT SNK (DIN #5) | MIDI 6        | B24          |              |
|                 | M3       |        | MSW (GND OR NC)              | MIDI 7        | B26          |              |
|                 | M4       |        | GND (DIN #2)                 |               |              |              |
| **XMIDI IN**    | m1       |        | RX+ OR MIDI IN SRC (DIN #4)  | MIDI 2        | B16          |              |
|                 | m2       |        | RX- OR MIDI IN SNK (DIN #5)  | MIDI 3        | B18          |              |
|                 | m3       |        | mdetect (GND OR NC)          | MIDI 4        | B20          | D4           |
|                 | m4       |        | GND                          |               |              |              |
| **EXT**         | X1       | Red    | Vcc (Red)                    |               |              |              |
|                 | X2       | Black  | GND (Black, Brown)           |               |              |              |
|                 | X3       | Orange | TX (Orange)                  | MIDI 1        | B14          | D1/TX        |
|                 | X4       | Yellow | RX (Yellow)                  | MIDI 0        | B12          | D0/RX        |
|                 | X5       | Green  | RTS (Green)                  | CTRL 0        | B23          | DTR          |
|                 | X6       | Brown  | xdetect (connect to Vcc)     | CTRL 1        | B25          |              |
| **GeekPort II** | G1       | Red    | Vcc (+5V)                    |               |              |              |
|                 | G2       | Black  | GND                          |               |              |              |
|                 | G3       | Brown  | gdetect (connect to GND)     | GEEK 0        | B3           | A6           |
|                 | G4       | Orange | In 0                         | GEEK 1        | B5           | A7           |
|                 | G5       | Yellow | In 1                         | GEEK 2        | B7           | A2           |
|                 | G6       | Green  | In 2                         | GEEK 3        | B9           | A3           |
|                 | G7       | Blue   | I2C SDA                      | GEEK 4        | B11          | A4/SDA       |
|                 | G8       | Purple | I2C SCL                      | GEEK 5        | B13          | A5/SCL       |
|                 | G9       |        | VREF                         |               | B15          |              |
|                 | G10      |        | Out 0                        | GEEK 6        | B17          | D6~          |
|                 | G11      |        | Out 1                        | GEEK 7        | B19          | D9~          |
|                 | G12      |        | Out 2                        | GEEK 8        | B21          | D10~         |
| **DrivePort**   | D1       |        | Vcc                          |               |              |              |
|                 | D2       |        | GND                          |               |              |              |
|                 | D3       |        | Max-set/BLANK                | (CTRL 2)      |              | (D3~INT)     |
|                 | D4       |        | Min-set/GSCLCK               | (CTRL 3)      |              | (D5~)        |
|                 | D5       |        | Clear-Min-Max/XLAT           | (CTRL 4)      |              | (A1)         |
|                 | D6       |        | MOSI                         | CTRL 5        |              | D11~/MOSI    |
|                 | D7       |        | MISO/LOAD                    | CTRL 6        |              | D12/MISO     |
|                 | D8       |        | SCLCK                        | CTRL 7        |              | D13/SCLCK    |
|                 | D9       |        | VR/MODE                      | CTRL 8        |              | (A0)         |
|                 | D10      |        | Reset                        | CTRL 10       |              |              |
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
| **Unconnected** |          |        | XBAR                         | CTRL 9        |              | D8           |
|                 |          |        | _RESERVED_                   |               |              | D2~INT*      |
|                 |          |        | _RESERVED_                   |               |              | D7*          |

*Not available on Pro Trinket.


## Parts

* Logic board
* U1: Arduino Pro Mini 328 5V [SparkFun](https://www.sparkfun.com/products/11113) [Switch-Science](https://www.switch-science.com/catalog/946/)
* U2: MAX7219CNG [SparkFun](https://www.sparkfun.com/products/9622) [Marutsu](http://www.marutsu.co.jp/pc/i/60116/)
* IC1: 74HC4051 [Kyohritsu](http://eleshop.jp/shop/g/gT11593/)
* IC2 and IC4: LTC1485CN8 x2 [Akizuki](http://akizukidenshi.com/catalog/g/gI-01869/)
* IC3: 74LS07N [Kyohritsu](http://eleshop.jp/shop/g/gT11678/)
* OK1: TLP552 or TLP2962 [Kyohritsu](http://eleshop.jp/shop/g/g44R13L/)
* T1: 2SC1815Y [Kyohritsu](http://eleshop.jp/shop/g/gA4B135/)
* D1 to D3: 1S1588 or similar [Kyohritsu](http://eleshop.jp/shop/g/g1CS13I/)
* LED1 and LED2: Green and Red LEDs
* C1: 0.1u
* C2 to C7: 0.01u x6
* R1: 22k
* R2: 10k
* R3: 3.3k
* R4, R8, and R9: 220
* R5 and R6: 330 x2
* R7 and R10: 120
* K1 and K2: G5V-2 DC5V [Kyohritsu](http://eleshop.jp/shop/g/g41713R/)
* CN1: JST PH 16p side [Kyohritsu](http://eleshop.jp/shop/g/g61L15C/)
* CN2: JST PH 10p side [Kyohritsu](http://eleshop.jp/shop/g/g61L146/)
* JP1: Pinheader 5p [Kyohritsu](http://eleshop.jp/shop/g/gEAT417/)
* JP2: Pinheader 2p [Kyohritsu](http://eleshop.jp/shop/g/gEAT417/)
* SV1: Harting 26p side [Kyohritsu](http://eleshop.jp/shop/g/g4A114X/)
* Case Takachi MX2-8-13BB [Kyohritsu](http://eleshop.jp/shop/g/g82731D/)
* SW: Nidech Copal-8A [Kyohritsu](http://eleshop.jp/shop/g/gD1G362/)
* SW: Miyama MS-402 [Kyohritsu](http://eleshop.jp/shop/g/g41W131/)
* VR: B 10k Supertech VR [Kyohritsu](http://eleshop.jp/shop/g/g4BP13G/)
* Knob
* LED: Kathode-common matrix LED LTP-305G [Akizuki](http://akizukidenshi.com/catalog/g/gI-07441/)
* LED: 3mm Green LED PY3407S [Akizuki](http://akizukidenshi.com/catalog/g/gI-03461/)
* Con: HR10A-7R-6S [Marutsu](http://www.marutsu.co.jp/pc/i/37647/)
* Con: HR10A-10R-12S [Marutsu](http://www.marutsu.co.jp/pc/i/37640/)
* Con: 4p mini pin jack Marushin MJ-079 x2 [Kyohritsu](http://eleshop.jp/shop/g/g6AR144/)
* Con: DC jack Marushin MJ-17 [Kyohritsu](http://eleshop.jp/shop/g/g3CU147/)
* Con: Harting 26p plug [Kyohritsu](http://eleshop.jp/shop/g/gC32361/) + [Kyohritsu](http://eleshop.jp/shop/g/gC32368/)
* Con: JST PH 16p plug [Kyohritsu](http://eleshop.jp/shop/g/g61K14H/)
* Con: JST PH 10p plug [Kyohritsu](http://eleshop.jp/shop/g/g61K14B/) 
* PH harness [Kyohritsu](http://eleshop.jp/shop/g/gEAO313/)
* Flat cable [Kyohritsu](http://eleshop.jp/shop/g/gA5G149/)



