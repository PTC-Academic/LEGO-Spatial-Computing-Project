# Appendices and Additional Resources**
This page is created with the intent of being an appendix to all the documentation
that has been given for this project. Please refer to this document throughout this
project.

There are also additional resources listed for further explanation with all parts of this
project.

**Appendix A:** SpatialToolbox-Mac/Windows-Interns folder hierarchy

**Appendix B:** Concept Map


**Appendix C:** Project Process Map

**Appendix D:** Node Explanations

Beginner


Beginner has 5 nodes: screen, LED, motors, distance, and stopMotors. This one
should be used by students who are just starting to work with the SPIKE Prime for
the first time.

- The screen node is connected to the screen of the SPIKE Prime so that the
    image on the SPIKE Prime interface can be changed
- The LED node allows for a number to be typed in to change the color of the
    LED on the SPIKE Prime
- The motors node, when toggled on, starts all the motors of the SPIKE
- The distance node outputs the distance that the SPIKE is from another object
    in cm
- The stopMotors node stops the motors from running when toggled on

Intermediate
Intermediate mode has 7 nodes: 3 motor nodes, a color sensing node, distance
node, force node, and stopMotors node. This should be used by students who feel
that they have gotten the hang of the Beginner mode.

- The three motor nodes are now separated for individual motor control, as
    opposed to the one motor node in Beginner mode that started all the nodes
    at once. In this case, users should note which motor is connected to which
    input on the SPIKE Prime. For example, if there are motors at inputs A, B, and
    C, the motors will match up with the number of motor nodes. The motor at
    input A on the Hub will be motor1, input B will be at motor2, and so on. If there
    are less than three motors, only motor1 and motor2, or only motor1 will be
    used.
- The color node will output a color when it is read the color sensor that can be
    attached to the SPIKE and can be attached to a Value tool that will display the
    name of the color
- The force node will output the amount of force that is put on it in Newtons,
    and like the color node, can be attached to a Value tool for viewing
- The distance and stopMotors nodes work the same as in the Beginner mode

Sensor
Sensor mode is meant to be used when sampling using a high refresh rate and has
gotten rid of some nodes, including all motor nodes, in order to do that. This mode
consists of the same color, distance, and force sensors from the Intermediate mode
and has added in accelerometer and gyroscope data in the X,Y, and Z directions.

- The three accelerometer nodes will output acceleration data for a certain
    direction in cm/s^2
- The three gyroscope nodes will output rotation data in degrees/s
- The color, distance, and force sensors work the same as they have in
    previous nodes


Advanced
Advanced mode combines concepts from all three modes before it. It contains
three motor nodes, for up to three motors to be connected, force, distance and
color sensors, a stopMotors node, and X, Y, and Z outputs for the gyroscope and
accelerometer. All these nodes work the same as in previous modes. It also adds
four new nodes: FFTStart, FFTLength, FFTAxis, and FFTOutput, which are used for
doing Fast Fourier Transform analyses.

- FFTStart works as a toggle to trigger the FFT analysis. When it is turned on,
    data sampling will start
- FFTLength is used for deciding the number of samples that are going to be
    taken into the FFT analysis. It intakes sample integers between 16 and 5 12
    samples at powers of 2 (16, 32, 64, etc). Higher sample rates lead to accurate
    results but will also take slightly longer due to more samples being taken.
- FFTAxis takes an input of 0, 1, or 2, which represent the X, Y, and Z axes on a
    coordinate system, respectively. This determines the axis along which the
    FFT analysis will be calculated.
- FFTOutput outputs the solution of the FFT analysis. This will be attached to a
    Number tool, where the primary frequency of oscillation of the system will be
    displayed

```
Additional Resources
```
- LEGO SPIKE Prime support/FAQ’s
- Vuforia Spatial Toolbox Forum – this is the go-to area for any questions
    relating to the Vuforia Spatial Toolbox and is monitored by the Spatial
    Toolbox team
- How to create an object with an AR interface – tutorial for creating a new
    object in the Vuforia Spatial Edge Server
- How to create an image target – tutorial for creating personal image targets
    using either the Vuforia Spatial Edge Server or PTC Developer Portal
- How to create a tool – tutorial teaching how to create additional tools for the
    pocket
- How to create a new hardware interface – tutorial for adding additional
    hardware interfaces to connect to something other than a SPIKE Prime
- Explaining the Vuforia Spatial Robotic Addon
- Dive deeper – a section outlining the system architecture, data model, and
    local vs global tools in Vuforia Spatial Toolbox
- Airtable Support


