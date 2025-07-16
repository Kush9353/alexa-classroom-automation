# alexa-classroom-automation
Project Overview
The "Alexa Class Room Automation" project enables voice control over various electrical devices in a classroom, such as lights and fans. The system uses a NodeMCU ESP8266 board to control a 4-channel relay module, with each relay connected to a different appliance. The NodeMCU is linked to the Arduino IoT Cloud, allowing for remote control and integration with Amazon Alexa.



Core Components
The project utilizes a combination of hardware and software components:

Hardware:

NodeMCU ESP8266 with a micro-USB cable 

4-Channel Relay Module 

Jumper wires 

Devices to be controlled (connected via 2-pin sockets) 

Software & Services:

Arduino IDE 

ESP8266 board drivers for the Arduino IDE 

ArduinoIoTCloud library 

Arduino IoT Cloud account for device management and dashboard creation 

Amazon Alexa app and service for voice control 

System Architecture and Functionality
The system's architecture is centered around the NodeMCU, which acts as the main controller.


Hardware Connection: The NodeMCU's digital pins (D1, D2, D5, D6) are connected to the input pins of the 4-channel relay module. Each relay on the module then controls the power to a separate classroom appliance.




Cloud Connectivity: The NodeMCU is programmed using the Arduino IDE to connect to a Wi-Fi network. It then establishes a connection with the Arduino IoT Cloud using a unique device ID and secret key.






Cloud Configuration: Within the Arduino IoT Cloud, a "Thing" is created to represent the NodeMCU. Four "CloudSwitch" variables (

switch1, switch2, switch3, switch4) are set up and linked to this "Thing". These cloud variables are then used to create a dashboard with toggle switches for remote control.






Alexa Integration: The Arduino IoT Cloud is integrated with Amazon Alexa. This allows the cloud switches to be recognized as smart devices within the Alexa ecosystem.



Operation: A user can issue a voice command to an Alexa device (e.g., "Alexa, turn on device 1"). Alexa processes this command and communicates the change to the corresponding switch in the Arduino IoT Cloud. The cloud platform then relays this command to the connected NodeMCU. The NodeMCU's code, which continuously checks for updates from the cloud, receives the signal and triggers the appropriate relay (by setting the pin to LOW for ON or HIGH for OFF), thus turning the classroom appliance on or off. The changes are also reflected in the Arduino IoT Cloud dashboard.






Sources






