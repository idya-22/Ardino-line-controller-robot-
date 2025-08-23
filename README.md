# Ardino-line-controller-robot-
An Arduino Line Follower Robot is an autonomous vehicle that uses IR sensors to detect and follow a black line on a white surface. The Arduino processes sensor data and controls DC motors via a driver module to keep the robot on track. It is widely used in automation, robotics learning, and competitions.



#Components
1. Motors
Attributes:

normal_speed: Normal speed of the motors.
min_speed: Minimum allowable speed.
max_speed: Maximum allowable speed.
Pins for left and right motor control (left_in1, left_in2, left_en, right_in1, right_in2, right_en).
Methods:

initialize(): Sets up the motor control pins.
set_motor(int in1, int in2, int en, int speed): Controls individual motors.
get_direction(int speed): Determines motor direction.
normalize_speed(int speed): Ensures speed stays within defined limits.
drive(int speed_difference, bool debug): Drives the robot with a speed difference between left and right motors.
2. PID (Proportional-Integral-Derivative) Controller
Attributes:

KP: Proportional gain.
KI: Integral gain.
KD: Derivative gain.
last_proportional, integral: Trackers for PID calculations.
Methods:

calculate_speed_difference(int proportional): Computes the speed difference using PID control.
3. Sensors
Attributes:

threshold: Threshold value for line detection.
sensors_count: Number of sensors.
sensor_pins: Array of pins for individual sensors.
errors: Array of error values corresponding to different line positions.
previous_error: Tracks the previous error value.
Methods:

calculate_error(): Calculates the error based on sensor readings.
on_line(int sensor_pin): Checks if a sensor is on the line.
get_line_position(): Determines the position of the line based on sensor readings.
Settings
User-configurable settings for threshold, sensor count, sensor pins, errors, motor speeds, PID gains, debugging, and delay time.

Implementation
Initialize Components:

Set up motor control and serial communication.
Adjust PID and sensor settings.
Main Loop:

Continuously calculate sensor error.
Use PID controller to determine speed difference.
Drive the motors accordingly.
Debugging:

Optionally print error and speed difference values to Serial for debugging purposes.

