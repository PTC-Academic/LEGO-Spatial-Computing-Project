# Learn About IOT using Airtable

**Estimated time to complete** 20 - 30 minutes

## Requirements
1. LEGO SPIKE Prime Hub & LEGO build
2. LEGO Education product feedback pamphlet
3. Computer with Bluetooth capabilities
4. Vuforia Spatial Toolbox compatible device
5. Vuforia Spatial Edge Server download from GitHub
6. Vuforia Spatial Toolbox app

## Getting Started
Airtable is an open-source collaborative database service. It can be used as an example of IOT connectivity that allows users to send data between different
objects and see those changes update in real time between the environments. In this example, using IOT, data will be sent between Airtable, Vuforia Spatial Toolbox,
and the SPIKE Prime using an API connection.

## Hardware Edits
As mentioned in the SPIKE Prime Hardware Build PDF, this activity serves its best purpose when additional parts are connected to the SPIKE Prime Hub. In the images
below, the distance sensor from the SPIKE Prime has been added to the build. If the distance sensor is not available, the pressure sensor can be substituted in to serve the same purpose.

## Setting Up Airtable

1. Visit https://airtable.com/
2. Click “Get started” to create a free account or sign in.
3. Make sure the “Bases” tab is selected
4. Click “Add a base” to start creating a database
    - Choose the “Start from scratch” option.
    - Give the base a name. The color of the base icon can be changed, and other customizations can be added if desired.
5. Click on the newly created database. The database that opens should lookl similar to the one below.
    - The table will be named “Table 1” by default. Keep this name, as it is the table name used when using the API to connect Airtable to Vuforia Spatial Toolbox. 
    - The API used to connect Airtable to Vuforia Spatial Toolbox is a XMLHttpRequest API, which is an object whose methods transfer data between a web browser and web server

6. Only two columns are needed for this project, so right click the heading of any extra fields and select “delete field”
7. Change the names of the columns. The first column should be named Variables and the second should be Value. Variables should be a “Single line text” field type and Value should be a “Long text” field type. The table should now look like the image below.
    #### Troubleshooting:
    - “Variables” is plural and “Value” is singular. It will not work if these columns do not match these exact names. To change the title of these two columns, search arrayItem.fields. within the index.html file of the _airtable_ tool folder (this is around line 315). This line arrayItem.fields. appears a few times so make sure to change all of them. arrayItem.fields.Variables should equal arrayItem.fields.[YOUR FIRST COLUMN NAME] and arrayItem.fields.Value should equal arrayItem.fields.[YOUR SECOND COLUMN NAME].

8. In the first row of the Variables field, type Motor and in the second row enter ```Distance```. Do not type anything into the Value field yet.

## Creating an API key
An API key is a unique identifier used to authenticate a user, developer, or calling program to an API. These are necessary to the cohesion of IOT connected devices.

1. Click on the account icon at the top right of the database and select “Account”
2. Click “Generate API key” under the <>API heading.
3. A personal API key will appear. Take note of this somewhere safe, as it gives anybody with the key access to the application and it will need to be used in a later section of this page.

## Getting a Base ID
Each base that is created will have its own unique identifier that will be used by the Airtable tool in the Vuforia Spatial Toolbox app.

1. Open a new tab and go to https://airtable.com/api
2. Select the base this is being used for this project to navigate to its main API page
3. The base ID for the base should be shown in a similar location to the image below.
4. Take note of the base ID in the same place that the API key is stored. This will be used in the next section.

## Prepare the Airtable Tool for Use
Before using the Airtable tool, it needs to be configured with the unique data for the base that will be used

1. Follow the folder path _SpatialToolbox-(Mac or Windows)-Interns/vuforia-spatial-edge-server/addons/vuforia-spatial-core-addon/tools/airtable_ and
    open the airtable.js file
2. Replace the “xxx..” placeholders with the API Key and Base ID that were written down in the previous steps and enter the name of the table that is being connected (Table 1 if the name of the table was not changed in step 5 of the Getting Started with Airtable section of this page)
    #### Troubleshooting:
    - A common error that hinders connection is just incorrect spelling of API Key or Base ID – be sure that they are copied and transferred exactly as they appear
3. The tool is now configured for a specific base inside of Airtable. The Airtable tool inside of Vuforia Spatial Toolbox will only take in data from this specific table. To send/receive data from a different table, go back into airtable.js and repeat step 2.

## Airtable API in Vuforia Spatial Toolbox
This section will instruct how to create a connection between Airtable, Vuforia Spatial Toolbox, and the SPIKE Prime.

1. If it is not already running, start the Vuforia Spatial Edge Server and open the
    Vuforia Spatial Toolbox app
    #### Troubleshooting:
        - If there are issues with connecting to the Vuforia Spatial Edge Server or the Vuforia Spatial Toolbox app, please refer to the PDF for connecting SPIKE Prime to Vuforia Spatial Toolbox
2. The Vuforia Spatial Toolbox needs to be in “Beginner” node configuration for this activity.
       -  To change the complexity of the node configuration, select the “Manage Hardware Interfaces” button of the Vuforia Spatial Edge Server to view all interfaces that are connected to the server
       -  Ensure that the “Spike-Prime” node is turned ON
       -  In the text box to the right of where it says “spikeComplexity,” change the node setting from its current state to _“beginner”_ to ensure that all necessary nodes are made visible
       - Click the “Save” button to save the changes
       -  An explanation of the Beginner node configurations can be found in **_Appendix D_** in [Appendices and Additional Resources](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/7-Appendices-and-Resources.md)
3. In the Vuforia Spatial Toolbox app connect to the SPIKE Prime using the LEGO SPIKE Prime feedback pamphlet as the image target
4. Drag and drop an Airtable API tool (seen below) from the pocket into the spatial environment in the Vuforia Spatial Toolbox app
5. Enter the variable name “Motor” where prompted. Make sure that the slider is on receiver mode, which will allow Vuforia Spatial Toolbox to receive data from Airtable. All other data to identify the unique table was added in the previous section.
6. Switch into Programming mode and make a connection from the Airtable API tool node to the motor1 node
7. In the Interface mode, add another Airtable API tool from the pocket. Enter the variable name “Distance” and change the slider to sender mode. This will send data from Spatial Toolbox to Airtable.
8. Switch into Programming mode again and make a connection from the distance node to the “Distance” Airtable API tool
9. Once this connection is established, the second row of the Value column in Table 1 in Airtable on the computer should register a value based on the distance between the distance sensor and the closest object in its path. This number will be equal to distance in cm. This number will change as objects are moved closer or further to the distance sensor.
    #### Troubleshooting:
    - If a value does not register, check to see if the SPIKE Prime connected to the Vuforia Spatial Edge Server properly and that the distance sensor registered properly during start up in the console
10. Type an integer between 0- 100 in the first row of the Value column next to Motor in Airtable, which will be the percentage of full speed that the motor is run at. Notice that this starts the rotation of the motor.
       -  To stop the motor, enter 0 into Airtable
    #### Troubleshooting:
    - If there are any issues with these steps, restart the server and close out of the app. Common issues may be: faulty server startup, failure to connect the SPIKE Prime to Vuforia Spatial Toolbox, and the computer and iPhone/iPad being on different Wi-Fi networks.

<-- Go back to [Fast Fourier Transform Activity](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/5-FFT-Activity.md) or Continue to [Appendices and Additional Resources](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/7-Appendices-and-Resources.md) -->