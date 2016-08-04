# Smart Trash Can with IOTIFY & IBM IoT Framework

This is the accompanying source code for [this](https://blog.iotify.io/monitor-your-trash-can-with-iotify-ibm-iot-framework/) blog post.

This project is an IoT enabled Smart Trash Can which can update users about its current level through a mobile app and also notify via SMS in case the level breaches a critical point. It uses IBM's IoT Platform to enable MQTT based messaging between the Trash can and mobile app. 

#Overview
Mobile app which is used to display the current level of filled trash inside the can. The trash can is powered by IOTIFY's raspberry pi simulator and has a ultrasonic sensor which is used to sense the level.  The hardware connection between Raspberry Pi and ultrasonic sensor is as per the IOTIFY TrasnCan project description.


#[Pre Requisites](#pre-requisites)

1. [IBM Id Bluemix Account](https://console.ng.bluemix.net/registration/) 
2. [Twillio Account](https://www.twilio.com/try-twilio)


#[Python Script Configuration](#python-script-config)
You will have to add some configuration settings to make the application work with IBM IoT platform service and Twilio messaging.
These configurations are to be done as variables, which are already defined in the trash can's application code under [Trashcan.py](https://github.com/iotify/smarttrash/blob/master/Trashcan.py).

Edit the variables in the following lines as follows 

          Variable name       Line no.           Description

          account_sid         23                 Twilio account SID

          auth_token          24                 Twilio account authToken

          organization        180                IBM account organization ID

          authKey             187                Generated API key

          authToken	          188                Generated Authentication token

#[Mobile App Configuration](#mobile-app-config)
The IBM IoT platform configurations has to be done in the mobile app as well, since the mobile app is also registered as a device instance for receiving the readings published by the trash can.

Edit the line numbers in [index.js](https://github.com/iotify/smarttrash/blob/master/TrashCanApp/www/js/index.js)

          Variable Name        Line no.            Description

          org                  55                  IBM account organization ID

          auth-key             60                  Generated API key	

          auth-token           61                  Generated authentication token  


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


