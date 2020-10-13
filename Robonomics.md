# Connecting sensors to robonomics network
### Requiremets
* ESP8266 Node MCU v3
* particle sensor SDS011
* micro USB cable
* connecting wires

### Installation
Download loader from here: https://github.com/opendata-stuttgart/airrohr-firmware-flasher/releases

Chose version for your OS:

![list](https://github.com/LoSk-p/media/blob/master/esp/load.jpg)
### Building
Run loader and choose firmware.

For ubuntu:
```bash 
chmod +x airRohr-firmware-flasher-0.3.1-Ubuntu_18.04_amd64
./airRohr-firmware-flasher-0.3.1-Ubuntu_18.04_amd64
```
![loader](https://github.com/LoSk-p/media/blob/master/esp/loader_1.jpg)
### Configuration
Connect to airRohr--xxxxxxx wi-fi network and in your browser write address 192.168.4.1:

![menu](https://github.com/LoSk-p/media/blob/master/esp/menu1.jpg)

Go to Configuration and in Wi-Fi Settings add information about your wi-fi network:

![config](https://github.com/LoSk-p/media/blob/master/esp/config.png)

Reboot NodeMcu and it will connect to your wi-fi.

Find NodeMcu in local network, for ubuntu you can use nmap:
```bash
nmap -sn 192.168.100.0/24
```
Write in your browser it's local address, go to Configuration and tick 'Send to custom API'. In 'Server' write 'connectivity.robonomics.network' and 'Port' - '65', then enable GPS and all sensors that you use.

![robonomics](https://github.com/LoSk-p/media/blob/master/esp/robonomics.jpg)

### Results
Go to sensors.robonomics.network, and you will see your sensor on the map.
![link](https://github.com/LoSk-p/media/blob/master/esp/sensors_rob.jpg)
![map](https://github.com/LoSk-p/media/blob/master/esp/map.jpg)
