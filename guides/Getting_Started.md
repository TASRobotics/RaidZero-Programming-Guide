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
    - [VS Code Can’t Deploy Code](#VS-Code-Can't-Deploy-Code)
- [Github](#Github)
    - [Style Guide](#Style-Guide)
    - [Github Guide](#Github-Guide)
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

