# Raspberry Pi smart mirror

![POINT4](./pictures/Rpi_smart_mirror2.jpg)

This project is a Raspberry Pi based two-way mirror with an electronic (in oure case: LED) display behind semi reflecting glass. 
The smart mirror allows you to swipe between various pages that display information like the latest news, the weatherforcast, your calender, live footage of the ISS, daily jokes, broadcasting.... and so much more!

In terms of software, we have chosen for the open-source ’MagicMirror²’ software that runs on an Raspberry Pi 2, 3B+ or 4B with Raspbian installed. 
This makes it very easy to customize the layout of your mirror (add, create, change different modules). 

The custom designed backplate allows you to: easily mount all the electronics, hang the mirror on the wall (landscape or portrait), and customize the sides of your mirror in any material like wood, metal, plastic.

## Specifications & features

Below, you can find the specs/features that you need to know before building this project!

* **24" LED monitor**  
  We used a 24 inch LED monitor from LVC. But any monitor with a HDMI input will work!
  
* **two way mirror glass**  
  The glass is custom made and has a translucency of about 35%. The borders of the mirror are opaque.  
  The Technical drawing for this glass can be downloaded above (two-way mirror.PDF).  
  **PAY ATTENTION:** the dimensions of the glass are based on the LED monitor we use! Be sure to adjust them to your monitor.
 
* **aluminium backplate**  
  The backplate is custom made, the technical drawing and production files can be downloaded above in the Aluminium backplate folder.  
    It has multiple purposes as mentioned before, here is a detailed list:    
  - Concealment for the wires and electronics like the Raspberry Pi, infrared sensors, motion sensor, power supply, connector board
  - Easy wall mounting in landscape or portrait orientation
  - Brackets with threaded holes, so you can customize the sides of your mirror in any material like wood, metal, plastic….. Max. thickness of the material should be: 10mm.
    Check out the picture below for an example with lasercut plywood of 6mm thick with a side finish. The lasercut files are also available for download above.
  
* **connector PCB**  
This is a custom designed PCB that extends some of the GPIO pins of the Raspberry Pi. The production files and schematic can be downloaded above in the Connector PCB folder.
This board allows you to easily connect the infrared sensors, motion sensor and safely power LED strips without
the need of soldering, and blowing up your Raspberry Pi.

* **IR sensors**  
  The IR sensors are used to swipe between pages, these are also mounted onto the backplate

* **PIR sensor**  
  The motion sensor or PIR sensor detects if there is any movement within its range. If so, the mirror will turn on. This is also mountable on the backplate.

* **power supply**  
We've used an power supply from AUKEY. It has 5X USB 3.0 ports with quick charge function, to power up the Raspberry Pi and the LED
strips. There are 3 spare USB ports.
  This Power supply is also integrated in the back plate, but any decent power supply will work.
  
* **open source-software "MagicMirror²"**
  More information about this software can be found here: ([MagicMirrorsoftware](https://magicmirror.builders/))

### Level of difficulty: Intermediate

## MATERIALS

### Ingredients:
* Raspberry Pi 3B/B+ or 4B set, which can be found in the [Whadda PI4SET](https://www.whadda.com/product/raspberry-pi-4-2gb-starter-kit-pi4set/)
    - Raspberry Pi (3B/B+ or 4B)
    - \>= 8 GB MicroSD Card
* 24" monitor with HDMI input
* Two way mirror glass
* Aluminium Backplate
* [IR sensor (VMA330)](https://whadda.com/product/ir-obstacle-avoidance-sensor-module-vma330/)
* [PIR motion sensor (WPSE314)](https://whadda.com/product/pir-motion-sensor-wpse314/)
* Sensor Cables 650mm (x3)
* USB A - Micro USB cable (min. 50cm long)
* USB A - USB C cable (min. 50cm long)
* Connector PCB
* [OPTIONAL] LED strip assembly
* Cable ties (x20)
* Aukey Power adaptor
* Power cord to C13
* Splitter cord C14 TO C5 & C7
* Bolts
   - M2X14 (x2)
   - M2.5x8 (x10)
   - M2.5x5.5 (x2)
   - M4x10 (x4)
* 40-PIN ribbon cable Female- Female
* HDMI - HDMI cable (short as possible, we used 30cm long one)
* Plastic spacer 5mm height M3 (x12)
* Strong double sided tape

### Tools:
  - USB Keyboard
  - USB Mouse
  - Internet connection (WiFi or wired ethernet)

## PROGRAMMING  the development board

### Dev board: Raspberry Pi (3B/B+, 4B)

### Code language: Javascript, CSS

### Difficulty: Intermediate

### Programming the Rasberry Pi

To install the software onto your Raspberry Pi easily, We've made an image file, that contains Raspbian (the standard Raspberry Pi OS) and the MagicMirror software with a variety of fun modules already installed. See the pictures below to discover how we designed the interface.

#### The front Page 
It Shows the Date/time, daily news from over the world, Belgium holidays( can be changed to any country), different time zones.... When powering up the PI, u should see this.
![UI1](./pictures/Page1.png)

#### Page 2 
The "SPACE" page. It shows various information about past en future space travels, LIVE ISS footage, current moonphase.... 
![UI2](./pictures/Page2.png)

##### Page 3 
Displays Reddit gaming topics, featured games, A qoute of the day and a new coctail every day!
![UI3](./pictures/Page3.png)

##### Page 4 
Connect your phone/tablet using screen mirroring
![UI4](./pictures/Page4.png)

### To install our image on your SD card (**MIN. 8GB**) follow the steps below.

#### 1. Installing Raspberry Pi Imager

To burn the image on an SD card, we wil need a software to do this. Download Raspberry [RPi imager](https://www.raspberrypi.org/software/). Then run the installer and follow the prompts to complete the setup.
![IMG1](./pictures/Imager1.PNG)

#### 2. Downloading the Image

Download the SmartMirror.img file above (5.6GB). As mentioned before, you will need an SD card with a minimum storage of 8GB.

#### 3. Formating your SD card

before we can burn the image file, you will have to format the SD card. ATTENTION, this will delete all the files on the SD card.

* Plug your SD card in the computer. 
* Wipe it by right clicking on the drive, then choose format.
  ![FRMT1](./pictures/Format1.PNG)
* Under file System, choose NTFS. the rest should be good by default.
  ![FRMT2](./pictures/Format2.PNG)

#### 3. Burning the Image

* Open the Raspberry Pi Imager
* **Click** CHOOSE OS and then select **USE CUSTOM** 
![IMG2](./pictures/Imager2.PNG)
* Navigate and select the SmartMirror.img file you just downloaded 
![IMG3](./pictures/Imager3.PNG)
* Now **click** storage and choose the SD card we formatted earlier. 
![IMG4](./pictures/Imager4.PNG)
* Its time to WRITE the image, this will take several minutes..... 
![IMG5](./pictures/Imager5.PNG)

# Assembling the Smart Mirror

Now that you have the software installed, and know all the necessary information about the parts, it is time to start making the smart mirror. This will probably take up to 2 hours (when you have all parts already).

WE WILL ASSEMBLE A HORIZONTAL VERSION OF THE SMART MIRROR. As metioned before, the backplate is designed to hang horizontal or vertical.

## MOUNTING  THE ELECTRONICS ON THE ALUMINIUM BACK PLATE

#### 1. Place the ALUMINIUM BACK PLATE on its flat side.

![Plate](./pictures/1.jpg)

#### 2. The first things we will mount are the IR SENSORS. Collect them, together with 2x SPACERS and 2x M2.5x8 BOLTS.
![IR+Spacerr](./pictures/2.jpg)

#### 3. Place the SPACER over the hole in the bottom left of the BACK PLATE.
![SPACER+MOUNT](./pictures/3.jpg)

#### 4. Place the IR SENSOR on the SPACER as shown in the picture below. Allign the hole from the IR SENSOR with the hole from the SPACER and the BACK PLATE.
![SPACER+IR+MOUNT](./pictures/4.jpg)

#### 5. Screw the M2.5x8 BOLT into place.
![SSCREWIR1](./pictures/5.jpg)

#### 6. Repeat the last 3 steps for the IR sensor at the bottom right of the BACK PLATE.
![SSCREWIR2](./pictures/6.jpg)

#### 7. You should now be at this point:
![point1](./pictures/7.jpg)

#### 8. Now take the PIR SENSOR and the 2x M2x14 BOLTS.
![PIR](./pictures/8.jpg)

#### 9. Place the PIR sensor on the bottom "lip" of the BACK PLATE and screw it into place. ATTETTION: IF YOU WANT TO MOUNT IT VERTICAL, PLACE THE PIR SENSOR ON THE LEFT "LIP".
![PIRscrew1](./pictures/9.jpg)

#### 10. Screw the other BOLT into place.
![PIRscrew2](./pictures/10.jpg)

#### 11. Take the aukey POWER SUPPLY (any decent power supply will work, but the BACK PLATE is designed with this one).
![AUKEY](./pictures/11.jpg)

#### 11. Place the POWER SUPPLY in the slot of the BACK PLATE as shown in the pictures below. NOTE THE ORIENTATION!
![AUKEYM1](./pictures/12.jpg)
![AUKEYM2](./pictures/13.jpg)

#### 11. Tighten the power supply with 2x M2.5x5.5 BOLTS.
![AUKEYM3](./pictures/14.jpg)

#### 12. Take the cable assemblies. As mentioned earlier, you can make these yourself easily.
![Cable](./pictures/15.jpg)

#### 13. Connect the cables to the 2 IR SENSORS and PIR sensor as shown in the picture below (see connection diagram for connections).
![CableConnect](./pictures/16.jpg)

#### 14. Place a zip tie around the cable of the left IR SENSOR. Then cut off the excess with cut pliers.
![Zip1](./pictures/17.jpg)
![Zip2](./pictures/18.jpg)

#### 15. Grab your RPI, the 4x SPACERS and the 4x M2.5x8 BOLTS.
![RPI](./pictures/19.jpg)

#### 16. Place the SPACERS onto the 4 holes (sligtly on the left of the bottom middle) of the BACKPLATE.
![RPISpacers](./pictures/20.jpg)

#### 17. Place the RPI on the SPACERS, allign the holes from the RPI with the holes from the SPACERS and the BACK PLATE.
![RPIMOUNT](./pictures/21.jpg)

#### 17. Thighten the RPI with 4x M2.5x8 BOLTS.
![RPIScrew1](./pictures/22.jpg)
![RPIScrew2](./pictures/23.jpg)

#### 18. Place a zip tie around the cable of the PIR SENSOR. Don't forget to cut off the excess material.
![PIRZIP](./pictures/24.jpg)
![PIRZIP2](./pictures/25.jpg)

#### 19. Now place zip ties around the PIR and IR SENSOR CABBLES as shown in the picture below.
![PIRZIP3](./pictures/26.jpg)
![PIRZIP4](./pictures/27.jpg)

#### 20. Take the CONNECTOR BOARD, 4x SPACERS and 4X M2,5X8 BOLTS.
![CB](./pictures/28.jpg)

#### 21. Place the SPACERS onto the 4 holes (sligtly on the right of the bottom middle) of the BACKPLATE.
![CBspacers](./pictures/29.jpg)

#### 22. Place the CONNECTOR BOARD on the SPACERS. Again, allign the holes from the CONNECTOR BOARD with the holes from the SPACERS and the BACK PLATE.
![CBMOUNT](./pictures/30.jpg)

#### 23. Tighten the CONNECTOR BOARD with the 4x M2.5x8 BOLTS.
![CBMOUNT2](./pictures/31.jpg)

#### 24. Connect the LEFT IR SENSOR and PIR SENSOR to the connector board. (Check out the connection diagram)
![CBCONNECT1](./pictures/32.jpg)

#### 25. Secure the CABLES from the RIGHT IR SENSOR with 2 ZIP TIES on the BACK PLATE, as shown in the picture below.
![CABLERIGHTIR](./pictures/33.jpg)

#### 26. Take the UBS A - MICRO USB CABLE (USB A - USB C if u use a RPI4).
![MicroUSB](./pictures/34.jpg)

#### 27. Connect the Micro USB to the RPI.
![RPIconnect](./pictures/35.jpg)

#### 28. Secure the USB A - MICRO USB CABLE and the cable from the LEFT IR sensor with a zip tie.
![usBZip](./pictures/36.jpg)

#### 29. Then secure the rest of the USB A - MICRO USB cable with 2 zip ties as shown in the picture below.
![USBzip2](./pictures/37.jpg)

#### 30. Take your USB A- USB C CABLE and connect it to the CONNECTOR BOARD.
![CBUSB](./pictures/38.jpg)

#### 31. Secure the USB A - USB C CABLE with 2 zip ties as shown in the picture below. Do not secure the others yet!
![USBCzip1](./pictures/39.jpg)
![USBCzip2](./pictures/40.jpg)

#### 32. Connect the USB A - USB C CABLE to the power supply. Roll up the excess of the cable (CABLE MANAGEMENT is important!).
![PowerConnect1](./pictures/41.jpg)

#### 33. Now connect the USB A - MICRO USB CABLE to the power supply. Again, roll up the excess of the cable.
![Cpowerconnect2](./pictures/42.jpg)

#### 34. Secure the 2 USB cables with zip ties.
![USBZip](./pictures/43.jpg)
![USBZip2](./pictures/44.jpg)

#### 35. You should be at this point right now.
![POINT2](./pictures/45.jpg)

#### 36. Take the POWER - C13 CORD, and the C14 to C5 and C7 SPLITTER CORD.
![SplitterCord](./pictures/46.jpg)

#### 37. Connect the POWER CORDS C13 to the C14 of the SPLITTER CORD.
![SplitterCord2](./pictures/47.jpg)
![SplitterCord3](./pictures/48.jpg)

#### 38. Place the cable assembly on the backplate as shown in the picture below. Pay attention to the orrientatien (the SPLITTER CORD needs to be upwards).
![SplitterCord4](./pictures/49.jpg)

#### 39. Then secure it with zip ties!
![SplitterCord5](./pictures/50.jpg)
![SplitterCord6](./pictures/51.jpg)

#### 40. The project should look like this by now.
![point3](./pictures/52.jpg)

#### 41. Secure the C5 cable end from the splitter cord with a zip tie like in the picture below.
![C5](./pictures/53.jpg)

#### 42. Connect the C7 CABLE end from the splitter cord to the power supply.
![C7](./pictures/54.jpg)

#### 43.Secure the C7 CABLE end with zip ties.
![C7ZIP1](./pictures/55.jpg)
![C7ZIP2](./pictures/56.jpg)

#### 44. Take your 40PIN RIBBON CABLE, and connect it to the CONNECTOR BOARD. Note the orientation of the RIBBON CABLE!
![RIBBON1](./pictures/57.jpg)

#### 45. Connect the other end of the RIBBON CABLE tot the RPi. Fold the RIBBON CABLE like in the picture below!
![CRIBBON2](./pictures/58.jpg)

#### 46. Take your HDMI - HDMI CABLE. (If you are using a RPi 4 this wil be MICRO HDMI - HDMI).
![HDMI](./pictures/59.jpg)

#### 47. Connect the HDMI CABLE to your RPi.
![HDMICONNECT](./pictures/60.jpg)

#### 48. All the electronics are now mounted on the BACK PLATE. Everything should look like this:
![POINT4](./pictures/61.jpg)

## MOUNTING THE BACK PLATE ONTO THE MONITOR

#### 1. Place the MONITOR WITH MIRRORGLASS in front of you, faced down. BE CAREFUL TO NOT SCRATCH THE MIRROR GLASS: Put something underneath it like a blanket or some foam!
![Monitor](./pictures/62.jpg)

#### 2.(OPTIONAL) stick the LED STRIP ASSEMBLY on the back of the glass. PAY ATTENTION TO WHERE THE CONNECTOR IS LOCATED!
![Ledstrip](./pictures/63.jpg)

#### 3. Place the BACKPLATE under the MONITOR/MIRRORGLASS ASSEMBLY, note the orientation!
![MountMirror1](./pictures/64.jpg)

#### 4. Plug in the HDMI cable to the MONITORS HDMI PORT.
![MountMirror2](./pictures/65.jpg)

#### 5. (OPTIONAL) Plug in the LED STRIP ASSEMBLY to the CONNECTOR BOARD.
![MountMirror3](./pictures/66.jpg)

#### 6. Carefully turn the BACK PLATE on the monitor, make sure the C5 CONNECTOR is still accessible.
![MountMirror4](./pictures/67.jpg)

#### 7. Plug in the C5 CONNECTOR to the MONITORS POWER INPUT
![MountMirror5](./pictures/68.jpg)

#### 8. Now align the holes of the BACK PLATE with the mounting holes of the MONITOR.
![MountMirror6](./pictures/69.jpg)

#### 9. Now fasten it with 4X M4X10 BOLTS.
![MountMirror7](./pictures/70.jpg)

#### 10. The project should look like this:
![MountMirror8](./pictures/71.jpg)
![MountMirror9](./pictures/72.jpg)

### MOUNTING THE SIDE FINISHES OF THE SMART MIRROR

As metioned earlier, u can customize the sides of your mirror with any material you like that has a maximum thickness of 10 mm. We did it with 6mm thick lasercutted OKOUMÉ wood. The Lasercut files can be downloaded in the main brach of this project. 

The 8 brackets (2 on each sdie) on the BACKPLATE that will hold the side plates are threaded with M4 thread. so you will need 8 M4 bolts. The length of these bolts depends on the thickness from the material you are going to use.

HORIZONTAL/VERTICAL side plates: depending on which orientation you have chosen to hang up the mirror, there are different side plates.
RED RECTANGLE: VERTICAL MOUNT
BLUE RECTANGLE: HORIZONTAL MOUNT
![Sidefinish](./pictures/73.jpg)

#### 1. Take 8 x M4 BOLTS. As metioned earlier, the lentgh depends on the tickness of your side plates. We used M4x12.
![Bolts](./pictures/74.jpg)

#### 2. Screw the BOLTS into place as shown in the pictures below, each side plate will require 2 BOLTS
![Bolts](./pictures/75.jpg)
![Bolts](./pictures/76.jpg)
![Bolts](./pictures/77.jpg)
![Bolts](./pictures/78.jpg)
![Bolts](./pictures/79.jpg)

