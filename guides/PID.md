# PID

This is a guide for what PID is and how to tune it. This will be based off the TalonSRX. If you are using some other motor controller, read about it online.

Most of the information comes from the CTRE documentation. It is highly recommended to [read through this manual](https://phoenix-documentation.readthedocs.io/en/latest/index.html).

PID control is what we currently use to control the motors for autonomous. What it does is you set a setpoint, then the sensors report data, then the data is processed to the correct motor power to get what you desired. In other words, it is closed loop control. Below is a flowchart of how it works:

![PID Flowchart](https://upload.wikimedia.org/wikipedia/commons/4/40/Pid-feedback-nct-int-correct.png)

## Setting up PID

There are 5 parts to set up PID Control. There is F, P, I, D, and Integral Zone. Below are the methods to set these 5 values. The values are just an example. It needs to be tuned to work well.

```java
// First paramter: PID Slot (Ranges from 0-3)
// Second parameter: Value
motor.config_kF(0, 0.2);
motor.config_kP(0, 2.1);
motor.config_kI(0, 0.001);
motor.config_kD(0, 20);
motor.config_IntegralZone(0, 50);
```

The F is known as the feed-forward gain. This is a conversion value that converts real motor properties to numbers calculable for the motor output.

The P is known as proportional value. It returns a value that is based off how far the current values are away from the setpoint. For instance, if the error is positive and large, then the value is also positive and large. Hence the name proportional.

The I is known as the integral value. It returns a value based off the accumulation of previous errors. If the accumulated error is too much over a period of time, it will return a greater value to run the motors to try to reach the setpoint faster.

The D is known as the derivative value. It checks the current rate of change and returns a value to adjust the rate of change. For instance, if the rate of change is too much, the D value will reduce the motor power to slow down the rate of change.

The Integral Zone is used to limit what error is used for the I calculation. If the error is greater than the Integral Zone, it will not contribute to the output of the motors.

## PID Modes

There are multiple PID modes:

- Position
- Velocity
- Current
- Motion Profile
- Motion Profile Arc
- Motion Magic

Position is used if you want the motor to run to a certain position.

Velocity is used if you want the motor to maintain a certain speed.

Current is used if you want the motor to maintain a certain current.

Motion profile is used if you want to generate a path for the robot to follow.

Motion Profile Arc is same as above, but the path includes an additional angle to follow.

Magic Motion is simplified motion profile. You tell it speed and acceleration and it will create the path for you.

## PID Tuning

There are many methods for PID Tuning, but sometimes they work, sometimes they don't. Below is what I believe to be the best way.

1. Set all other constants except for F to zero. Calculate F by dividing 1024 with the max speed of the sensor. F is necessary for every mode other than position
2. Now, start with the P constant at 1 and increase until the system oscillates.
3. Afterwards, add a D constant. Start the D constant around 10 times the P value and turn it up until you're satisfied.
4. Add an I constant if necessary. This should be added when system is near the setpoint, but is not quite there. Start at around 0.001. Remember to put an I Zone Constant!
