# First Program

This is the guide for your first program. Follow this guide if you have finished the getting started guide. [Here](https://wpilib.screenstepslive.com/s/currentCS/m/java) is a guide that covers a lot of the programming for FRC. It is a little long, therefore the steps below will be shorter and easier for you to create a basic program to control the bot. After this, it is your turn to program whatever you want. Use the helpful sites guide to help whenever you get stuck in the future.

## Starting a New Project
To start, you need to create a new project. 
1. Click on the wpilib icon on the upper right then select “Create a new project”
2. Go through each step and fill it out. It should look something like this:
3. Click Generate

## Installing Third Party Libraries
For VS Code to recognize third party libraries such as CTRE, you have to add them to VS Code.
1. Click on the WPILib Command Icon in VS Code (Upper Right Corner)
2. Look for “Manage Vendor Libraries” and press enter
3. Click “Install new libraries (offline)”
4. Select the third party libraries and click “Go”

## Import, Declare, Initialize
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
