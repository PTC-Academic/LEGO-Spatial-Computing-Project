# Fast Fourier Transform Activity

**Estimated time to complete** 20 - 30 minutes

## Requirements
1. LEGO SPIKE Prime Hub & LEGO build
2. LEGO Education product feedback pamphlet
3. Computer with Bluetooth capabilities
4. Vuforia Spatial Toolbox compatible device
5. Vuforia Spatial Edge Server download from GitHub
6. Vuforia Spatial Toolbox app


## Getting Started
A Fast Fourier Transform (FFT) is a form of frequency analysis that takes a discrete signal in the time domain and transforms that signal into its discrete frequency
domain representation in order to find the primary frequency that the object is vibrating at. This frequency is important to know to avoid having an object vibrate at
its natural frequency, as that would cause potential failure in the object. In this activity, a Fast Fourier Transform analysis will be made on a LEGO SPIKE Prime
representation of a radial engine. The FFT analysis will be used to tell how many vibrations occur per second on the engine. This is important, as vibration analysis is used for predicting failure in rotating machinery. This activity will have students use the Vuforia Spatial Toolbox to trigger an FFT analysis on their LEGO SPIKE Prime and be able to visualize the number of vibrations per second on its motor while it is rotating.

## Changing the Hardware Interface

As mentioned in **Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox**, the setup of the nodes can be changed depending on need. In the case of this FFT
activity, the node setup needs to be in Advanced mode in order to do the necessary analysis.

1. Connect the SPIKE Prime to a computer via Bluetooth if not already connected
2. Open Terminal/Command Prompt and go to the vuforia-spatial-edge-server directory
   - Enter ```cd Documents/SpatialToolbox-Mac-Interns/vuforia-spatial-edge-server``` on MacOS
   - Enter ```cd Documents/SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server``` on Windows
3. Start the Vuforia Spatial Edge Server using the node server (Enter ```npm start```)
4. Type “localhost:8080” in a browser to view the server
    #### Troubleshooting:
   - For any troubleshooting issues, view the troubleshooting notes in the Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox for [MacOS](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4a-Connect-Prime-to-Toolbox-Mac.md) or [Windows](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4b-Connect-Prime-to-Toolbox-Win.md)
5. The Vuforia Spatial Toolbox needs to be in “advanced” node configuration for this activity.
   - To change the complexity of the node configuration, select the “Manage Hardware Interfaces” button of the Vuforia Spatial Edge Server to view all interfaces that are connected to the server
   - Ensure that the “Spike-Prime” node is turned ON
      - In the text box to the right of where it says “spikeComplexity,” change the node setting from its current state to “advanced” to ensure that all necessary nodes are made visible
      - Click the “Save” button to save the changes

6. In Terminal/Command prompt, Enter ```CTRL + C``` to stop the Vuforia Spatial Edge Server.
   - The server needs to be restarted for the node setup to change
7. Restart the server by typing node server into the _vuforia-spatial-edge-server_ directory
8. Open the Vuforia Spatial Toolbox mobile app and try connecting to the SPIKE Prime using the feedback pamphlet image target.
   - Open into Programming mode. If the new node configuration looks like the one below, then this step was completed.
    #### Troubleshooting:
      - If the node setup does not look like this, restart this section.
      - Common errors will include not changing the node setup to “advanced” or not hitting “save” before clicking out of the “Manage Hardware Interfaces” tab or not entering “advanced” in all lowercase letters.
      - If all steps for this section are followed properly but there are still issues with connecting, refer to Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox for [MacOS](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4a-Connect-Prime-to-Toolbox-Mac.md) or [Windows](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4b-Connect-Prime-to-Toolbox-Win.md)

## Setting up Vuforia Spatial Toolbox for a Fast Fourier Transform
This section introduces how to set up Vuforia Spatial Toolbox for using the FFTanalysis on the SPIKE Prime radial engine

1. The four nodes used for running the FFT are as follows:
   - FFTStart works as a toggle to trigger the FFT analysis. When it is turned on, data sampling will start
   - FFTLength is used for deciding the number of samples that are going to be taken into the FFT analysis. It intakes sample integers between 16 and 512 samples at powers of 2 (16, 32, 64, etc). Higher sample rates lead to accurate results but will also take slightly longer due to more samples being taken.
   - FFTAxis takes an input of 0, 1, or 2, which represent the X, Y, and Z axes on a coordinate system, respectively. This determines the axis along which the FFT analysis will be calculated.
   - To determine the direction the coordinate system is facing, attach a Value tool to each of the accelerometer nodes. Whichever node outputs a number around 980 (cm/s^2 ) is the vertical axis. Move the SPIKE Prime linearly to determine where the other two horizontal axes are. In the case below, the Value tool that is outputting 1005 cm/s^2 and is connected to the accelerometerY shows that the Y direction is on the vertical axis
   - FFTOutput outputs the solution of the FFT analysis. This will be attached to a Number tool, where the primary frequency of oscillation of the system will be displayed
2. In addition to the FFT nodes, there will also be three different tools that need to be added into the spatial environment in the Vuforia Spatial Toolbox app
   -  Numbers tool for inputting numbers and text
   - Switch tool that can be turned on and off
   - Value tool for number readouts
3. Add three Number tools, one Switch and one Value tool into the interface
4. Tool/Node connections are as follows:
   - Connect a Numbers tool to the motor1 node. This will be used for inputting the percentage of speed between 0 and 100 that the motor will run at
   - Connect a Numbers tool to the FFTAxis node for inputting the axis to apply the FFT analysis to
   - Connect a Numbers tool to the FFTLength node for inputting the number of samples to be taken during the analysis
   - Connect the Switch to the FFTStart node. When toggled ON, the FFTStart node will start the FFT analysis.
   - Connect the the FFTOutput node to the Value tool. This will display the frequency that the FFT analysis outputs
5. The connections should look similar to the image below, with the green arrows noting the way that the connection should be made:

## Running the Fast Fourier Transform
While the Fast Fourier Transform is just triggered by toggling on a node, there many things happening in the background. The FFT analysis is hosted on a  Heroku
server and calculations are triggered when the FFTStart node is toggled on. Heroku is a platform that enables applications to be built and run entirely in the cloud, which
is where the FFT server is hosted for this project.

1. Input a number between 0 and 100 in the Number tool that is connected to the _motor1_ node to start the motor. This number represents the percentage of full power that the motor will be running at.
- The motor should start running after the number is input and “done” is Entered on the upper right-hand of the keyboard.
    #### Troubleshooting:
   - Ensure that the SPIKE Prime is connected to the Vuforia Spatial Edge Server. There will be an array similar to the one below that is printed in the console when it is connected. There should be at least one motor that shows up and the corresponding port that it is connected to.
   - If the motor does not start, try deleting the Numbers tool that is connected to the motor1 node and close out of the app. Reopen the app, add in a new Numbers tool, connect it to the motor node, and repeat this step. If this does not work, restart the server and check that the Vuforia Spatial Toolbox app was able to connect to the Vuforia Spatial Edge Server

2. Input a 0, 1, or 2, for the X, Y, or Z axis, into the Numbers tool that is connected to the FFTAxis node to decide which axis will be sampled
3. Input an integer between 16 and 512 and a power of 2 into the Numbers tool that is connected to FFTLength to set the number of samples that will be taken.
4. Toggle the Switch to ON to start the FFTStart node to run the FFT analysis
5. In a few seconds, the Value tool connected to the FFTOutput should display the frequency that the radial engine is vibrating at in the given direction
6. As a bonus, try changing the design of the LEGO build and SPIKE Prime position to see how it affects the output of the FFT analysis

<-- Go back to [Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox on MacOS](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4a-Connect-Prime-to-Toolbox-Mac.md) or [Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox on Windows](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/4b-Connect-Prime-to-Toolbox-Win.md) or Continue to [Learn About IOT using Airtable](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/6-IOT-with-Airtable.md) -->
