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
A Fast Fourier Transform (FFT) is a method of frequency analysis that takes a discrete signal in the time domain and transforms that signal into its frequency domain components -- the fundamental frequencies at which an an object is vibrating. These frequencies is important to know to avoid having an object vibrate at its natural frequency, as that could cause potential failure in the object. In this activity, an FFT analysis will be made on a LEGO-based radial engine. 

## Changing the Hardware Interface

As mentioned in **Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox**, the setup of the nodes can be changed depending on need. In the case of this FFT activity, the Spike Prime Hardware Interface setup needs the **complexity** set to "advanced" and the **activity** set to "fft" in order to  ensure that all necessary nodes are made visible for the necessary analysis.

1. Connect the SPIKE Prime to a computer via Bluetooth if not already connected
2. Open Terminal/Command Prompt and go to the vuforia-spatial-edge-server directory
   - Enter ```cd Documents/SpatialToolbox-Mac-Interns/vuforia-spatial-edge-server``` on MacOS
   - Enter ```cd Documents/SpatialToolbox-Windows-Interns/vuforia-spatial-edge-server``` on Windows
3. Start the Vuforia Spatial Edge Server using the node server (Enter ```npm start``` or ```node server```)
4. Type “localhost:8080” in a browser to view the server
    ## ![Edge Server](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image001.png)
5. Set the Spike Prime Hardware Interface **complexity** to "advanced" and **activity** to "fft"
   - To change the complexity of the node configuration, select the “Manage Hardware Interfaces” button of the Vuforia Spatial Edge Server to view all interfaces that are connected to the server
   - Ensure that the “Spike-Prime” node is turned ON
      - In the text box to the right of where it says **spikeComplexity**, change the node setting from its current state to “advanced” 
      - In the text box to the right of where it says **activity**, change the node setting from its current state to fft 
    ## ![Edge Server Directory](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/4a-image020.png)
      - Click the “Save” button to save the changes
6. The server must be restarted for the node setup to change
   - In Terminal/Command prompt, Enter ```CTRL + C``` to stop the Vuforia Spatial Edge Server.
   - Restart the server by entering ```node server ```into the _vuforia-spatial-edge-server_ directory
7. Open the Vuforia Spatial Toolbox mobile app and try connecting to the SPIKE Prime using the feedback pamphlet image target.
   - Open into Programming mode. If the new node configuration looks like the one below, then this step was completed.  
    ## ![Node Configuration](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image002.png)
    #### Troubleshooting:
      - If you do not see the advanced and FFT notes, restart this section.
      - Common errors will include not changing the setup to “advanced”, "fft" or not clicking “save” before exiting the “Manage Hardware Interfaces” tab or not entering “advanced” in all lowercase letters.

## Setting up Vuforia Spatial Toolbox for a Fast Fourier Transform
This section introduces how to set up Vuforia Spatial Toolbox for using the FFTanalysis function with the SPIKE Prime radial engine

1. The first step to create the FFT visualization for your Spike Prime is to make an Airtable account. The purpose of Airtable is to store the necessary values of the FFT heroku server which is then used to update the visualization in the Spatial Toolbox. 
   - To make an Airtable account, visit [Airtable](https://airtable.com/)
      - Click “Get started” to create a free account or sign in
      - Make sure the “Bases” tab is selected
      - Click “Add a base” to start creating a database. Choose the “Start from scratch” option and give the base a name
   - Once you have made your own Airtable account, you should configure your Table to look exactly like the one below: 
   ## ![Airtable Configuration](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image010.png)
   - **IMPORTANT:** For your table, it should be called Table1 as default (if there is a space, right click and edit the name to say "Table1"). Additionally, you should only have two columns, one titled **Variables** (plural) and the other **Value** (singular). Underneath the **Variables** column, please write **magnitudes** and below that, write **frequencies**. (See image above for reference). 
2. The next step is to find your API Key and BaseID of your Airtable. This can be found by clicking the **HELP** button at the top right of your Airtable and then selecting **API Documentation**. In this documentation, there should be a toggle to show your API key in the top right. Once you have located your information, we can transfer this to the Spatial Toolbox.
   - Within your Spatial Toolbox folder (either SpatialToolbox-Mac-Interns or SpatialToolbox-Windows-Interns), double click the respective folders to naviate to the necessary file: ```vuforia-spatial-edge-server/addons/vuforia-spatial-core-addon/blocks/fft``` 
   - Open the ```index.js``` file and on lines 66-68 replace the the text on the right hand side with your informated. **Ex.** On the right side of **BASEID**, type "Your Unique BaseID" (**Note.** make sure to include the quotes as these are all strings)
   - Once you update the file, make sure to save and then close out the file
3. Now that you have updated the file with your credentials, we can start the server. In terminal, navigate to your vuforia-spatial-edge-server and start the Vuforia Spatial Edge Server using the node server (Enter ```npm start``` or ```node server```). This is similar to the steps mentioned above. 
   - Once you open the app and hover over your image target, you can use this video for some assistance: [Using the FFT in Vuforia Spatial Toolbox](https://youtu.be/DtDQxQUz03o)
   - The FFT Tool and the FFT logic block looks like: <br /> 
      <img src="https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image011.png" alt="FFT Tools" width="200px">

## Using the FFT in Vuforia Spatial Toolbox
As you use the video above as reference, here are some specific steps for further clarification:
<br>**Helpful Resource:** [An illustrated guide to using the Vuforia Spatial Toolbox](https://spatialtoolbox.vuforia.com/docs/use/using-the-app)
1. Hover over your image target so that all of the nodes appear
2. Select the pocket on the right (this is the middle icon) and click and drag the Number Tool onto your screen. The Number Tool looks like: 
   ## ![Numbers tool](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image005.png)
3. Then select the pocket once more to click and drag the FFT tool onto your screen
4. After you have these two objects, select the programming mode on the right (this is the icon above the pocket)
   - Once you are in the programming mode, click & hold onto the pocket and drag your finger to somewhere on your screen. This should allow you to bring a logic block into your space (use the illustrated guide above for further assistance if needed)
5. You can then slect your logic block which will open its panel. Select the green pocket on the right and click & hold on the FFT logic block. Place this logic block on the upper left on the 2x4 panel for ease of convience. 
6. Notice how the FFT logic block takes up two spaces, this is because it expects two inputs and returns one output. 
   - For our purpose, we can make on connection from the blue input to the left side of the FFT logic block (Input 1) and another connection from the green input to the right side (Input 2). 
   - We can then make a connection from the FFT logic block to an output. In the video, [Using the FFT in Vuforia Spatial Toolbox](https://youtu.be/DtDQxQUz03o), we use the yellow OUT
7. Select the back arrow on the right side to exit the logic block. 
   - Still in the programming mode, make a connection going from the number tool to the logic block. As you make this connection you will notice four colors appearing on the logic block. The number tool should be our Input 1, so it should be connected to the blue color. 
   - The next step is to connect the accelerometer data from the SPIKE Prime to our Input 2, the green color. You can choose whether you want the X, Y, or Z accelerometer data
   - After these inputs are connected, connect the output of the logic block (if you chose the yellow OUT, then it would be the yellow color) to the FFT Tool
8. Once you follow all of these steps, it should be ready to go! 
   - The Number Tool that is connected to the FFT logic block is for the **Sample Size**, which should be a power of 2
   - If your motor is not already running, you can drag in a number tool and connect it to the a SPIKE Prime motor to have it move at various speeds
   - **IMPORTANT:** The default **Sample Rate** is ```50```. To change this value, navigate to: ```vuforia-spatial-edge-server/addons/vuforia-spatial-core-addon/blocks/fft```. Open the ```index.js``` and on line 227, change the number ```50``` to your desired Sample Rate 

<!--
1. The four nodes used for running the FFT are as follows:
   - **FFTStart** works as a toggle to trigger the FFT analysis. When it is turned on, data sampling will start
   - **FFTLength** is used for deciding the number of samples that are going to be taken into the FFT analysis. It intakes sample integers between 16 and 512 samples at powers of 2 (16, 32, 64, etc). Higher sample rates lead to accurate results but will also take slightly longer due to more samples being taken.
   - **FFTAxis** takes an input of 0, 1, or 2, which represent the X, Y, and Z axes on a coordinate system, respectively. This determines the axis along which the FFT analysis will be calculated.
   - To determine the direction the coordinate system is facing, attach a Value tool to each of the accelerometer nodes. Whichever node outputs a number around 980 (cm/s^2 ) is the vertical axis. Move the SPIKE Prime linearly to determine where the other two horizontal axes are. In the case below, the Value tool that is outputting 1005 cm/s^2 and is connected to the accelerometerY shows that the Y direction is on the vertical axis
    ## ![FFTAxis](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image003.png)
    ## ![FFT Axis Values](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image004.png)
   - **FFTOutput** outputs the solution of the FFT analysis. This will be attached to a Number tool, where the primary frequency of oscillation of the system will be displayed
2. In addition to the FFT nodes, there will also be three different tools that need to be added into the spatial environment in the Vuforia Spatial Toolbox app
   - Numbers tool for inputting numbers and text
    ## ![Numbers tool](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image005.png)
   - Switch tool that can be turned on and off
    ## ![Switch tool](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image006.png)
   - Value tool for number readouts
    ## ![Value tool](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image007.png)
3. Add three Number tools, one Switch and one Value tool into the interface
4. Tool/Node connections are as follows:
   - Connect a Numbers tool to the motor1 node. This will be used for inputting the percentage of speed between 0 and 100 that the motor will run at
   - Connect a Numbers tool to the FFTAxis node for inputting the axis to apply the FFT analysis to
   - Connect a Numbers tool to the FFTLength node for inputting the number of samples to be taken during the analysis
   - Connect the Switch to the FFTStart node. When toggled ON, the FFTStart node will start the FFT analysis.
   - Connect the the FFTOutput node to the Value tool. This will display the frequency that the FFT analysis outputs
5. The connections should look similar to the image below, with the green arrows noting the way that the connection should be made:
    ## ![Node-Tool Connections](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image008.png)
-->
<!--
## Running the Fast Fourier Transform
While the Fast Fourier Transform is just triggered by toggling on a node, there are many things happening in the background. The FFT analysis is hosted on a  Heroku
server and calculations are triggered when the FFTStart node is toggled on. Heroku is a platform that enables applications to be built and run entirely in the cloud, which
is where the FFT server is hosted for this project.
-->
<!--
1. Input a number between 0 and 100 in the Number tool that is connected to the _motor1_ node to start the motor. This number represents the percentage of full power that the motor will be running at.
- The motor should start running after the number is input and “done” is Entered on the upper right-hand of the keyboard.
    #### Troubleshooting:
   - Ensure that the SPIKE Prime is connected to the Vuforia Spatial Edge Server. There will be an array similar to the one below that is printed in the console when it is connected. There should be at least one motor that shows up and the corresponding port that it is connected to.
## ![Console output](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/images/5-image009.png)
   - If the motor does not start, try deleting the Numbers tool that is connected to the motor1 node and close out of the app. Reopen the app, add in a new Numbers tool, connect it to the motor node, and repeat this step. If this does not work, restart the server and check that the Vuforia Spatial Toolbox app was able to connect to the Vuforia Spatial Edge Server
-->
<!--
2. Input a 0, 1, or 2, for the X, Y, or Z axis, into the Numbers tool that is connected to the FFTAxis node to decide which axis will be sampled
3. Input an integer between 16 and 512 and a power of 2 into the Numbers tool that is connected to FFTLength to set the number of samples that will be taken.
4. Toggle the Switch to ON to start the FFTStart node to run the FFT analysis
5. In a few seconds, the Value tool connected to the FFTOutput should display the frequency that the radial engine is vibrating at in the given direction
6. As a bonus, try changing the design of the LEGO build and SPIKE Prime position to see how it affects the output of the FFT analysis
-->

Go back to [Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox on MacOS](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/4a-Connect-Prime-to-Toolbox-Mac.md) or [Connecting a LEGO SPIKE Prime to Vuforia Spatial Toolbox on Windows](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/4b-Connect-Prime-to-Toolbox-Win.md) or continue to [Appendices and Additional Resources](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/6-Appendices-and-Resources.md)

