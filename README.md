# DESIGN-AND-DEVELOPMENT-OF-VIRTUAL-BUTTONS-USING-UNITY-TO-CONTROL-HOME-APPLIANCES
AR Interface Development: The AR application is developed in Unity3D. The Vuforia SDK is integrated to enable image target recognition. Virtual buttons are created and positioned on the image target within the Unity3D workspace.
C# Script for Button Interaction: A C# script is developed within the Unity3D project. This script handles user interaction with the virtual buttons. When a user presses a virtual button on the AR interface, the script retrieves the corresponding URL (defined in the code snippet you provided) associated with turning the appliance on or off.
Communication with Blynk Server:  The C# script initiates a 'Get' request using the UnityWebRequest library, sending the retrieved URL to the Blynk server. This URL triggers a predefined action on the Blynk server.
Blynk Server and ESP32 communication:  The Blynk server receives the request from the AR interface and forwards it to the ESP32 module using the defined authentication token.

ESP32 Code and Appliance Control: The ESP32 code, written in Arduino IDE, is uploaded to the microcontroller. It continuously monitors the Blynk server for incoming messages. Upon receiving a message from the Blynk server, the ESP32 code parses the message and extracts the control signal (on/off). The ESP32 then controls the connected appliance through the relay based on the received signal.

Code Explanation:
The provided code snippets demonstrate the functionalities of the C# script (Unity3D) and the Arduino IDE code for the ESP32 module.

C# Script:
Vb_on and Vb_off are references to the virtual button objects in the Unity3D scene.
url_on and url_off store the URLs associated with turning the appliance on and off, respectively. These URLs likely trigger virtual pin actions within the Blynk app.
GetRequest function initiates a web request to the Blynk server using the provided URL.
OnButtonPressed_on and OnButtonPressed_off functions are called when the corresponding virtual buttons are pressed. These functions trigger the GetRequest function with the appropriate URL based on the button pressed.

Arduino IDE Code:
The code includes libraries for WiFi communication, Blynk integration, and pin control.
relay variable defines the pin connected to the relay that controls the appliance.
auth stores the Blynk authentication token for secure communication.
ssid and pass define the WiFi network credentials for the ESP32 module.

Compiler Arduino IDE Code
4. Implementation
This section details the steps involved in setting up and deploying the proposed AR-based smart home appliance control system.

AR Interface Development:
Download and install Unity3D game engine (https://unity.com/download).
Install the Vuforia SDK within Unity3D following the official documentation (https://developer.vuforia.com/library/).
Create a new Unity3D project and import the Vuforia package.

Connecting Vuforia in Unity
Design the AR interface using 3D modeling tools within Unity 3D.
Integrate the Vuforia SDK to define an image target. This image target will be used to trigger the overlay of virtual buttons when viewed through the smartphone/tablet camera.
Create virtual buttons and position them on the image target within the Unity3D workspace.

C# Script Development:
Within the Unity3D project, create a new C# script file.
Implement the functionalities described in Section 3.4 (C# Script for Button Interaction). This script should handle user interaction with the virtual buttons, retrieve URLs based on button presses, and initiate communication with the Blynk server using UnityWebRequest.

#c code
4.2 Hardware Setup
ESP32 Microcontroller Setup:
Obtain an ESP32 microcontroller board.
Install the Arduino IDE software (https://www.arduino.cc/).
Install the necessary libraries for WiFi communication, Blynk integration, and pin control according to the ESP32 board specifications.
Connect the ESP32 board to your computer using a USB cable.

Relay and Appliance Connection:
Connect a relay module to the ESP32 board based on its pin configuration.
Wire the relay's output to the appliance you want to control (ensure compatibility based on voltage and current requirements).

Image Target Printing:
Print a copy of the image target defined within the Unity3D project. This image will be used by the Vuforia SDK to trigger the AR interface overlay.

Image Target

4.3 Blynk Configuration
Download and install the Blynk app on your smartphone or tablet.
Create a new Blynk project within the app.
Configure virtual buttons within the Blynk app. These buttons will correspond to the virtual buttons displayed in the AR interface.
Assign actions to the virtual buttons in the Blynk app. These actions can be sending a specific value (e.g., 1 for on, 0 for off) to a virtual pin.
Obtain the Blynk authentication token from the Blynk app settings. This token will be used in the ESP32 code for secure communication.

![IMG_20240318_173734](https://github.com/UPHARISH24/DESIGN-AND-DEVELOPMENT-OF-VIRTUAL-BUTTONS-USING-UNITY-TO-CONTROL-HOME-APPLIANCES/assets/160720153/c784cf8b-4b72-4f15-a28c-4194a330d9af)
![IMG_20240318_173008](https://github.com/UPHARISH24/DESIGN-AND-DEVELOPMENT-OF-VIRTUAL-BUTTONS-USING-UNITY-TO-CONTROL-HOME-APPLIANCES/assets/160720153/15d1be0e-617c-4097-84f9-0bd94ee76f2a)
![Screenshot 2024-02-28 212517](https://github.com/UPHARISH24/DESIGN-AND-DEVELOPMENT-OF-VIRTUAL-BUTTONS-USING-UNITY-TO-CONTROL-HOME-APPLIANCES/assets/160720153/e0d5acbd-a029-4733-931a-b11712ec39a7)
![Screenshot 2024-02-28 212901](https://github.com/UPHARISH24/DESIGN-AND-DEVELOPMENT-OF-VIRTUAL-BUTTONS-USING-UNITY-TO-CONTROL-HOME-APPLIANCES/assets/160720153/e35a88e6-0cba-480b-98be-bcb70252975f)
