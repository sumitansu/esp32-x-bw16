# ESP32 X BW16

One esp32 wroom 32u 38 pin module running the main script with a bw16 as it's master connected via rx and tx providing a web ui at 5ghz in order to control the device. 4 NRF24L01 pa lna module which will be connected to the esp32 transmitting signals etc. One 0.96' oled i2c 4pin display connected to the esp32 to show it's current state or mode some 100uf electrolytic capacitors on vcc and gnd of NRF24L01 pa lna module one 3mm led with a 4.7k ohm resistor(or smth else if u suggest) one push button one type c to power the circuit. 
Wiring
ESP32 Pin Assignments
NRF1 - HSPI
NRF24 Pin	ESP32 GPIO
CE	16
CSN	15
SCK	14
MOSI	13
MISO	12
VCC	3.3V
GND	GND
NRF2 - VSPI
NRF24 Pin	ESP32 GPIO
CE	22
CSN	21
SCK	18
MOSI	23
MISO	19
VCC	3.3V
GND	GND
NRF3 - HSPI shared (same SCK/MOSI/MISO as NRF1, unique CE/CSN)
NRF24 Pin	ESP32 GPIO
CE	32
CSN	17
SCK	14
MOSI	13
MISO	12
VCC	3.3V
GND	GND
NRF4 - VSPI shared (same SCK/MOSI/MISO as NRF2, unique CE/CSN)
NRF24 Pin	ESP32 GPIO
CE	25
CSN	2
SCK	18
MOSI	23
MISO	19
VCC	3.3V
GND	GND
OLED (I2C)
OLED Pin	ESP32 GPIO
SDA	4
SCL	5
VCC	3.3V
GND	GND
UI
Component	ESP32 GPIO
Button	GPIO0 → GND
LED	GPIO27
UART to BW16
Signal	ESP32 GPIO	BW16 Pin
RX	GPIO26	PB1 (TX)
TX	GPIO33	PB2 (RX)
GND	GND	GND
3V3	3V3	3V3
Note: Cross the TX/RX lines. ESP32 TX → BW16 RX and ESP32 RX → BW16 TX.
Also note in this setup also add a type c port somewhere which should be able to power this whole setup and also a 5v to 3.3v converter which support upto 5A so it can power at worst current spike too.
