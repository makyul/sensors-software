# Connecting sensors to robonomics network
## Requiremets
* ESP8266 Node MCU v3
* particle sensor SDS011
* micro USB cable
* connecting wires
---
## Installation
### For Linux:
Install platformio:
```bash
pip install -U platformio
```
Clone ropository with firmware
```bash
git clone https://github.com/LoSk-p/sensors-software
cd sensors-software/airrohr-firmware
```
Connect your ESP to computer via micro USB and upload firmware:
```bash
platformio run -e nodemcuv2_en -t upload
```
You can choose language changing "nodemcuv2_en".

In the end you will see

![upload](https://github.com/LoSk-p/media/blob/master/esp/upload.jpg)

---
### For Windows:
Download and unpack repository with firmware from https://github.com/LoSk-p/sensors-software. Choose "Download ZIP":

![git](https://github.com/LoSk-p/media/blob/master/git.PNG)

Then install Visual Studio Code. You can download it from [here](https://code.visualstudio.com/Download).

In Visual Studio Code you need to install Platformio IDE extention. Platformio use python so if you don't have it or you have python version less then 3.5, install the latest version of python3 (you can install it from [here](https://www.python.org/downloads/)). 

In Extentions find Platformio IDE and install it:

![ext](https://github.com/LoSk-p/media/blob/master/ist_plat.PNG)

Go to Home and click to Open Project:

![open_pr](https://github.com/LoSk-p/media/blob/master/plat_home.PNG)

Find sensors-software-master directory, choose airrohr-firmware and open it:

![proj](https://github.com/LoSk-p/media/blob/master/open_proj.PNG)

Connect your ESP to computer via micro USB, then open terminal and write:
```bash
pio run -e nodemcuv2_en -t upload
```

![term](https://github.com/LoSk-p/media/blob/master/terminal.PNG)

---
## Configuration
Connect to airRohr--xxxxxxx wi-fi network and in your browser write address 192.168.4.1:

![menu](https://github.com/LoSk-p/media/blob/master/esp/menu1.jpg)

Go to Configuration and in Wi-Fi Settings add information about your wi-fi network:

![config](https://github.com/LoSk-p/media/blob/master/esp/config.png)

Reboot NodeMcu and it will connect to your wi-fi.

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
