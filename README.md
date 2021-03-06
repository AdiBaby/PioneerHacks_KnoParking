# KnoParking

Car Detection System. The entire system detects motion, sends pictures to a website, and (to be implemented) sends liscence plates to the website. Applicable to parking lots, garages, and driveways.

## Getting Started

The setup requires three things:

* A Raspberry Pi with a [Camera Module](https://www.raspberrypi.org/documentation/hardware/camera).
* A ESP8266 with a HCSR04 Motion Detector.
* A computer running the website.

### Prerequisites

The Raspberry Pi program will not run unless the terminal command `vcgencmd get_camera` returns `supported=1 detected=1`. If the return is `supported=0 detected=0`, the Raspberry Pi cannot use a Camera Module. If the return is `supported=1 detected=0`, follow the following steps:

1. Check to make sure ribbon of the camera is facing the right way, and is all the way in the connector slot. 
2. Check to make sure ribbon is in proper connector slot: the one between the ethernet port and the HDMI port.
3. Try enabling the camera interface in the config settings. Run `sudo apt-get update` and `sudo apt-get upgrade`. Then run `sudo raspi-config`. If the `camera` option doesn't appear, select the `Update` option, restart the raspberry pi, and then go back and  select the `Interfacing Options`, select `Camera`, and enable it. If it does appear, select `camera` and enable it, run `vcgencmd get_camera` again, and the camera should be detected.

For the ESP8266 Motion Detector, *to be added*.

For the website, *to be added*.

## Deployment

Point the camera of the Raspberry Pi in a direction so it can see the liscence plate, and the and the ESP8266 right above the space for the car. The Camera should hang from the ribbon so the ribbon is above the Camera. Download the contents of the Raspberry Pi folder on the Raspberry Pi. ls to the folder and do `java -cp ":jrpicam-1.1.1.jar:" CameraSender` to run the CameraSender.class file.

## Further Expansion

This program can be expanded to maintain a running memory of cars and their license plates in a parking lot. We plan on adding this as an extension to the project.

## Built With

* [JRPiCam](https://github.com/Hopding/JRPiCam), the Java version of the RPi Camera Modu API.

## Info

This program was used for PioneerHacks II 2019.

## Links

* [Devpost](https://devpost.com/software/knoparking) 
* [Adobe Spark](https://spark.adobe.com/page/TnMddVnVLV9Kn/) 

## Authors

* Aditya Prerepa - Server architecture, MySQL schema, push pull networking, Web Server Wrapper code.
* Akshay Trivedi - RPI image taking, image sending, networking assistance/backup/smart kid
* Ishan Jain - Web Design
