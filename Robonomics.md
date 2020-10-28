# Connecting sensors to robonomics network
## Requiremets
* ESP8266 Node MCU v3
* particle sensor SDS011
* temperature and humidity sensor BME280 or DHT22 (optional)
* micro USB cable
* connecting wires
---
## Assembly
### Connection diagram

![scheme](https://github.com/LoSk-p/media/blob/master/scheme.PNG)

### Connecting SDS011

* Pin 1 (TX) -> (RX) Pin D1 (GPIO5)
* Pin 2 (RX) -> (TX) Pin D2 (GPIO4)
* Pin 3 (GND) -> GND
* Pin 4 (2.5m) -> unused
* Pin 5 (5V) -> VU
* Pin 6 (1m) -> unused

Sensor's sold complete with USB adapter and connection wires. You don't need USB adapter, so disconnect wires from it.

![disconnect](https://github.com/LoSk-p/media/blob/master/assembly_usb.PNG)

You may connect it to ESP via connecting wires "Female-Male":

![f-m](https://github.com/LoSk-p/media/blob/master/conn.PNG)

And connect them to your ESP according connection diagram.

Or you can use wires from USB adapter. Disconnect one wire: push on it with some sharp object and carefully pull the wire:
Insert it to extreme connector:

![extreme_con](https://github.com/LoSk-p/media/blob/master/assembly_wires.PNG)

Insert it to extreme connector:

![extr](https://github.com/LoSk-p/media/blob/master/wires1.PNG)

Then cut connector in the middle:

![cut](https://github.com/LoSk-p/media/blob/master/assembly_wires2.PNG)

And connect them to ESP accoding to connection diagram:

![esp_con](https://github.com/LoSk-p/media/blob/master/esp_con.PNG)

### Connecting DHT22

* Pin 1 => 3V3
* Pin 2 => Pin D7 (GPIO13)
* Pin 3 => unused
* Pin 4 => GND

### Connecting BME280

* VCC -> Pin 3V3
* GND -> Pin GND
* SCL -> Pin D4 (GPIO2)
* SDA -> Pin D3 (GPIO0)

---
## Device firmware
Download airrohr-flasher for your OS from [here](https://github.com/airalab/sensors-connectivity/releases/tag/v0.4).
Connect ESP to computer via micro-USB and run flasher. 
For Linux don't forget to give it permission to execute:
```bash
chmod +x airrohr-flasher-linux
./airrohr-flasher-linux
```
Choose firmware (english or russian) and push upload. 

---
## Configuration
Reboot your ESP (just reconnect USB to computer).
Then connect to airRohr--xxxxxxx wi-fi network and in your browser write address 192.168.4.1:

![menu](https://github.com/LoSk-p/media/blob/master/esp/menu1.jpg)

Go to Configuration and in Wi-Fi Settings add information about your wi-fi network:

![config](https://github.com/LoSk-p/media/blob/master/W-fi.PNG)

Then press "Save configuration and restart" and ESP will connect to your wi-fi.

![save](https://github.com/LoSk-p/media/blob/master/Снимок.PNG)

---
Then you need to find NodeMcu in local network.
### For Linux:
Firstly find your address:
```bash
ip a
```

![ipa](https://github.com/LoSk-p/media/blob/master/esp/ipa.jpg)

Then you can find NodeMcu with nmap (use your address with "0" in the end):
```bash
nmap -sn 192.168.100.0/24
```

---
### For Windows:
Firstly find your address. In Settings - Network & Internet - Wi-Fi click to Hardware properties:

![addr_win](https://github.com/LoSk-p/media/blob/master/addr.PNG)

Then install Advanced IP Scanner from [here](https://www.advanced-ip-scanner.com/ru/). Open it and scan your network (write your address with 0 and 255 in the end)

![ip_scan](https://github.com/LoSk-p/media/blob/master/ipscan.PNG)

---

Write in your browser it's local address, go to Configuration and tick 'API Robonomics'. 

![robonomics](https://github.com/LoSk-p/media/blob/master/esp/APIrobonomics.jpg)

Then enable GPS and all sensors that you use and write your coordinates:

![gps](https://github.com/LoSk-p/media/blob/master/esp/gps.jpg)

---

## Results
Go to [sensors.robonomics.network](https://sensors.robonomics.network/#/), and you will see your sensor on the map.
![map](https://github.com/LoSk-p/media/blob/master/esp/map.jpg)
