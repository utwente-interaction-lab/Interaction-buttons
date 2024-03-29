Interaction-lab-eemcs@utwente.nl<div style="position: absolute; top: 0; right: 200;">
  <img width="50px" src="/images/Template/Interactionlab-Logo.png" alt="Interaction Lab Logo"/>
</div>

# Mesh enabled interaction buttons

**Version/Date: 04/11/2023**

## Table of Contents

- [Mesh enabled interaction buttons](#mesh-enabled-interaction-buttons)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Requirements](#requirements)
  - [Creation](#creation)
  - [Instructions](#instructions)
    - [Functions dongle](#functions-dongle)
  - [Creating a script](#creating-a-script)
  - [Commands](#commands)
  - [Screenshots](#screenshots)
  - [Code](#code)
  - [Conclusion](#conclusion)

## Introduction

The mesh-enabled interaction buttons allow you to easily make interactions that use buttons, lights and music with the use of any programming language you want.

## Requirements

List the hardware, software, and any other necessary resources required to complete the project.

- **Hardware**:
-   X amount of interaction buttons
-   1 mesh dongle 
- **Software**:
-   A programming language that supports sending data over a serial connection 

## Creation

The buttons were originally created for the course Experience Design for Interaction. 
The goal was to create a new layer to existing small playgrounds, to make it more fun for children to play there.
The buttons tried to solve this by hanging these buttons all around the playground. And with the use of these buttons create games like a capture the flag.
They were set up in a way where the buttons listened to basic commands via a mesh network, and sent when they were pressed.


## Instructions

Provide step-by-step instructions on how to set up and use the project. Include any troubleshooting tips or common issues that might arise.

- 1\. Make sure the buttons are configured to be in the same mesh, the setting for this can be changed with the use of an SD card. The following settings have to match.
    - MESH_SSID: This is the name of the mesh (you can see this with your phone), they have to match otherwise the buttons will be separate meshes.
    - MESH_PASSWORD: This is the password to connect to the mesh, if this is wrong it is not allowed to join the mesh.
    - WIFI_CHANNEL: These if to match otherwise they can not see each other at all
    - MESH_PORT: This determines on what port the buttons will listen to for commands, you can choose to mismatch these but not the settings above. For example of you want to meshes for sending commands, but you do want to make use of other buttons to expand the mesh (increase the range).   
- 2\. Turn on the buttons, they will start out blinking red, when to connect to a mesh it will blink green.
- 3\. Put the mesh dongle in your computer, the screen will turn on. When connected to the mesh it should show the amount of buttons that are connected to it.
- 4\. Run your script that creates the interactions. There is a Python example available.
    - If you stop the script the dongle reboots, make sure it is connected to the mesh before running the script again.

### Functions dongle
The dongle has a button on the underside, this button can do three things:

- Normal press: it refreshed the node list and the connected amount of buttons
- Double press: It will flip the screen, it can be upside down depending on what side the USB port is.
  - This state is remembered when the dongle is turned on again.
- Long press: Sets all connected buttons to Battery display mode
  - The actual values are also sent over the serial port. You can read these for example with the arduino ide or putty.


## Creating a script

-   1. To create a script for your interactions, choose a programming language of your choice and make sure it has the library installed for serial Communication (for Python this is PySerial).
    2. Set up the serial communication, set the baud rate to 115200 and select the right COM port. The device should be called 'USB Serial Device'.
    3. Listen to the serial communication so you can receive information from the mesh (list of the nodes connected, battery level and which button has been pressed)
    4. You can send commands in the following format ``nodeid:command:subcommand` ``, the backtick at the end is important.
 
## Commands
- To receive the list of all nodes connected to the mesh send ``Nodelist` ``. You will receive a list of all nodes starting with the id of the dongle. The ids are separated with a \.
- You can start with the word Broadcast, this means that the command will be sent to all nodes in the mesh. Or a specific node id received by sending the Nodelist command, the ids are also located on the buttons.
- After the part where you tell which buttons have to receive the command you can use the command and subcommand to tell it what to do. Below are all the available commands.

- `:Play:[song]` - This is how u play a song on a button. [song] has to be replaced with the name of a song u have put in the sounds folder of the SD card without the ".mp3".
- `:Rainbow` - This will put a rainbow effect on the button.
- `:Full:[color]` - This will put a solid color on the button. Replace [color] with one of the colors.
- `:Circle:[color]` - This will put a circle effect on the button in a color.
- `:Blink:[color]` - This will have the button blink a color.
- `:Clear` - Turns of the LEDs.
- `:Brightness` - With this, u can change the brightness of the button on a scale from 0 - 255.
- `:Volume` - With this u can change the volume of the speaker on a scale from 0-21.
- `:Battery:[subcommand]` - With this, u can get information about the battery.
  - `Percentage` - Gives the battery percentage over serial.
  - `Voltage` - Gives the battery voltage over serial.
  - `Show` - Gives back the battery voltage and percentage over serial, but also show the battery capacity with the LEDs. 

The following colors are available; Red, Blue, Green, Purple, Yellow, Orange, Cyan, Pink.

> **Note**: Add notes for specific instructions, such as searching folders or finding buttons.

## Screenshots

Include screenshots of the project in action, highlighting its key features and functionalities.

![Screenshot 1](\Pictures\Pictures/screenshot%20programm.png)
This is how to program looks when starting.

![Picture 1](\Pictures/Dongle.jpg) 
Picture of the dongle.

![Picture 2](\Pictures\Pictures/Button_Inside.jpg)
Picture of the inside of the buttons.

![Picture 3](\Pictures\Pictures/Button_on_off.jpg)
Picture of the buttons, one is of the other one is green



## Code

Include a link to the GitHub repository where the code for the project is stored. Provide instructions on how to access and modify the code.

- [GitHub Repository]([https://github.com/username/repository](https://github.com/utwente-interaction-lab/Bee-Buttons)) <!-- Replace with the actual repository URL -->

> **Note**: Explain any unusual code or code requirements here.

## Conclusion

The buttons will be tested in module 6 as a tool in the course. Besides this they might be used for graduations projects.
If any problems occur during those use cases, the functionality of the buttons might be extended.

The buttons as is work great on the software side and are easy to set up. This used to be complicated.
However due to same manufacturing error, there is only one set of buttons where the LEDs work correctly.
The other 2 sets have defective LEDs, they migh be replaced later.




Interaction Lab - [Website](https://example.com) <!-- Replace with the actual website URL -->
Interaction-lab-eemcs@utwente.nl<div style="position: absolute; top: 0; right: 200;">
  <img width="500px" src="/images/Template/Footer.png" alt="Interaction Lab Logo"/>
</div>
