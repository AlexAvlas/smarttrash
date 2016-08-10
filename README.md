# Smart Trash Can with IOTIFY & IBM IoT Framework

This is the accompanying source code for [this](https://blog.iotify.io/monitor-your-trash-can-with-iotify-ibm-iot-framework/) IOTIFY documentation.

This project is an IoT enabled Smart Trash Can which can update users about its current level through a mobile app and also notify via SMS in case the level breaches a critical point. It uses IBM's IoT Platform to enable MQTT based messaging between the Trash can and mobile app. 

#Overview
Mobile app which is used to display the current level of filled trash inside the can. The trash can is powered by IOTIFY's raspberry pi simulator and has a ultrasonic sensor which is used to sense the level.  The hardware connection between Raspberry Pi and ultrasonic sensor is as per the IOTIFY TrasnCan project description.




# [Pre Req](#pre-requisites)
You will have to add some configuration settings to make the application work with IBM IoT platform service and Twilio messaging.
These configurations are to be done as variables, which are already defined in the trash can's application code under [Trashcan.py](https://github.com/iotify/smarttrash/blob/master/Trashcan.py).

Edit the variables in the following lines as follows 

          Variable name       Line no.           Description

          account_sid         23                 Twilio account SID

          auth_token          24                 Twilio account authToken
          
          twilionumber        28                 Twilio Number ( Your Twilio subscribed number)
          
          receivernumber      29                 Twilio verified number (where you want to receive the SMS notifications). 
                                                 Should have country code, for example +18458892405

          organization        182                IBM account organization ID

          authKey             189                Generated API key

          authToken	      190                Generated Authentication token

# [Mobile App Configuration](#mobile-app-config)
The IBM IoT platform configurations has to be done in the mobile app as well, since the mobile app is also registered as a device instance for receiving the readings published by the trash can.

Edit the line numbers in [index.js](https://github.com/iotify/smarttrash/blob/master/TrashCanApp/www/js/index.js)

          Variable Name        Line no.            Description

          org                  55                  IBM account organization ID

          auth-key             60                  Generated API key	

          auth-token           61                  Generated authentication token  


# [Steps to Build the Mobile App](#mobile-app-build)

For building the mobile app, please refer to the official Cordova & Android documentation to setup the build dependencies. You will have to setup a build system with the dependencies, primarily the NodeJS, Java and Ant among others. 

Follow the steps below to build the APK file for the mobile app. All these steps are to be performed on the build system. These steps have been verified on a build system with Ubuntu mate OS along with Android version 23 & Cordova 6.3.0

Step 1: Clone this repository and run the following commands from within the repository to pull the submodules from https://github.com/ibm-watson-iot/iot-nodejs to get the nodejs sdk for the IBM IoT platform.

	git submodule init
	git submodule update

Step 2: Add the android platform by executing this command in the terminal under the app root folder ( TrashCanApp)

		cordova platform add android
		
Step 3:	In the config.xml file in the root folder change the name of the app to the name you want. This is optional step. By default the app name is "Trash Can"

Step 4: Build the app by executing the following command in the terminal in the root folder of the cordova app
          
          cordova build android

Step 5: Once build is successful, you can find the generated apk file in the following path relative to the cordova project root directory.
	
		/platforms/android/build/outputs/apk
			




