# Self-Balansing-Arduino-controlled-Robot

We decided to create a robot for autonomous balancing using the Arduino UNO microcontroller. In this way, we will overcome the basic concept behind the functioning of the PID algorithm and the systems whose control is enabled using it.
The general idea is to have a robot on two wheels connected to DC motors, that will keep its balance and not fall by changing and modulating the motor speed. The motos speed is controlled using an integrated circuit MPU6050 with gyroscope and accelometer, L298 motor driver, and the PID algorithm. Using the gyroscope and accelometer, the angle incline by which the robot is falling and the fall direction is calculated. Additionally, the yaw, pitch and roll angles are read from the MPU6050 board, and the pitch angle, converted in degrees and adapted to fit the normal position of the robot is used as an input in the PID algorithm. Furthermore, by experimentally finding the desired Kp, Kd, and Ki values, combined with the input, the PID algorithm generates an output voltage that is passed on the motor driver to control the speed of the motors and enable the robot not to fall. 


The code segments we used throughout the development of the project are the following ones: 

1) Motor_Test.ino

After connecting the motors and the driver to the arduino board according to the desired scheme, this code is to be used to check if the motors and the driver work properly.
After running the code, it runs the motors at different speeds and directions, and enables the user to check if the hardware and the connections are working or there is some anomaly or mistake. 

2) MPU6050_calibration.ino

After connecting the MPU6050 sensor, and deciding what will be its position on the robot, it is important to modify the offset values in the code according to your robot's needs. This is done by using this code script, which prints the desired offset values for each axis that are to be plugged in in the main program _24.12_Self_Balans main code.ino. 
For example: mpu.setXGyroOffset(220);

It is important to modify these values, since when the mpu is not moving, there exist values which we have to remove from our readings. For that we get the average of this error and subtract it from our reading.

3) _24.12_Self_Balans main code.ino

This is the main portion of the code that does all the work. The code is well commented and explained in the script. 
Run it in the end after modifying the offset values and the setpoint value in the code. [For example : double setpoint= 170.3;]
The setpoint should be modified by setting the value when the bot is perpendicular to ground using serial monitor. This is the point which is considered to have a perfect balance, and the control algorithm strives to achieve this balance point (zeroth point). 
This point should be read by running the code and reading the input value from serial monitor for which the bot is perfectly balanced. This value should be plugged in/ edited in the code. 

** 4) MPU6050_printRAWvalues.ino
This code is to be used optionally, in order to see how the MPU works.


