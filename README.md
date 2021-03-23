# Raspberry Pi smart mirror

![POINT4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Rpi_smart_mirror2.jpg)

This project is a Raspberry Pi based two-way mirror with an electronic (in oure case: LED) display behind semi reflecting glass. 
The smart mirror allows you to swipe between various pages that display information like the latest news, the weatherforcast, your calender, live footage of the ISS, daily jokes, broadcasting.... and so much more!

In terms of software, we have chosen for the open-source ’MagicMirror²’ software that runs on an Raspberry Pi 2, 3B+ or 4B with Raspbian installed. 
This makes it very easy to customize the layout of your mirror (add, create, change different modules). 

The custom designed backplate allows you to: easily mount all the electronics, hang the mirror on the wall (landscape or portrait), and customize the sides of your mirror in any material like wood, metal, plastic.

## Specifications & features

Below, you can find the specs/features that you need to know before building this project!

## MATERIALS

![Ingredients](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Ingerdients.png)

### Ingredients:

1. **24" LED monitor**  
We used a 24 inch LED monitor from LVC. But any monitor with a HDMI input will work!

2. **Two way mirror glass**  
The glass is custom made and has a translucency of about 35%. The borders of the mirror are opaque. The Technical drawing for this glass can be downloaded here [Two-way mirror.pdf](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/Two-way%20mirror.pdf). A very nice and easy way to get some 2 way mirror glass is here: https://www.pyrasied.nl/en/product/spy-mirror/. You just have fill in your dimensions, and it will be shipped within a day.  
**PAY ATTENTION:** the dimensions of the glass are based on the LED monitor we use! Be sure to adjust them to your monitor.
  
3. **Aluminium backplate**  
The backplate is custom made, the technical drawing and production files can be downloaded Here: [Aluminium backplate files](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/tree/main/Aluminium%20Backplate). It has multiple purposes as mentioned before, here is a detailed list:    
  - Concealment for the wires and electronics like the Raspberry Pi, infrared sensors, motion sensor, power supply, connector board
  - Easy wall mounting in landscape or portrait orientation
  - Brackets with threaded holes, so you can customize the sides of your mirror in any material like wood, metal, plastic….. Max. thickness of the material should be: 10mm.
    Check out the picture below for an example with lasercut plywood of 6mm thick with a side finish. The lasercut files are also available for download above.
  
4. **Raspberry Pi 3B/B+ or 4B set**, which can be found in the [Whadda PI4SET](https://www.whadda.com/product/raspberry-pi-4-2gb-starter-kit-pi4set/)
    - Raspberry Pi (3B/B+ or 4B)
    - \>= 8 GB MicroSD Card
5. **Connector PCB**  
This is a custom designed PCB that extends some of the GPIO pins of the Raspberry Pi. The production files and schematic can be downloaded here: [Connector PCB Files](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/tree/main/Connector%20PCB) (If you search on google for a PCB manufacturer, upload the production files we provided, you will get an instant quote and in most cases it only takes a few days to make the actual PCB.) This board allows you to easily connect the infrared sensors, motion sensor and safely power LED strips without
the need of soldering, and blowing up your Raspberry Pi.

6. [**IR sensor (VMA330)**](https://whadda.com/product/ir-obstacle-avoidance-sensor-module-vma330/)  
The IR sensors are used to swipe between pages, these are also mounted onto the backplate

7. [**PIR motion sensor (WPSE314)**](https://whadda.com/product/pir-motion-sensor-wpse314/)  
The motion sensor or PIR sensor detects if there is any movement within its range. If so, the mirror will turn on. This is also mountable on the backplate.

8. **Aukey Power adaptor**  
We've used an power supply from AUKEY. It has 5X USB 3.0 ports with quick charge function, to power up the Raspberry Pi and the LED
strips (optional). There are 3 spare USB ports. This Power supply is also integrated in the back plate, but any decent power supply will work.

9. **USB A - USB C cable (min. 50cm long)**

10. **USB A - Micro USB cable (min. 50cm long)**

11. **Sensor Cables 650mm (x3)**  
These cables are used to connect the IR and PIR sensor to the Connector board. You can easily make them yourselfs! technical drawing can be downloaded here: [Sensor cables.pdf](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/Sensorcable.pdf)

12. **Power cord to C13**

13. **40-PIN ribbon cable Female- Female**

14. **Splitter cord C14 TO C5 & C7**

15. **HDMI - HDMI cable (short as possible, we used 30cm long one)**

16. **Bolts**
      - M2X14 (x2)
      - M2.5x8 (x10)
      - M2.5x5.5 (x2)
      - M4x10 (x4)

17. **Plastic spacer 5mm height M3 (x12)**

18. **Strong double sided tape**

19. **Cable ties (x20)**

20. **open source-software "MagicMirror²"**  
More information about this software can be found here: ([MagicMirrorsoftware](https://magicmirror.builders/))

21. **[OPTIONAL] LED strip assembly.**  
The technical drawing can also be downloaded here:[LED strip assembly](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/LED%20strip%20assembly.pdf)

22. **[OPTIONAL] Side Finishes.**  
You van customize the sides of your mirror with any material you like that has a maximum thickness of 10 mm. We did it with 6mm thick lasercutted OKOUMÉ wood. The Lasercut files can be downloaded here: [Side Finishes.pdf](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/SideFinishes-Lasercut.pdf)

### Tools:
  - USB Keyboardz
  - USB Mouse
  - Internet connection (WiFi or wired ethernet)
  - Hex keys
  - .....

## Programming the RasBerry Pi

To install the software onto your Raspberry Pi easily, we've made an image file that contains Raspbian (the standard Raspberry Pi OS) and the MagicMirror software with a variety of fun modules already installed. See the pictures below to discover how we designed the interface.

**The front Page** 
It Shows the Date/time, daily news from over the world, Belgium holidays( can be changed to any country), different time zones.... When powering up the PI, u should see this.
![UI1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Page1.png)

**Page 2** 
The "SPACE" page. It shows various information about past en future space travels, LIVE ISS footage, current moonphase.... 
![UI2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Page2.png)

**Page 3**
Displays Reddit gaming topics, featured games, A qoute of the day and a new coctail every day!
![UI3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Page3.png)

**Page 4** 
Connect your phone/tablet using screen mirroring
![UI4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Page4.png)

### installing the image on your SD card (**MIN. 8GB**)
If you like our interface, you can follow the steps below to install it on your Raspberry Pi.
Otherwise you can download a standard version of the [magicMirror software](https://magicmirror.builders/) and design your own interface! This is also very fun and easy to do! Just follow [this guide](https://docs.magicmirror.builders/).

1. Installing Raspberry Pi Imager

To burn the image on an SD card, we wil need a software to do this. Download the [Raspberry Pi Imager](https://www.raspberrypi.org/software/) here. Then run the installer and follow the prompts to complete the setup.
![IMG1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Imager1.PNG)

2. Downloading the Image

Download the SmartMirror.img file here (5.6GB). As mentioned before, you will need an SD card with a minimum storage of 8GB.

3. Formating your SD card

Before we can burn the image file, We will have to format the SD card. ATTENTION, this will delete all the files on the SD card.

* Plug your SD card in a computer. 
* On Windows, open File Explorer and right click on the drive, then choose format.

![FRMT1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Format1.PNG)

* Under file System, choose NTFS. the rest should be good by default. (you can give the SD-card a name in the `Volume label` textbox

![FRMT2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Format2.PNG)

4. Burning the Image

* Open the Raspberry Pi Imager
* **Click** CHOOSE OS and then select **USE CUSTOM** 
![IMG2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Imager2.PNG)
* Navigate and select the SmartMirror.img file you just downloaded 
![IMG3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Imager3.PNG)
* Now **click** storage and choose the SD card we formatted earlier. 
![IMG4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Imager4.PNG)
* Its time to WRITE the image, this will take several minutes..... 
![IMG5](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Imager5.PNG)

## Frst time setup

If everything went good in the steps above... you can mount the SD card into the pi and connect all of your peripherals (mouse, keyboard, monitor). Also plug in a network cable if you're planning to use a wired ethernet connection. Power up the pi by connecting it to the USB power supply adapter.

Now wait for it to boot up, this will take couple of minutes depending on what Pi you use. The MagicMirror software should also start automatically and you should see THE FRONT PAGE.  

For now we will just put some settings right, Follow the steps below:

1. Close the MagicMirror software (For Now)

 * Press `F11` on your keyboard (this will make the MagicMirror window smaller) 
 * then open the terminal with `CTRL + ALT + T`
 * Type `pm2 stop mm` this is the command to stop the MagicMirror Software 
![RPI1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI1.png)
     * other usefull commands are 
        * `pm2 restart mm` restarts the software
        * `pm2 logs mm` shows log files
        * `pm2 show mm` Shows proces information
     * If the keyboardlayout is wrong go to `Application menu (RPI logo top left corner) > Preferences > Keyboard and mouse` 
![RPI2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI2.png)
     * Then click `Keyboard layout` and select you country under the drop down menu. 
![RPI3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI3.png)

2. Connecting with WiFi

If you are going use an ehternet (UTP) cable you can skip this step.
otherwise you can connect to a Wifi acces point by Clicking on the 'connection icon' in the top right corner...
![RPI4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI4.png)

3. Horizontal or Vertical display

As mentioned before you can choose to hang the Mirror horizontally or vertically. If you are going to hang it horizontally you can skip this.
if you plan to hang it vertically, we will have to change the display orientation:
* open the terminal with `CTRL + ALT + T` and type ` sudo nano /boot/config.txt`
![RPI5](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI5.png)
* change the line `display_rotate=0` to `display_rotate=1`
![RPI6](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI6.png)
* Close and save the file wit `CTRL+X` then `Y` and press `ENTER` 
![RPI7](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI7.png)
* The changes only take effect after a reboot. In the terminal type `sudo reboot` and press `ENTER`
![RPI8](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI8.png)

### The MagicMirror configuration file

The config file controls some important features of your mirror, as well as the various modules. It is written in JavaScript, this language is very sensitive to syntax errors. for example a misplaced `{` or `}` and the software will not work...
The config file also contains a `modules` section that controls which modules are loaded and where they’re placed.

### Some things u need to know!
* The congif.js file is located in the file manager under `/home/pi/MagicMirror/Config`
![RPI9](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI9.png)
* at the top of the config.js file U can change the unit system: `metric or imperial`, language `en` (uses the official abbreviations) and the timeformat `12 or 24`.
![RPI10](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI10.png)
* We have divided the config file with the modules per page using brackets
![RPI11](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI11.png)
* In the example below u can see the configuration of the REDDIT module. 
![RPI12](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI12.png)
* Each module has its own github page with all the explanation about it here [3rd party modules GitHub](https://github.com/MichMich/MagicMirror/wiki/3rd-party-modules)
for example the Reddit module settings can u find here: [Reddit module](https://github.com/kjb085/MMM-Reddit)
![RPI13](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/RPI13.PNG)

# Assembling the Smart Mirror

Now that you have the software installed, and know all the necessary information about the parts, it is time to start making the smart mirror. This will probably take up to 2 hours (when you have all parts already).

WE WILL ASSEMBLE A HORIZONTAL VERSION OF THE SMART MIRROR. As metioned before, the backplate is designed to hang horizontal or vertical.  
The only difference between the horizontal and vertical way, is the location of the IR and PIR sensor on the backplate. Below and illustrarion.
**Landscape orientation sensors**
![LANDSCAPE ORIENTATION](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Landscape.jpg)
**Portrait orientation sensors**
![PORTRAIT ORIENTATION](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/Portrait.jpg)
## MOUNTING THE ELECTRONICS ON THE ALUMINIUM BACK PLATE

1. Place the ALUMINIUM BACK PLATE on its flat side.

![Plate](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/1.jpg)

2. The first things we will mount are the IR SENSORS. Collect them, together with 2x SPACERS and 2x M2.5x8 BOLTS.
![IR+Spacerr](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/2.jpg)

3. Place the SPACER over the hole in the bottom left of the BACK PLATE.
![SPACER+MOUNT](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/3.jpg)

4. Place the IR SENSOR on the SPACER as shown in the picture below. Allign the hole from the IR SENSOR with the hole from the SPACER and the BACK PLATE.
![SPACER+IR+MOUNT](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/4.jpg)

5. Screw the M2.5x8 BOLT into place.
![SSCREWIR1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/5.jpg)

6. Repeat the last 3 steps for the IR sensor at the bottom right of the BACK PLATE.
![SSCREWIR2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/6.jpg)

7. You should now be at this point:
![point1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/7.jpg)

8. Now take the PIR SENSOR and the 2x M2x14 BOLTS.
![PIR](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/8.jpg)

9. Place the PIR sensor on the bottom "lip" of the BACK PLATE and screw it into place. ATTETTION: IF YOU WANT TO MOUNT IT VERTICAL, PLACE THE PIR SENSOR ON THE LEFT "LIP".
![PIRscrew1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/9.jpg)

10. Screw the other BOLT into place.
![PIRscrew2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/10.jpg)

11. Take the aukey POWER SUPPLY (any decent power supply will work, but the BACK PLATE is designed with this one).
![AUKEY](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/11.jpg)

12. Place the POWER SUPPLY in the slot of the BACK PLATE as shown in the pictures below. NOTE THE ORIENTATION!
![AUKEYM1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/12.jpg)
![AUKEYM2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/13.jpg)

13. Tighten the power supply with 2x M2.5x5.5 BOLTS.
![AUKEYM3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/14.jpg)

14. Take the cable assemblies. As mentioned earlier, you can make these yourself easily.
![Cable](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/15.jpg)

15. Connect the cables to the 2 IR SENSORS and PIR sensor as shown in the picture below (see connection diagram for connections).
![CableConnect](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/16.jpg)

16. Place a zip tie around the cable of the left IR SENSOR. Then cut off the excess with cut pliers.
![Zip1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/17.jpg)
![Zip2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/18.jpg)

17. Grab your RPI, the 4x SPACERS and the 4x M2.5x8 BOLTS.
![RPI](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/19.jpg)

18. Place the SPACERS onto the 4 holes (sligtly on the left of the bottom middle) of the BACKPLATE.
![RPISpacers](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/20.jpg)

19. Place the RPI on the SPACERS, allign the holes from the RPI with the holes from the SPACERS and the BACK PLATE.
![RPIMOUNT](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/21.jpg)

20. Thighten the RPI with 4x M2.5x8 BOLTS.
![RPIScrew1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/22.jpg)
![RPIScrew2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/23.jpg)

21. Place a zip tie around the cable of the PIR SENSOR. Don't forget to cut off the excess material.
![PIRZIP](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/24.jpg)
![PIRZIP2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/25.jpg)

22. Now place zip ties around the PIR and IR SENSOR CABBLES as shown in the picture below.
![PIRZIP3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/26.jpg)
![PIRZIP4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/27.jpg)

23. Take the CONNECTOR BOARD, 4x SPACERS and 4X M2,5X8 BOLTS.
![CB](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/28.jpg)

24. Place the SPACERS onto the 4 holes (sligtly on the right of the bottom middle) of the BACKPLATE.
![CBspacers](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/29.jpg)

25. Place the CONNECTOR BOARD on the SPACERS. Again, allign the holes from the CONNECTOR BOARD with the holes from the SPACERS and the BACK PLATE.
![CBMOUNT](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/30.jpg)

26. Tighten the CONNECTOR BOARD with the 4x M2.5x8 BOLTS.
![CBMOUNT2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/31.jpg)

27. Connect the LEFT IR SENSOR and PIR SENSOR to the connector board. (Check out the connection diagram)
![CBCONNECT1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/32.jpg)

28. Secure the CABLES from the RIGHT IR SENSOR with 2 ZIP TIES on the BACK PLATE, as shown in the picture below.
![CABLERIGHTIR](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/33.jpg)

29. Take the UBS A - MICRO USB CABLE (USB A - USB C if u use a RPI4).
![MicroUSB](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/34.jpg)

30. Connect the Micro USB to the RPI.
![RPIconnect](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/35.jpg)

31. Secure the USB A - MICRO USB CABLE and the cable from the LEFT IR sensor with a zip tie.
![usBZip](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/36.jpg)

32. Then secure the rest of the USB A - MICRO USB cable with 2 zip ties as shown in the picture below.
![USBzip2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/37.jpg)

33. Take your USB A- USB C CABLE and connect it to the CONNECTOR BOARD.
![CBUSB](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/38.jpg)

34. Secure the USB A - USB C CABLE with 2 zip ties as shown in the picture below. Do not secure the others yet!
![USBCzip1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/39.jpg)
![USBCzip2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/40.jpg)

35. Connect the USB A - USB C CABLE to the power supply. Roll up the excess of the cable (CABLE MANAGEMENT is important!).
![PowerConnect1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/41.jpg)

36 Now connect the USB A - MICRO USB CABLE to the power supply. Again, roll up the excess of the cable.
![Cpowerconnect2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/42.jpg)

37 Secure the 2 USB cables with zip ties.
![USBZip](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/43.jpg)
![USBZip2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/44.jpg)

38. You should be at this point right now.
![POINT2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/45.jpg)

39. Take the POWER - C13 CORD, and the C14 to C5 and C7 SPLITTER CORD.
![SplitterCord](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/46.jpg)

40 Connect the POWER CORDS C13 to the C14 of the SPLITTER CORD.
![SplitterCord2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/47.jpg)
![SplitterCord3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/48.jpg)

41. Place the cable assembly on the backplate as shown in the picture below. Pay attention to the orrientatien (the SPLITTER CORD needs to be upwards).
![SplitterCord4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/49.jpg)

42. Then secure it with zip ties!
![SplitterCord5](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/50.jpg)
![SplitterCord6](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/51.jpg)

43. The project should look like this by now.
![point3](./pictures/52.jpg)

44. Secure the C5 cable end from the splitter cord with a zip tie like in the picture below.
![C5](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/53.jpg)

45. Connect the C7 CABLE end from the splitter cord to the power supply.
![C7](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/54.jpg)

46.Secure the C7 CABLE end with zip ties.
![C7ZIP1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/55.jpg)
![C7ZIP2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/56.jpg)

47. Take your 40PIN RIBBON CABLE, and connect it to the CONNECTOR BOARD. Note the orientation of the RIBBON CABLE!
![RIBBON1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/57.jpg)

48. Connect the other end of the RIBBON CABLE tot the RPi. Fold the RIBBON CABLE like in the picture below!
![CRIBBON2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/58.jpg)

49. Take your HDMI - HDMI CABLE. (If you are using a RPi 4 this wil be MICRO HDMI - HDMI).
![HDMI](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/59.jpg)

50. Connect the HDMI CABLE to your RPi.
![HDMICONNECT](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/60.jpg)

51. All the electronics are now mounted on the BACK PLATE. Everything should look like this:
![POINT4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/61.jpg)

## MOUNTING THE BACK PLATE ONTO THE MONITOR

1. Place the MONITOR WITH MIRRORGLASS in front of you, faced down. BE CAREFUL TO NOT SCRATCH THE MIRROR GLASS: Put something underneath it like a blanket or some foam!
![Monitor](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/62.jpg)

2.(OPTIONAL) stick the LED STRIP ASSEMBLY on the back of the glass. PAY ATTENTION TO WHERE THE CONNECTOR IS LOCATED!
![Ledstrip](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/63.jpg)

3. Place the BACKPLATE under the MONITOR/MIRRORGLASS ASSEMBLY, note the orientation!
![MountMirror1](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/64.jpg)

4. Plug in the HDMI cable to the MONITORS HDMI PORT.
![MountMirror2](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/65.jpg)

5. (OPTIONAL) Plug in the LED STRIP ASSEMBLY to the CONNECTOR BOARD.
![MountMirror3](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/66.jpg)

6. Carefully turn the BACK PLATE on the monitor, make sure the C5 CONNECTOR is still accessible.
![MountMirror4](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/67.jpg)

7. Plug in the C5 CONNECTOR to the MONITORS POWER INPUT
![MountMirror5](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/68.jpg)

8. Now align the holes of the BACK PLATE with the mounting holes of the MONITOR.
![MountMirror6](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/69.jpg)

9. Now fasten it with 4X M4X10 BOLTS.
![MountMirror7](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/70.jpg)

10. The project should look like this:
![MountMirror8](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/71.jpg)
![MountMirror9](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/72.jpg)

### MOUNTING THE SIDE FINISHES OF THE SMART MIRROR

As metioned earlier, u can customize the sides of your mirror with any material you like that has a maximum thickness of 10 mm. We did it with 6mm thick lasercutted OKOUMÉ wood. The Lasercut files can be downloaded in the main brach of this project. 

The 8 brackets (2 on each sdie) on the BACKPLATE that will hold the side plates are threaded with M4 thread. so you will need 8 M4 bolts. The length of these bolts depends on the thickness from the material you are going to use.

HORIZONTAL/VERTICAL side plates: depending on which orientation you have chosen to hang up the mirror, there are different side plates.  
RED RECTANGLE: VERTICAL MOUNT  
BLUE RECTANGLE: HORIZONTAL MOUNT
![Sidefinish](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/73.jpg)

1. Take 8 x M4 BOLTS. As metioned earlier, the lentgh depends on the tickness of your side plates. We used M4x12.
![Bolts](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/74.jpg)

2. Screw the BOLTS into place as shown in the pictures below, each side plate will require 2 BOLTS
![Bolts](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/75.jpg)
![Bolts](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/76.jpg)
![Bolts](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/77.jpg)
![Bolts](https://github.com/WhaddaMakers/RPi-smart-mirror-tutorial/blob/main/pictures/78.jpg)

