# Downloads

## Time to complete: 30 - 45 minutes

## Requirements

Computer running either MacOS or Windows
iPhone/iPad running iOS 12.0 or later

## Style Guide:

- Code is designated by <inline code> font
- Important notes are in **_bold italics_**
- Folder names are in _italics_
- Spatial UI buttons actions are in “quotations”

## Getting Started 
This page will give detailed instructions for downloading the software necessary to complete this project. 

## Vuforia Spatial Toolbox
Vuforia Spatial Toolbox has two primary software components: 
1. Vuforia Spatial Edge Server
1. Vuforia Spatial Toolbox application. 
Watch [Differentiating between the Vuforia Spatial Toolbox app and Vuforia Spatial Edge Server](https://www.youtube.com/watch?v=G5-06A-dxy4) for an explanation of these two components.

### Vuforia Spatial Toolbox App
Download the Vuforia Spatial Toolbox App through the App Store. Visit the
Download section of the Vuforia Spatial Toolbox website to see a list of
compatible devices. This app interacts with the spatial environment of Vuforia
Spatial Toolbox via an iPhone/iPad.

### ![Project Workflow Overview](https://github.com/PTC-Academic/LEGO-Spatial-Computing-Project/blob/master/Documentation/images/2-toolbox-app.png)

Troubleshooting note: iOS 14.0 may sometimes cause issues with connecting
using the Vuforia Spatial Toolbox app. To fix this issue, follow these steps:
```
1. Go into the iPhone/iPad Settings
2. Scroll down and click on “Toolbox”
3. Toggle the switches for local network and cellular data on and off

```
Vuforia Spatial Edge Server
The Vuforia Spatial Edge Server provides a web interface for connecting and
configuring the environment that is viewed in the Vuforia Spatial Toolbox app.
This server can edit image targets and spatial tools, as well as manage the
hardware interfaces that can be interacted with. The server needs to be
running on a computer to connect the LEGO SPIKE Prime to the Vuforia
Spatial Toolbox App. Mac and PC instructions for downloading the server
from GitHub are listed below, as they have slightly different download
methods.
```
**Git (Optional)**
Git is a distributed version control system which allows users to make changes to
code before actually implementing them. In this case, it provides a shortcut for
downloading the Vuforia Spatial Toolbox from GitHub. This download is not
required, as a zip file of the documents can be downloaded from GitHub, but it will
speed up the download process.


4. Use the link in the header of this section to go to the Getting Started page
    for Git. Scroll through this page and find the instructions for downloading
    Git.
5. Download Git with all default settings
6. Type where git if using Windows Command Prompt or whereis^ git if using
    Mac Terminal. **_If an error is received saying that “git is not recognized as_**
    **_an internal or external command, operable program or batch file” refer to_**
    **_the instructions below_**
       o To make sure Git is downloaded, follow these steps from Stack
          Overflow:

```
Modifying PATH on Windows 10:
```
▪ (^) In the Start Menu or taskbar search, search for "environment
variable".
▪ Select "Edit the system environment variables".
▪ Click the "Environment Variables" button at the bottom.
▪ Double-click the "Path" entry under "System variables".
▪ With the "New" button in the PATH editor, add C:\Program
Files\Git\bin\ and C:\Program Files\Git\cmd\ to the end of the
list.
▪ Close and re-open the console.
Modifying PATH on Windows 7:
▪ (^) Right-click "Computer" on the Desktop or Start Menu.
▪ (^) Select "Properties".
▪ (^) On the very far left, click the "Advanced system settings" link.
▪ Click the "Environment Variables" button at the bottom.
▪ Double-click the "Path" entry under "System variables".
▪ At the end of "Variable value", insert a^ ; if there is not already
one, and then C:\Program Files\Git\bin\;C:\Program
Files\Git\cmd\. Do not put a space between ; and the entry.
▪ Close and re-open the console.
**GitHub Desktop (Optional)**
Desktop interface for storing any files downloaded from GitHub. Suggested for
users who are not yet familiar with Git.

1. Download GitHub Desktop from the link in the section title
2. Open the install file that has been downloaded and start the install process
3. Sign in with GitHub account information or create an account

**Downloading the Vuforia Spatial Edge Server from GitHub**
GitHub is a website that provides hosting for code management and this is where all

the necessary files for using Vuforia Spatial Toolbox are stored. In order to do this


project, users will need to download the _SpatialToolbox-Mac-Interns_ or

_SpatialToolbox-Windows-Interns_ folder from the LEGO-Spatial-Computing-Project
repository in the PTC Academic GitHub, as explained in the bullets below, which
includes all the necessary files for running the Vuforia Spatial Edge Server. Check
out **_Appendix A_** in **Appendices and Additional Resources** for a folder hierarchy
explanation.

For Mac Users

1. In a web browser, go to the GitHub repository where the Vuforia Spatial Edge
    Server download is located: https://github.com/PTC-
    Academic/SpatialToolbox-Mac-Interns
2. Using Git in Terminal **_(for users experienced with Git)_**
    o Use git clone to download the GitHub repository. This is the fastest
       download method, but **_Git needs to be installed_** to complete it.
          ▪ Open Terminal. For instructions how to do this, follow the
             information on Apple’s website.
          ▪ Navigate to the _Documents_ folder in Terminal using the
             command cd^ Documents
                - Information on how to navigate through folders in
                   Terminal

▪ (^) Type in git clone https://github.com/PTC-Academic/Spatial-Toolbox-Mac-
Interns.git

- This step clones the GitHub repository into the _Documents_
    folder
3.^ Using GitHub desktop

o (^) The “Open with GitHub Desktop” option allows a manual import of the
Vuforia Spatial Edge Server folder into GitHub Desktop, **_if GitHub
Desktop has already been downloaded_**.


```
▪ Selecting the “Open with GitHub Desktop” option will prompt
GitHub Desktop to open
```
▪ (^) When GitHub Desktop opens, there is a pop-up window that
prompts users to choose a location for the repository to be
downloaded.

- For consistency purposes throughout the project, choose
    the _Documents_ folder of the computer as the location to
    clone the repository.
▪ Once a location has been chosen, the repository will clone itself
to the given location.

▪ (^) Navigate to the _Documents_ folder in Finder. If there is a folder
named _SpatialToolbox-Mac-Interns_ , then the cloning was
completed successfully.

4. Downloading ZIP File
    o For an option that does not require any additional software downloads,
       select the “Download ZIP” option. This will download a zipped version
       of the Vuforia Spatial Edge Server folder, most likely to the _Downloads_
       folder of the computer.
          ▪ When the download completes, locate the file in Finder and
             move it into the _Documents_ folder. Unzip the file if it did not unzip
             automatically.
5.^ **_The_** _SpatialToolbox_ **_folder inside of the_** _SpatialToolbox-Mac-Interns_ **_folder will_**
    **_need to be moved to sit directly in the_** _Documents_ **_folder, regardless of_**
    **_download method_****.** **_If this folder is not in the correct spot, the connection will_**
    **_not be properly established._**

For PC Users

1. In a web browser, go to the GitHub repository where the Vuforia Spatial Edge
    Server download is located https://github.com/PTC-
    Academic/SpatialToolbox-Windows-Interns
2. Using Git in Command Prompt
    o Use git clone to download the GitHub repository. This is the fastest
       download method, but **_Git needs to be installed_** to complete it.
          ▪ Open the Command Prompt
          ▪ Navigate to the _Documents_ folder in the Command Prompt using
             the command cd Documents
                - Information about common Command Prompt commands
          ▪ Type in git clone https://github.com/PTC-Academic/SpatialToolbox-
             Windows-Interns.git
                - This step clones the GitHub repository into the _Documents_
                   folder


3. Using GitHub Desktop
    o The “Open with GitHub Desktop” option allows a manual import of the
       Vuforia Spatial Edge Server folder into GitHub desktop, if GitHub
       Desktop has already been downloaded.
          ▪ Selecting the “Open with GitHub Desktop” option will prompt
             GitHub Desktop to open
          ▪ When GitHub Desktop opens, there is a pop-up window that
             prompts users to choose a location for the repository to be
             downloaded.
                -^ For consistency purposes throughout the project, choose
                   the _Documents_ folder of the computer as the location to
                   clone the repository.^

▪ (^) Once a location has been chosen, the repository will clone itself
to the given location.^
▪ Navigate to the _Documents_ folder in Finder. If there is a folder
named _SpatialToolbox-Windows-Interns_ , then the cloning was
completed successfully.

4. Downloading ZIP
    o For an option that does not require any additional software downloads,
       select the “Download Zip” option. This will download a zipped version
       of the Vuforia Spatial Edge Server folder most likely to the _Downloads_
       folder of the computer.
          ▪ When the download completes, locate the file in File Explorer.
             Unzip the file and move it into the _Documents_ folder
5. **_The_** _SpatialToolbox_ **_folder inside of the_** _SpatialToolbox-Windows-Interns_ **_folder_**
    **_will need to be moved to sit directly in the_** _Documents_ **_folder_**. **_If this folder is_**
    **_not in the correct spot, the connection will not be properly established._**


**Visual Studio 2019** (Community Edition – free)
Visual Studio is an integrated development environment for editing code

1.^ Download Visual Studio from the link in the section title
2. In the Visual Studio Installer, select the “Community Edition”
3. **_Make sure to check the boxes for the_** “Desktop development with C++” **_and_**
    “Node.js development” **_workloads when installing, as seen in the image_**
    **_below_**
4. In the pulldown bar at the bottom right-hand corner, select either “Install
    while downloading” or “Download all, then install” and then click “Install”.
    Download all, then install should be used if the internet connection that is
    being used is slow.
5.^ **_Troubleshooting note:_**^ The install can take a few minutes sometimes,
    depending on internet speed, so do not be alarmed if it does not complete
    the install immediately
6. The computer will need to restart after the install. Save all current work and
    restart the computer

**Node.js**
Node.js is an open source JavaScript environment that executes JavaScript code in

Terminal or Command Prompt. This in necessary in order to start the Vuforia Spatial
Edge Server.

1. Download Node.js for either MacOS or Windows from the link in the section
    title
       o For Windows, check the box that says “Automatically install the
          necessary tools. Note that this will also install Chocolatey. The script
          will pop-up in a new window after the new installation completes.”

**Python 3.**
Python is an object-oriented programming language. It is used when connecting

Vuforia Spatial Toolbox to the SPIKE Prime Hub. No changes will need to be made in


Python, but the software needs to be downloaded in order to run the initialize.py file

in the _vuforia-spatial-edge-server_ folder.

1. Follow the link in this section title to go to the download page for Python
    3.
2. Read the instructions on the page and scroll down to the different
    downloads at the bottom.

```
o For computers running macOS, choose the “macOS 64-bit installer”
o For Windows computers, choose the “Windows x86 executable
installer” or “Windows x86- 64 executable installer” for 64-bit
machines (Support for figuring out if a computer is 32 or 64 bits)
▪ Open the installer and choose the “Customize installation”
option
```
```
▪ In the Optional Features page, leave all default options
checked off and click “Next”
▪ In the Advanced Options page, set the file path for the
download to be C:/Users/[Your User
Name]/AppData/Local/Programs/Python/Python37 and
click “Install”
```

**LEGO Education SPIKE app**
The SPIKE app can be downloaded for free and is traditionally used as the
controlling interface for the SPIKE Prime. In this project, it is used only for connecting
the computer to the SPIKE Prime Hub since the Prime will be controlled with Vuforia
Spatial Toolbox.

1. Download the LEGO Education SPIKE app on a computer or tablet. This app
    will be used for connecting the SPIKE Prime to the Vuforia Spatial Edge
    Server in the **Connecting LEGO SPIKE Prime to Vuforia Spatial Toolbox**
    section of this project.


