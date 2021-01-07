# Connecting LEGO SPIKE Prime to Vuforia Spatial Toolbox on Windows

**Estimated time to complete** 30 - 60 minutes

##  Requirements
1. LEGO SPIKE Prime Hub & LEGO build
2. LEGO Education product feedback pamphlet
3. LEGO Education SPIKE app
4. Computer with Bluetooth capabilities
5. Vuforia Spatial Toolbox compatible device
6. Vuforia Spatial Edge Server download from GitHub
7. Vuforia Spatial Toolbox app

## Suggested pre-requisites:
1. [What is Vuforia Spatial Toolbox?](https://youtu.be/k3uHFk1PAAM)
2. [Getting Started with the Vuforia Spatial Toolbox](https://spatialtoolbox.vuforia.com/docs/use)
3. [Using the Vuforia Spatial Toolbox](https://spatialtoolbox.vuforia.com/docs/use/using-the-app)
4. [Glossary of Spatial Tools](https://spatialtoolbox.vuforia.com/docs/use/spatial-tools)
5. [Spatial Programming](https://spatialtoolbox.vuforia.com/docs/use/spatial-programming)
6. [Logic Blocks](https://spatialtoolbox.vuforia.com/docs/use/spatial-programming/example-programs)
7. [Example Programs](https://spatialtoolbox.vuforia.com/docs/use/spatial-programming/example-programs)

## Preparing the LEGO Education SPIKE App.
The LEGO SPIKE Prime Hub needs to be connected to the LEGO Education SPIKE App. Open the app and become familiar with the capabilities of the LEGO SPIKE Prime. Learn how to connect it to Bluetooth with the beginning tutorials within the SPIKE app.

## Getting Started
This section details how to connect the SPIKE Prime to the Vuforia Spatial Edge Server to allow the SPIKE Prime to be controlled by the Vuforia Spatial Toolbox app.

## Image Target
A key part of using the Vuforia Spatial Toolbox is an image target. This allows the app to scan a predetermined image that will signal the server to display an AR overlay onto the physical world as viewed through a mobile device or tablet. For this project, the feedback pamphlet that comes in each LEGO SPIKE Prime box will be used as the image target. This image has already been preconfigured in the Vuforia Spatial Edge Server that has been downloaded. If the pamphlet is not accessible, save the image below as a standalone picture and print it out and use it as the image target.

## ![LEGO SPIKE Prime Pamphlet](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image001.jpg)

- If printing out the image is not an option, the pamphlet image will also scan ff the computer monitor
- Resources for creating new image targets are in the **Appendices and Additional Resources** PDF for this project.

## Connecting the LEGO SPIKE Prime Hub to a computer
When using a SPIKE Prime for the first time, it needs to be connected to a computer for it to be named, which plays a key part in connecting it to Vuforia Spatial Toolbox. This section will explain how to start the initial connection of the SPIKE Prime Hub.

1. Open the LEGO Education SPIKE app and click “New Project” to start a new project. Choose the “Word Blocks” option, even though there will not be any coding inside of this interface.
2. Click the “Connect” button at the top of the page and turn on the SPIKE Prime Hub.
## ![Connect Button](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image003.png)
3. Ensure that the computer has Bluetooth enabled and choose the “CONNECT VIA BLUETOOTH” option at the top right-hand corner of the pop-up window
4. Turn on the SPIKE Prime Hub
5. Hold down the Bluetooth button on the corner of the Hub until it starts beeping and lights up
    - Make sure that the SPIKE Prime Hub is within range of the computer, otherwise it will not be able to connect.
6. If the SPIKE Prime hub can connect to the computer, it will show up on the screen as a nearby Hub and will be recognized as a device by the computer    
    - If this is the first time that the Hub is connected to the app, a prompt will pop up so that it can be given a unique name
## ![Hub Screenshot](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image004.png)
7. Once the SPIKE Prime Hub has been connected successfully, close out of the SPIKE app to avoid interference when connecting with Vuforia Spatial Toolbox

## Connecting the LEGO SPIKE Prime to Vuforia Spatial Toolbox
The following steps will describe the procedure of connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox via the Bluetooth connection on a computer and the Vuforia Spatial Toolbox mobile app. All code will be run in the Command Prompt.

1. Turn on the LEGO SPIKE Prime if it is not already on
2. Click the Windows key on the keyboard and type in “Bluetooth” to go to Bluetooth and other devices settings. Ensure that Bluetooth is turned on and hold down the Bluetooth button on the LEGO SPIKE Prime until it is recognized by the computer. Pair the LEGO SPIKE Prime with the computer.
3. If the LEGO SPIKE Prime isn’t immediately visible, look under the “other devices” heading and scroll down.
4. Select the “Devices and Printers” link at the bottom or right side of Bluetooth and other devices.
5. Scroll through the devices and search for a device that starts with “LEGO Hub@...” right click on the device, and select “Properties”    
    - If the SPIKE Prime Hub does not show up as a Bluetooth device, ensure that Bluetooth enabled on the computer and that the Bluetooth button on the Hub has been pressed to prepare it for pairing
    - Also ensure that the LEGO SPIKE App has been closed and disconnected from the SPIKE Prime Hub
6. In the new Properties window, navigate into the tab for “Hardware”.
7. There should be a Device Function with the name “Standard Serial over Bluetooth Link”. The COM name in the parenthesis is the serial port for the SPIKE Prime, take note of this.
    ## ![Serial Port List](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4b-image006.png)
    
    #### Troubleshooting: 
    If this serial port cannot be found, open the LEGO Educational SPIKE app.
        - Unplug the LEGO SPIKE Prime from the computer if it is plugged in
        - Turn the SPIKE Prime off and then back on
        - Open a new project and select the “connect” button in the upper left-hand corner of the screen
        - Select “Connect via Bluetooth” in the upper right-hand corner of the window that pops up.
        - Follow the instructions from LEGO for Connecting via Bluetooth
        - Be sure to close the LEGO SPIKE Prime from the app after connecting. This will block communication with the server if not disconnected.
        - Repeat the steps above.

8. Open the serial.js document inside of the folder ```SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server/addons/Vuforia-spatial-robotic-addon/interfaces/SPIKE-Prime```    
    - Go to line 23 of serial.js and replace the serial port with the one that was just taken note of. The part of the line that has COMX, where X is the number of the serial port that was found above. For example, the code at line 23 that was used when making this tutorial was ```const port = new SerialPort('COM 6 ', {```, where ```COM 6``` is the port that the PTC hub is connected to.
    ## ![Serial Port List](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4b-image007.png)
9. Open a new Command Prompt and navigate to the vuforia-spatial-edge-server directory inside of SpatialToolbox-Windows-Interns by entering ```cd Documents/SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server```. If the _SpatialToolbox-Windows-Interns_ folder is not saved in the _Documents_ folder, replace _Documents_ in the code above with wthe acutal path to the _SpatialToolbox-Windows-Interns_ folder.
10. Type ```node -v``` to check which version of Node.js was installed and take note of the result.
11. Run ```npm install``` while in the _SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server_ directory
12. Navigate to the _Spatial Robotic Addon_ folder using ```cd addons/vuforia-spatial-robotic-addon``` while still in the _SpatialToolbox-Windows-Interns/vuforia- spatial-edge-server directory_ and run ```npm install``` again    
    - These two commands will install all necessary packages for this project    
    - If Node.js is a version other than v12.18.2, enter ```npm rebuild``` to get the folder to work with the current version of Node.js. The server will not start if the without doing this if Node is a version other than v12.18.2.
13. Enter ```cd ../../``` in the Command Prompt window to navigate to the _SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server_ directory
14. Run node server:
    - This should start the Vuforia Spatial Edge Server. 
    - Navigate to _localhost:8080_ into a web browser. 
    - If the page does not load, troubleshoot using the methods below. If it does load, it should look like this image:
    ## ![Edge Server](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image009.png)

    #### Troubleshooting: 
    - The LEGO SPIKE Prime will make a beep shortly after running node server and connecting for the first time. This indicates that everything was connected correctly.
    - If there is an error like the one below in the Command Prompt, it is okay. 
    ## ![Connection Error](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image011.png)

15. If the readout in the Command Prompt shows something like the image below, then the server is working! The last two lines in this image describe what type of instrument is connected to the SPIKE Prime and which port that they are in. For example, there is a motor connected to port A and B, with the location in the instrument array corresponding to the location of the port that instrument is attached to in the port array.
    ## ![Terminal readout](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image012.png)
    #### Troubleshooting: 
    - There is the possibility that there may be issues when starting the server. Most issues can be resolved by restarting either the SPIKE Prime or the Vuforia Spatial Edge Server (control key + c and node server again in Terminal).
    - If there are multiple error statements in the Terminal after running node server, like shown below, then the LEGO SPIKE Prime did not connect correctly. Restart the LEGO SPIKE Prime and confirm that the correct serial port is being used.
    ## ![Multiple errors](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image010.png)
    -  If there are errors in the Terminal that do not look like this, or localhost:8080 does not load in the browser, restart the Vuforia Spatial Edge Server by closing out of Terminal or typing control key + c and repeating the start up instructions.

16. Open the Vuforia Spatial Toolbox mobile app and point the camera at the image target. A light blue box should appear around the image target. If nothing seems to happen, try moving the camera/target or changing the lighting of the room. If the light blue box still isn’t visible, then restart the mobile app.
    ## ![Blue spatial target box](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image013.png)
    #### Troubleshooting:
    - The iPhone being used needs to be on the same Wi-Fi network as the computer being used to form a connection with the Vuforia Spatial Edge Server
    - If restarting still does not work, go into the settings tab in the Vuforia Spatial Toolbox app and go into Found Objects. Compare this list to the list of objects in the Vuforia Spatial Edge Server.
    - If objects are missing and the only thing showing up is “_WORLD_local”, then there was an issue connecting the app and the Vuforia Spatial Edge Server and the connection process will need to be restarted
    - If the list of objects looks like the one below, but all of the font is red, then the app was opened too quickly. Closing out and then reopening the app should solve the issue.
    ## ![Object list](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image015.png)

17. When in Programming Mode in the app, a node setup similar to one of the following should appear:
    ## ![Different node complexity levels](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image018.png)

18. Changes to complexity levels can be made within the Vuforia Spatial Edge Server.
    - Select “Manage Hardware Interfaces” from the home screen
    - Click the gear icon next to Spike-Prime interface to open up settings for the SPIKE Prime.
    - Change the setting called “spikeComplexity” by typing in one of the four options shown above **(all configurations should be typed in lower case letters).** For more information about the different nodes and omplexity levels, visit **Appendix D** in **Appendices and Additional Resources**
    - When changing complexities, the server will need to be restarted. Go back into Terminal and press control key + C to stop the server and then start the process again while running node server in the vuforia-spatial-edge-server directory.
    ## ![Edge Server Directory](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image020.png)

<-- Go back to [LEGO SPIKE Prime Hardware Build](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/3-LEGO-SPIKE-Prime-Build.md), or Continue to [Fast Fourier Transform Activity](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/5-FFT-Activity.md) -->
