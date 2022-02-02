# Getting Started with FRC Programming

This is a quick guide to get setup to start programming. 

## Installing Programs

You need to install 4 different things. The first is FRC Driver Station, which allows you to control the robot. The second is the CTRE Toolsuite, which is the library for the motor controllers. Next is the REV Hardware Client, which allows you to interface with the PDP and SparkMAX motor controllers. Finally, WPILib is the IDE we will use to write the robot code.

### FRC Driver Station

1. Download and run the installer from [here](http://www.ni.com/download/first-robotics-software-2017/7904/en/)
    - Needs login with NI Account. Make one if you don’t have one 
3. Click Next for everything. There is no need to fill in any information
4. You can skip NI Licensing
5. If you encounter errors during the installation, try running the offline installer instead. 

### CTRE

1. Click [here](https://github.com/CrossTheRoadElec/Phoenix-Releases/releases)
2. Download the latest version of “CTRE Phoenix Framework Installer” for your os
3. Run the installer

### REV Hardware Client

1. Click [here](https://docs.revrobotics.com/rev-hardware-client/getting-started/installation-instructions)
2. Download the latest version of the REV Hardware Client
3. Run the installer

### WPILib Suite

1. Click [here](https://github.com/wpilibsuite/allwpilib/releases) and download the Windows 64 iso file
2. Right click on the downloaded iso and mount the disk image
3. Run the installer in the disk
4. You should choose the option that reinstalls VScode on your computer (Top Left)

## Roborio

Roborio (the brain of the robot) needs to be configured correctly for it to work for this year. Here are the steps.

1. Updating the firmware and imaging the Roborio: https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/imaging-your-roborio.html?highlight=robo%20rio%20imaging
2. Install Phoenix Library/Diagnostic
    - Open Phoenix Tuner and connect to the robot
    - Click “Install Phoenix Library/Diagnostics”

## Configuring Radio

These are the steps for configuring the radio. [here](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html?highlight=radio).

1. Install radio configuration utility:
https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/radio-programming.html?highlight=radio
2. Choose radio type
3. Load firmware
4. Type in team number, then configure.

## Updating Firmwares

The PDP, PCM, Roborio, and Motor Controllers may need firmware updates.

Updating the CTRE Motor Controllers, Pidgeon

1. Connect to roborio and open up Phoenix Tuner
2. Navigate to CAN Devices tab.
3. Under Field-Upgrade Device Firmware, locate the most up-to-date CRF, and click Update Device

Updating the PDP, CAN Motor Controllers

1. Connect to the PDP and open up REV Hardware Client
3. Select Check for Updates, then click Update All

## Driver Station

The driver station is the program used to control the Robot. You can get familiar with the layout of the program [here](https://wpilib.screenstepslive.com/s/currentCS/m/getting_started/l/599677-frc-driver-station-powered-by-ni-labview). However, there are some settings that should be set to help you debug and connect to the robot.

1. Set the team number at the third tab (gear tab).
    - Change this whenever you work on a different robot.
2. At the same tab, change the dashboard type to Shuffleboard.

After finishing this guide, you should go on to the [First Program guide](First_Program.md).
