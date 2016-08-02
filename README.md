# Smart Trash Can with IBM IoT Framework

An IoT enabled Smart Trash Can which can update users about its current level through a mobile app and also notify via SMS in case the level breaches a critical point. It uses IBM's IoT Platform to enable MQTT based messaging between the Trasn can and mobile app. 

#Overview
Mobile app which is used to display the current level of filled trash inside the can. The trash can is powered by IOTIFY's raspberry pi simulator and has a ultrasonic sensor which is used to sense the level.  The hardware connection between Raspberry Pi and ultrasonic sensor is as per the IOTIFY TrasnCan project description.


#Pre Requisites

1. [IBM Id Bluemix Account](https://console.ng.bluemix.net/registration/) 
2. [Twillio Account](https://www.twilio.com/try-twilio)


#Steps to Build the Mobile App

For building the mobile app, please refer to the official cordova documentation to build the apk file which can then be installed on an android phone. The app source is located in [TrashCanApp](TrashCanApp} folder under this repo.


#Configuration for Trash Can Sensing Application

The application source for the Trash can sensing is built on python. Refer the file [TrashCan.py](TrashCan.py} under this repo.
Clone this repo within IOTIFY console and copy this file to another location from where you would like to run it. 
Open the file and make the following edits to configure IBM IOT and Twillio settings. 


#Run Trash Can Sensing Application on Raspberry Pi

Run this program by issuing the following command

          python TrashCan.py





#Test the Trash Can


