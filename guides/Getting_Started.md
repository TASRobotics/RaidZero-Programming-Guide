# Getting Started with FRC - Programming Team

This is a quick guide to get started for the programming team. However, not everything may be mentioned here, because we value the ability to problem solve and RTFM (Read The Manual). Therefore, when you encounter a problem, use your brain a bit before asking for help. Most of the details mentioned in this document are mentioned in the wpilib screen steps live website. Use this [site](http://wpilib.screenstepslive.com/s/currentCS) if you need to further information. 

The guide will be as updated as possible. If something is out of date or some more information needs to be included, please make a github issue [here](https://github.com/TASRobotics/Raid-Zero-Programming-Guide/issues) so one of the veterans can work on it.

## Table of Contents
- [Installing Programs](#Installing-Programs)
    - [FRC Driver Station](#FRC-Driver-Station)
    - [CTRE](#CTRE)
    - [WPILib Suite](#WPILib-Suite)
    - [Installing Third Party Libraries](#Installing-Third-Party-Libraries)
- [Roborio](#Roborio)
- [Configuring Radio](#Configuring-Radio)
- [Updating Firmwares](#Updating-Firmwares)
- [Driver Station](#Driver-Station)
- [Programming](#Programming)
    - [Starting a New Project](#Starting-a-New-Project)
    - [Import, Declare, Initialize](#Import,-Declare,-Initialize)
- [Deploying Code](#Deploying-Code)
- [Sensors](#Sensors)
- [Troubleshooting](#Troubleshooting)
    - [Driver Station Connection Issue](#Driver-Station-Connection-Issue)
    - [Firewall](#Firewall)
    - [Changing Team Number](#Changing-Team-Number)
- [API Docs](#API-Docs)
- [Helpful Sites and Manuals](#Helpful-Sites-and-Manuals)

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

#### Installing Third Party Libraries
For VS Code to recognize third party libraries such as CTRE, you have to add them to VS Code.
1. Click on the WPILib Command Icon in VS Code (Upper Right Corner)
2. Look for “Manage Vendor Libraries” and press enter
3. Click “Install new libraries (offline)”
4. Select the third party libraries and click “Go”

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

## Programming
If you have finished everything from above, you can now start to code! [Here](https://wpilib.screenstepslive.com/s/currentCS/m/java) is a guide that covers a lot of the programming for FRC. It is a little long, therefore the steps below will be shorter and easier for you to create a basic program to control the bot. After this, it is your turn to program whatever you want. Use the guides down below to help whenever you get stuck in the future.
#### Starting a New Project
To start, you need to create a new project. 
1. Click on the wpilib icon on the upper right then select “Create a new project”
2. Go through each step and fill it out. It should look something like this:
3. Click Generate

#### Import, Declare, Initialize
Before doing anything, you can delete all the default template code except for line 8. Then paste this in as a template.

```java
package frc.robot;

import edu.wpi.first.wpilibj.TimedRobot;
import edu.wpi.first.wpilibj.Joystick;

import com.ctre.phoenix.motorcontrol.ControlMode;
import com.ctre.phoenix.motorcontrol.can.TalonSRX;

public class Robot extends TimedRobot {
  // Declare objects below here
  TalonSRX motor;
  Joystick joy;

  /**
   * This function is run when the robot is first started up and should be
   * used for any initialization code.
   */
  @Override
  public void robotInit() {
    motor = new TalonSRX(0);
    joy = new Joystick(0);
  }

  /**
   * This function is run once each time the robot enters autonomous mode.
   */
  @Override
  public void autonomousInit() {
    
  }

  /**
   * This function is called periodically during autonomous.
   */
  @Override
  public void autonomousPeriodic() {
    
  }

  /**
   * This function is called once each time the robot enters teleoperated mode.
   */
  @Override
  public void teleopInit() {

  }

  /**
   * This function is called periodically during teleoperated mode.
   * This is where the code for manual control goes
   */
  @Override
  public void teleopPeriodic() {
    motor.set(ControlMode.PercentOutput, 0);
  }
}
```

This code is an example for importing, declaring, and initializing objects and also a hint for controlling the motors.

Importing is done before the class, declaring is done before robotInit, and initializing is done in robotInit. Motor control goes in teleopPeriodic.

The example motor is currently told to run at 0%, so it is up to you to figure how to control with the joystick.

#### Deploying Code
To deploy the program into the roborio, connect to it first either by usb or wireless. Then press “Shift + F5”. Wait until it says build successful.

*Note: Be sure that the team number is the same as the roborio number. To change this, there is a wpilib command called “Set Team Number”.


## Troubleshooting
For some occasions, you may be unable to connect to the robot or deploy code. This could be due to numerous reasons such as the firewall, but the issue changes depending on the situation. These are just some solutions to common issues.


#### Driver Station Connection Issue
If the driver station is not connecting to the robot, it could be two reasons: firewall or the team number is wrong. 

##### Firewall
1. Go to control panel and search for firewall. Select Allow a program through Windows Firewall
2. Check if Driver Station is on the list. If not, click Allow another program
3. Select FRC Driver Station and click add. If it is not there, browse
    C:\Program Files (x86)\FRC Driver Station\DriverStation.exe
4. Now, click all the checkboxes for FRC Driver Station

##### Changing Team Number
Refer back [here](#Driver-Station)

## API Docs
These are the documents where you can search up methods and classes of the libraries.
- WPI Lib (Main FRC Classes): http://first.wpi.edu/FRC/roborio/release/docs/java/
- CTRE (Motor controller): http://www.ctr-electronics.com/downloads/api/java/html/index.html

## Helpful Sites/Manuals
These are a few sites and manuals that will be helpful for you.

- Roborio Page
    - CONNECT to the roborio when you do this.
    - Use any broswer and search http://roborio-XXXX-frc.local/, where XXXX is your team number, with no leading zeroes
    - You can use 172.22.11.2 if you use a USB cable to connect. 
- [Hardware Overview](https://wpilib.screenstepslive.com/s/currentCS/m/getting_started/l/599672-frc-control-system-hardware-overview) 
- [Wiring Overview](https://wpilib.screenstepslive.com/s/currentCS/m/cs_hardware/l/144971-wiring-the-frc-control-system) 
- [CTRE Documentation/Manual](https://phoenix-documentation.readthedocs.io/en/latest/index.html) 