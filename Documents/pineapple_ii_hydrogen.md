# Pineapple II Hydrogen/0.0.0 Tech Doc

## Interface

| Panel/Port      | Pin      | Cable  | Signal                       | Int. Bus      | Int. Port    | Micro Pin    |
| --------------- | -------- | ------ | ---------------------------- | ------------- | ------------ | ------------ |
| **Panel**       | Reset SW |        |                              |               | F3, F4       |              |
|                 | LED      |        |                              |               | F5, F6       | D13          |
| **Power**       | P1       | Red    | Power (+7V)                  |               | F1           |              |
|                 | P2       | Black  | GND                          |               | F2           |              |
| **MIDI OUT**    | M1       |        | NC                           |               |              |              |
|                 | M2       |        | GND                          |               | B2           |              |
|                 | M3       |        | NC                           |               |              |              |
|                 | M4       |        | MIDI OUT SRC                 |               | B3           |              |
|                 | M5       |        | MIDI OUT SNK                 |               | B4           | D1           |
| **MIDI IN**     | m1       |        | NC                           |               |              |              |
|                 | m2       |        | NC                           |               |              |              |
|                 | m3       |        | NC                           |               |              |              |
|                 | m4       |        | MIDI IN SRC                  |               | B5           |              |
|                 | m5       |        | MIDI IN SNK                  |               | B6           | D0           |
| **GeekPort D**  | G1       |        | USB Power                    |               |              |              |
|                 | G2       |        | USB D+                       |               |              |              |
|                 | G3       |        | USB D-                       |               |              |              |
|                 | G4       |        | USB GND (?)                  |               |              |              |
|                 | G5       |        | I2C SDA                      |               |              | D2INT        |
|                 | G6       |        | I2C SCL                      |               |              | D3~INT       |
|                 | G7       |        | Vcc                          |               |              |              |
|                 | G8       |        | Sensor A                     |               |              | A0           |
|                 | G9       |        | Sensor B                     |               |              | A1           |
|                 | G10      |        | Sensor C                     |               |              | A2           |
|                 | G11      |        | Sensor X                     |               |              | A7/D6~       |
|                 | G12      |        | Sensor Y                     |               |              | A9/D9~       |
|                 | G13      |        | Sensor Z                     |               |              | A10/D10~     |
|                 | G14      |        | GND                          |               |              |              |
| **GeekPort II** | G1       |        | Vcc                          |               | F7           |              |
|                 | G2       |        | GND                          |               | F8           |              |
|                 | G3       |        | USB D+                       |               |              |              |
|                 | G4       |        | USB D-                       |               |              |              |
|                 | G5       |        | USB Power                    |               |              |              |
|                 | G6       |        | I2C SDA                      |               | F9, F10      | D2INT        |
|                 | G7       |        | I2C SCL                      |               | F11, F12     | D3~INT       |
|                 | G8       |        | Sensor A                     |               | F13, F14     | A0           |
|                 | G9       |        | Sensor B                     |               | F15, F16     | A1           |
|                 | G10      |        | Sensor C                     |               | F17, F18     | A2           |
|                 | G11      |        | Sensor X                     |               | F19, F20     | A7/D6~       |
|                 | G12      |        | Sensor Y                     |               | F21, F22     | A9/D9~       |
|                 | G13      |        | Sensor Z                     |               | F23, F24     | A10/D10~     |
|                 | G14      |        | GPIO                         |               | F25, F26     | D5~          |
| **Unconnected** |          |        | _RESERVED_                   |               |              | D4           |
|                 |          |        | _RESERVED_                   |               |              | D7           |
|                 |          |        | _RESERVED_                   |               |              | D8           |
|                 |          |        | _RESERVED_                   |               |              | D11~         |
|                 |          |        | _RESERVED_                   |               |              | D12~         |


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



