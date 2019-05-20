# Getting Started with FRC Programming

This is a quick guide to get setup to start programming. 

## Installing Programs
You need to install 3 different things in order. The first is FRC Driver Station. This program allows you to control the robot. Next is CTRE Toolsuite, which is the library for the motor controllers. Finally, VS Code is the program to write the robot code. 

#### FRC Driver Station
1. Download FRC Driver Station from [here](http://www.ni.com/download/first-robotics-software-2017/7904/en/)
    - Needs login with NI Account. Make one if you don’t have one 
2. Unzip the whole folder and run setup.exe
3. Click Next for everything. There is no need to fill in any information
4. You can just skip NI Licensing
    - Serial Number (if necessary): M83X20058
    - Season Unlock Password: $Robots&in#SPACE!!
#### CTRE
1. Click [here](http://www.ctr-electronics.com/hro.html#product_tabs_technical_resources)
2. Download the newest version of “CTRE Phoenix Framework Installer” (zip file) 
3. Unzip and run the program

#### WPILib Suite
1. Click [here](https://github.com/wpilibsuite/allwpilib/releases) and download the Windows 64 installer
2. Select all or current user, doesn’t matter
3. Make sure all checkboxes are checked. You probably have to select/download VS Code
4. Click “Execute Install” 

## Roborio
Roborio (the brain of the robot) needs to be configured correctly for it to work for this year. Here are the steps.
1. Updating the firmware and imaging the Roborio: https://wpilib.screenstepslive.com/s/currentCS/m/getting_started/l/1009233-imaging-your-roborio 
    - Note: If the shortcut is not on the desktop, it is located here: 
    C:\Program Files (x86)\National Instruments\LabVIEW 2017\project\roboRIO Tool
2. Install Phoenix Library/Diagnostic
    - Open Phoenix Tuner and connect to the robot
    - Click “Install Phoenix Library/Diagnostics”

## Configuring Radio
These are the steps for configuring the radio. Complete screen steps live instructions [here](https://wpilib.screenstepslive.com/s/4485/m/13503/l/144986-programming-your-radio-for-home-use).
1. Install radio configuration utility:
https://wpilib.screenstepslive.com/s/currentCS/m/getting_started/l/144986-programming-your-radio#download_the_software 
2. Choose radio type
3. Load firmware
4. Type in team number, then configure.

## Updating Firmwares
The PDP, PCM, Roborio, and TalonSRX may need firmware updates. 
1. Connect to roborio and open up Phoenix Tuner
2. Navigate to CAN Devices tab.
3. Under Field-Upgrade Device Firmware, select the CRF and click Update Device

Current Versions:

| Hardware Name | Firmware Version | Location |
|---------------|------------------|----------------------------------------------------------------------------------------------------------------------------|
| Roborio | 6.0.0.f | C:\Program Files (x86)\National Instruments\Shared\Firmware\cRIO\76F2 |
| PDP | 1.40 | All CTRE hardware are under the folder C:\Users\Public\Documents\Cross The Road Electronics\LifeBoat\HERO Firmware Files |
| PCM | 1.65 |  |
| Talon SRX | 4.22 |  |
| PigeonIMU | 4.13 |  |
| CANifier | 4.0 |  |

## Driver Station
The driver station is the program used to control the Robot. You can get familiar with the layout of the program [here](https://wpilib.screenstepslive.com/s/currentCS/m/getting_started/l/599677-frc-driver-station-powered-by-ni-labview). However, there are some settings that should be set to help you debug and connect to the robot.
1. Set the team number at the third tab (gear tab).
    - Change this whenever you work on a different robot.
2. At the same tab, change the dashboard type to Shuffleboard.

After finishing this guide, you should go on to the [First Program guide](First_Program.md).
