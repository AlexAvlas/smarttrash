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


#[Steps to Build the Mobile App](#mobile-app-build)

For building the mobile app, please refer to the official Cordova & Android documentation to setup the build dependencies. 

Follow the steps below to build the APK file for the mobile app.

Step 1: Clone this repository https://github.com/ibm-watson-iot/iot-nodejs to get the nodejs sdk for the IBM IoT platform.

Step 2: Add this parent folder of the cloned repository folder in the [js](https://github.com/iotify/smarttrash/tree/master/TrashCanApp/www/js) folder.

Step 3: Edit [index.html](https://github.com/iotify/smarttrash/blob/master/TrashCanApp/www/index.html) file add this line
          
          -> "js/iot-nodejs/dist/iotf-client-bundle.js"

Step 4: To make nodejs package work work have to download the require.js program from the link below 

          -> http://requirejs.org/docs/download.html#requirejs
          
Step 5: Copy the require.js file under [js]((https://github.com/iotify/smarttrash/tree/master/TrashCanApp/www/js) folder.

Step 6: Add require.js file in the index.html
          -> "js/require.js"


Step 7: Create an empty folder and change directory to that.

          -> Create a cordova project using the command 

	          cordova create appname

Step 8: Add the app package in the folder [www](https://github.com/iotify/smarttrash/tree/master/TrashCanApp/www) in the newly created cordova app folder.

Step 9: Add the android platform by executing this command in the terminal

		cordova platform add android
		
Step 10:	In the config.xml file in the root folder change the name of the app to the name you want.

Step 11: Build the app by executing the following command in the terminal in the root folder of the cordova app
          
          cordova build android

Step 12: You can find the generated apk file in the file path
	
		/platforms/android/build/outputs/apk
			




