# Smart Mirror

The Smart Mirror is an ‘Two-Way mirror’ with an electronic (LED) display behind the glass. 
Swipe between various pages that display information like the latest news, date, weatherforcast, calender, live footage of the ISS, Daily jokes, Broadcasting.... and so much more!

in terms of software we've chosen for the open-source ’MagicMirror²’ software that runs on an Raspberry Pi 2,3B+ or 4B with Raspbian installed. 
This make's it very easy to customize the layout of your mirror (add, create, change different modules). 

The custom designed backplate allows u to: easily mount all the electronics, hang the mirror on the wall (landscape or portrait), customize the sides of your mirror in any material like wood, metal, plastic.

## Specification & features

Below you can find the specs/features that you need to know before building this project!

* **24" LED monitor**  
  We used an 24 inch  LED monitor from LVC. But any monitor with a HDMI input will work.
  
* **Two way mirror glass**  
  The glass is custom made and has translucency of about 35%. The borders of the mirror are made opaque.  
  The Technical drawing for this glass can be downloaded above (Two-Way Mirror.PDF).  
  **PAY ATTENTION:** the dimensions of the glass are based on the LED monitor we use!
 
* **Aluminium Back plate**  
  The backplate is custom made, the technical drawing and production files can be downloaded above.  
    It has multiple purposes as metioned before, below a detailed list:    
  - Concealment for the wires and electronics like the Raspberry Pi, infrared sensors, motion sensor, power supply, connector board
  - Easy wall mounting in landscape or portrait orientation
  - Brackets with threaded holes, so you can customize the sides of your mirror in any material like wood, metal, plastic….. Max. thickness material: 10mm.
    see picture below for an example with lasercutted okoume wood 6mm thick side finish. (lasercut files also available for download above.
  
* **Connector PCB board**  
This is an custom designed PCB that extends some of the GPIO pins of the Raspberry Pi. Production files and schematic can also be downloaded above
This board allows you to easily connect the Infrared sensors, motion sensor and safely power LED strips without
the need of soldering, and blowing up your Raspberry Pi.

* **IR sensor x2**  
  The IR sensors are used to swipe between pages, these are also mounted on the backplate

* **PIR sensor**  
  The motion sensor detects if ther is any movement within its range, the mirror will turn on. Also mountable on the backplate

* **Power supply**  
We've used an Power supply from AUKEY. It has 5X USB 3.0 ports with Quick Charge function, to power up the Raspberry Pi and the LED
strips. There are 3 spare USB ports.
  This Power suply is also integrated in the Back Plate, but any decent power supply will work
  
* **open source-software "MagicMirror²"**
  More information about this software can be found here: ([MagicMirrorsoftware](https://magicmirror.builders/))

### You will need to do the following things for the project to work:

### Level of difficulty: Intermediate

## MATERIALS

### Ingredients:
* Raspberry Pi 3B/B+ or 4B set (e.g. [Whadda PI4SET](https://www.vellemanformakers.com/product/raspberry-pi-4-2gb-starter-kit-pi4set/))
    - Raspberry Pi (3B/B+ or 4B)
    - Good quality USB power supply
    - \>= 8 GB MicroSD Card
* IR obstacle avoidance sensor module  (e.g. [IR sensor VMA330](https://whadda.com/product/ir-obstacle-avoidance-sensor-module-vma330/))
* PIR motion sensor (e.g. [PIR sensor WPSE314](https://whadda.com/product/pir-motion-sensor-wpse314/))
* Bolts
   - M2X14 (x2)
   - M2.5x8 (x10)
   - M4x10


### Tools:
* Working locally on Raspberry Pi:
  - HDMI Screen/monitor
  - USB Keyboard
  - USB Mouse
  - Internet connection (WiFi or wired ethernet)
* Working remotely on pc:
    - PC
    - RPi & PC connected to same network (WiFi or wired ethernet)




## PROGRAMMING  the development board

### Dev board: Raspberry Pi (3B/B+, 4B)

### Code language: Python (3)

### Difficulty: Intermediate

### Preparations:

1) If you don't have a (recent) version of Raspberry Pi OS installed on the Pi's microSD card, go to [raspberrypi.org/downloads](https://www.raspberrypi.org/downloads/) and download the latest version of the Raspberry Pi Imager. Use the Raspberry Pi Imager to flash the MicroSD card with the latest verion of Raspberry Pi OS. 

From this point on there are 2 ways to configure the pi: **on the pi itself** by connecting the necessary peripherals (mouse, keyboard and screen) to it directly, or **using your pc to connect to it remotely**. If you plan to use the 1st option you can skip step 2 and proceed directly to step 3.

2) If you want to use WiFi follow [this guide](https://www.raspberrypi.org/documentation/configuration/wireless/headless.md) to configure the WiFi access details before you proceed. 
Navigate to the SD Card partition named ```BOOT``` and add an empty file called ```ssh```. Make sure that this file doesn't have a file extension. In Windows you might need to check the ```File name extensions``` box in the View tab in file explorer to be able to do this.

3) Insert the MicroSD card into the Pi and connect all of your peripherals (if you're planning to use a seperate monitor). Also plugin a network cable if you're planning to use a wired ethernet connection. Power up the pi by connecting it to the USB power supply adapter.

4) Wait 2-3 min until the pi is fully booted. If you're using a seperate monitor, run through the initial Raspberry Pi OS setup wizard to configure network connections, etc... 
If you're connecting to the pi remotely, go to your network router setup webpage or use an IP-scanner (e.g. [Angry IP Scanner](https://angryip.org/download/)) to find the assigned IP-address of your pi and connect to it by opening Powershell/Terminal and type in the following command: ```ssh pi@<REPLACE WITH IP ADDRESS>```. The default password is ```raspberry```.

5) To make sure your pi is fully up-to-date, run the following command: ```sudo apt update && sudo apt upgrade -y```

6) Enable the I2C interface (necessary to use the OLED display) by running ```sudo raspi-config``` and selecting ```5 Interfacing Options > P5 I2C > Yes```.

## Installing necessary software

Run the following commands:

1) Make sure the python package manager (pip) is installed:
```bash
sudo apt install python3-pip
```

2) Install git client so we can easily download the project code
```bash
sudo apt install git
```

1) Download the project code
```bash
git clone https://github.com/Whaddadraft/Whadda_you_see_RPi.git && cd ./Whadda_you_see_RPi
```

4) Install the Text-To-Speech module using our install script:
```bash
sudo chmod +x install_tts.sh && sudo ./install_tts.sh
```

5) Install the required python modules:
```bash
pip3 install -r requirements.txt
```

6) If you are using headphones via the 3.5 mm audio jack, use the raspi-config tool to select the forced headphones audio output
```bash
sudo raspi-config
7 Advanced Options > A4 Audio > 1 Headphones
```
## Prepping the connection

It is possible to wire everything up without a breadboard using Male-to-Female jumper wires, although using a breadbord and a Raspberry Pi GPIO extension/breakout board will make the process a lot easier. 
