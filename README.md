# Smart Trash Can

An IoT enabled Smart Trash Can which can update users about its current level and also notify via email in case the level breaches a critical point. 

#Overview
This trash can is assisted by a mobile app which is used to check the current level of filled trash inside the can. The trash can is powered by raspberry pi b+ and has a ultrasonic sensor which is used to sense the level. The schematic diagram of the hardware setup is as follows.

![Schematic](https://github.com/iotify/smarttrash/blob/master/trashCan.png "Schematic")

#Steps to Build
1. There are three source folders for this project, app, rpi_client and server. "app" contains the mobile app, "rpi_client" contains the raspberry pi client side code and "Server" contains the server side code.
2. For building the mobile app, please refer to the official cordova documentation to build the apk file which can then be installed on an android phone. 
3. Transfer the rpi_client folder to raspberry pi and update the [config file](https://github.com/iotify/smarttrash/blob/master/rpi_client/config.ini) as per the configuration section below.
4. Transfer the server folder to a server having python environment and update the   [config file](https://github.com/iotify/smarttrash/blob/master/server/config.ini) as per the configuration section below.

#Configuration
1. Update the config file under "Server" folder to modify the parameters which are explained as follows

  - pub_key : PubNub publish key
  - sub_key : PubNub subscribe key
  - host_ip : IP of the server host machine
  - host_and_port : DNS host and port of the mail server
  - user_email_id : Email id of the sender 
  - user_password : Password of the sender
  - receiver_mail_id : Email of the receiver
  

2. Update the config file under "rpi_client" folder to modify the parameters which are explained as follows

  - trashcan_1 : ID of trash can ( can be left as default value)
  - mqtt_server_ip : IP address of the server hosting the MQTT broker
  - mqtt_server_port : Port number of MQTT
  - mqtt_channel : MQTT channel name ( can be left as default value)
  - mqtt_address : MQTT address ( can be left as  default value)

3. For sending email notification , if the sender's email service is GMail, then you need to enable a configuration under the Gmail account by visiting the following link

    -   https://www.google.com/settings/u/0/security/lesssecureapps
  
        Make sure that "Turn on" option is selected for the setting  "Access for less secure apps".

        For other email service providers, please check the respective documentation. 
 



#How to run
1. Setup the hardware as per the schematic diagram above
2. In the server, run the 'garbageServer.py' script to start the application on server.
3. In the raspberry pi , Run the 'garbageClient.py' script to start the application on the client.
4. Launch the app on a mobile phone and check the level.
5. Using an object, obstruct the ultrasonic sensor from a distance, to simulate the presence of trash at a certain level. Notice that , with every change in level, the level inicator on the app will get updated.
6. Bring the obstructing object very close to the sensor to simulate a full trash can scenario. In this case a notification email will be sent to the configured email id.

  



