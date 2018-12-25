# Self-Balansing-Arduino-controlled-Robot

After enrolling in the subject  Computer Process Control, where various control techniques and algorithms were taught, including PID control, we decided to develop a project and see its real life practical implementation.
For that purpose, we decided to create a robot for autonomous balancing using the Arduino UNO microcontroller. In this way, we will overcome the basic concept behind the functioning of the PID algorithm and the systems whose control is enabled using it.
The general idea is to have a robot on two wheels connected to DC motors, that will keep its balance and not fall by changing and modulating the motor speed. The motos speed is controlled using an integrated circuit MPU6050 with gyroscope and accelometer, L298 motor driver, and the PID algorithm. Using the gyroscope and accelometer, the angle incline by which the robot is falling and the fall direction is calculated. Additionally, the yaw, pitch and roll angles are read from the MPU6050 board, and the pitch angle, converted in degrees and adapted to fit the normal position of the robot is used as an input in the PID algorithm. Furthermore, by experimentally finding the desired Kp, Kd, and Ki values, combined with the input, the PID algorithm generates an output voltage that is passed on the motor driver to control the speed of the motors and enable the robot not to fall. 


The code segments we used throughout the development of the project are the following ones: 

