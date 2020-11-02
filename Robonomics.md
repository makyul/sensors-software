# Connecting sensors to robonomics network
## Requiremets
* ESP8266 Node MCU v3
* particle sensor SDS011
* micro USB cable
* connecting wires
---
## Assembly
### Connection diagram

![scheme](https://github.com/LoSk-p/media/blob/master/photo_2020-10-28_17-21-11.jpg)

### Connecting SDS011

* Pin 1 (TX) -> (RX) Pin D1 (GPIO5)
* Pin 2 (RX) -> (TX) Pin D2 (GPIO4)
* Pin 3 (GND) -> GND
* Pin 4 (2.5m) -> unused
* Pin 5 (5V) -> VU
* Pin 6 (1m) -> unused

Sensor is sold with USB adapter and connection wires. You don't need USB adapter, so disconnect wires from it.

![disconnect](https://github.com/LoSk-p/media/blob/master/assembly_usb.PNG)

You may connect it to ESP via connecting wires "Female-Male":

![f-m](https://github.com/LoSk-p/media/blob/master/conn.PNG)

And connect them to your ESP according to the connection diagram.

Or you can use wires from USB adapter. Disconnect one wire: push on it with some sharp object and carefully pull the wire:

![extreme_con](https://github.com/LoSk-p/media/blob/master/assembly_wires.PNG)

Insert it to last connector:

![extr](https://github.com/LoSk-p/media/blob/master/wires1.PNG)

Then cut connector in the middle:

![cut](https://github.com/LoSk-p/media/blob/master/assembly_wires2.PNG)

And connect them to ESP accoding to the connection diagram:

![esp_con](https://github.com/LoSk-p/media/blob/master/esp_con.PNG)

---
## Device firmware
Download `airrohr-flasher` from the latest release for your OS. Releases you can find [here](https://github.com/airalab/sensors-connectivity/releases).
Connect ESP to computer via micro-USB and run flasher. 

### For Linux:
Firstly you need to get permission to USB port:
```bash
sudo usermod -a -G dialout $USER
```
Then restart computer.

Now you can run flasher (don't forget to give it permission to execute):
```bash
chmod +x airrohr-flasher-linux
./airrohr-flasher-linux
```
---
### For windows:
Unpack flasher and run it with double click.

---
Choose firmware (english or russian) and press upload. It will take a few minutes.

![flasher](https://github.com/LoSk-p/media/blob/master/flasher.PNG)

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
Then you need to find ESP in local network (for that your computer and ESP must be in one network). You can do it using airrohr-flasher. Run it and go to Discovery and press Refresh, then you'll be able to see the address.

![addr](https://github.com/LoSk-p/media/blob/master/flaser2.PNG)

---

Write in your browser ESP local address, go to Configuration and tick 'API Robonomics'. 

![robonomics](https://github.com/LoSk-p/media/blob/master/esp/APIrobonomics.jpg)

Then enable GPS and all sensors that you use and write your coordinates:

![gps](https://github.com/LoSk-p/media/blob/master/esp/gps.jpg)

Then press "Save configuration and restart".

---

## Results
Go to [sensors.robonomics.network](https://sensors.robonomics.network/#/), and you will see your sensor on the map.
![map](https://github.com/LoSk-p/media/blob/master/esp/map.jpg)
