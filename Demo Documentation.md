
<div style="position: absolute; top: 0; right: 200;">
  <img width="50px" src="/images/Template/Interactionlab-Logo.png" alt="Interaction Lab Logo"/>
</div>

# Interaction Buttons - Chase game

**Version/Date: 02/12/2023

## Overview

The buttons were created for a master course and the intent was to deliver a new layer to an existing playground.
The buttons are made in such a way, that they can be used to create interactive games with the use of almost any programming language.

## Setup

Provide step-by-step instructions for setting up the device or project for a demo.

1. Download the demo.exe from the GitHub
2. Turn on the buttons with the slider
3. Stick the dongle in the computer
4. The display should say how many buttons/nodes are connected
5. If not all buttons are accounted for the configuration on the sd card does not match.
    - Make sure the configs match, otherwise, the buttons can not find each other.

## Usage

Explain how to use the device or project during the demo.

1. When the setup is done start the demo.exe file by double clicking
    - The program only works on windows devices, and not on University laptops. 
3. All buttons should turn purple
4. Double click one of the buttons to start the game
5. Keep on pressing the yellow button that moves around
6. After x amount of times, the buttons get a rainbow effect and play a song
7. You can reset the game by long pressing a button
8. You can check the battery level by long pressing the button on the dongle

## Troubleshooting

List common issues and their solutions related to the demo.

- **Issue 1**: Button turn yellow
    - **Solution**: Make sure the SD card is in the button
- **Issue 2**: Button keeps on flashing red
    - **Solution**: The config does not match with the other buttons. (It can not find the other buttons)
- **Issue 3**: Display tells the wrong node count
    - **Solution**: Press the button on the dongle
- **Issue 4**: Display is upside down
    - **Solution**: Double press the button on the dongle
- **Issue 5**: The exe file does not start
    - **Solution_1**: You are not using windows or your laptop blocks the file from starting (computer from the university). Use an other laptop
    - **Solution_2**: You have another program open that is connected to the dongle over serial. (Can be an other instance of the demo)

 
[detailed documentation](https://github.com/utwente-interaction-lab/Interaction-buttons/blob/main/Detailed%20Documentation.md)

**Max Pijnappel**

Interaction Lab footer 

## extra

To compile your own python code into a exe for demos use pyinstaller.
For example `pyinstaller --onefile --name demo .\Python_Serial_Example.py` can be used, depending on the name of you python file