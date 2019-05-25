# Sensors

This is a guide for common sensors used in FRC. All code is based off the TalonSRX. If you are using other motor controllers, read up other api docs.

## Basics

To start, tell the motor what type of sensor is plugged in. To do this, call the method `configSelectedFeedbackSensor(FeedbackDevice.XXXX)`, where XXXX is the type of the feedback device. Below is an example to setup a quadrature encoder.

```java
motor.configSelectedFeedbackSensor(FeedbackDevice.QuadEncoder);
```

To get data from the sensors, call these methods:

```java
motor.getSelectedSensorPosition(0); // Gets the current position of the sensor
motor.getSelectedSensorVelocity(0); // Gets the current velocity of the sensor
```

To reset the position reading of the sensors, call this method:

```java
motor.setSelectedSensorPosition(0);
```

Sometimes the sensor direction could be different than the motor output direction. For instance, when you run the motor with a positive power, the sensor might show negative values. To fix this, use this method:

```java
motor.setSensorPhase(true);
```

Another way to read just the raw sensor is to use `SensorCollection`. There are many methods in SensorCollection, so be sure to check them out. Below is a way to get the raw position of the quadrature encoder.

```java
motor.getSensorCollection().getQuadraturePosition();
```

## Encoders

Encoders are the basic movement sensors. It counts ticks for every turn done to the axel. The number of ticks to equal a revolution depends on the robot. It is not all the same.

### Quadrature Encoders

The Greyhills or the US Digital encoders fall into this category. Call this method to set them up.

```java
motor.configSelectedFeedbackSensor(FeedbackDevice.QuadEncoder);
```

### Analog Encoders

Analog encoders are analog, not digital, which means they only have outputs corresponding to the position it is currently in.  It is basically a potentiometer that goes all around. The position for this **cannot be reset**.

```java
motor.configSelectedFeedbackSensor(FeedbackDevice.Analog);
```

### Magnetic Encoders

These encoders are able to do both what the quadrature and the analog encoders can do. It changes depending on the settings you choose.

```java
// Setting for the absolute encoder mode.
motor.configSelectedFeedbackSensor(FeedbackDevice.CTRE_MagEncoder_Absolute);

// Setting for the relative (regular) encoder mode.
motor.configSelectedFeedbackSensor(FeedbackDevice.CTRE_MagEncoder_Relative);
```

## Potentiometer

Potentiometer checks the position of the axel connected to it. It has a limited turn, about 270 degrees.  Don’t try to overturn it!
The position **cannot be reset**.

```java
motor.configSelectedFeedbackSensor(FeedbackDevice.Analog);
```

## Limit Switch/Talon Tach

Limit switch is self-explanatory. Talon Tach is a optical limit switch. Below is an example for setting one up. You can change whether it is forward or reverse, where it is connected to, and whether it is normally opened or closed.

```java
// Configure the limit switch
motor.configForwardLimitSwitchSource(LimitSwitchSource.FeedbackConnector, LimitSwitchNormal.NormallyOpen);

// Check if limit switch is pressed
motor.getSensorCollection().isFwdLimitSwitchClosed();
```

## Pigeon IMU

This is a board that has multiple sensors on it, including gyroscope and accelerometer. This is how you construct it.

```java
// Constructor for the pigeon if it is connected to a motor.
PigeonIMU pidgey = new PigeonIMU(motor);

// Constructor for the pigeon if it is connected directly to the CAN Bus.
// Device_ID is the ID for the pigeon.
PigeonIMU pidgey = new PigeonIMU(Device_ID);
```

These are some other useful methods.

```java
// Get the gyro angle
pidgey.getCompassHeading();

// Get the change of the angle in degrees per second
double[] dps = new double[3];
pidgey.getRawGyro(dps);
System.out.println(dps[2]);

// Set the gyro angle to zero
pidgey.setCompassAngle(0);
```
