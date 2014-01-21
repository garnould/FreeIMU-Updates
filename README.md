FreeIMU-Updates
===============

Change Log
Monday, January 20, 2014
6:28 PM
�
�
 
10-27-2013	1. Modified incorporate temperature correction for gyro and accelerometer
2. Corrected __AVR__ to __AVR_ATmega128__
3. Added call to get temperature from MPU-6050 in getRawValues
4. 1D Kalman Filter on q-values in sketch
	   
10-29-2013	Corrected temp coefficient array for temp
�	   
11-01-2013	 Added new inverse sqrt code obtained from articles:
http://pizer.wordpress.com/2008/10/12/fast-inverse-square-root/ and
http://www.diydrones.com/forum/topics/madgwick-imu-ahrs-and-fast-inverse-square-root
�	   
11-05-13	1. Add code to reset MPU-6050 on start-up, implemented in the Arduino sketch as well as option to manually reset in processing sketch.
2. Added LPF code line, currently set to MPU60X0_DLPF_BW_42
�	   
11-23-13	1. Changed twoKidef from 0.1 to 0.0f -12-12 => twoKiDef changed from 0f to 0.0025f based on article in DIYDrones
2. Added bypass caps (0.1 and 0.01 ceramic caps on the power pins of the freeIMU
2a. Added a 10 uF tantalum on the power bus
3. Yaw drift stabilized very nicely
4. Updated processing sketch to calculate heading and display based on the freescale application note and as implemented:
   http://diydrones.com/profiles/blogs/tiltcompensated-heading
5. update RESET function to zero out initial values
�	   
12-06-13	1. added LSM303D Polulo board instead of  calculating heading from FreeIMU
2. added option to turn on/off temp correction, temp_corr_on
3. added variable to set temperature break where calibration turns off, temp_break, note: temp_break in units directly from MPU-6050
�	   
01-02-14 to
  01-05-14	1. Recalibrated 6050 using Madgewick automated calibration rig - see paper
2. Corrected temperature calibration coefficients to ensure that gyros are zeroed for whole temp range when at rest - deleted necessary to run zerogyro routine.
3. Acceleration coefficients adjusted so Ax = 0, Ay = 0 and Az = 1g when at rest
4. Had to tune Ki to reduce drift - now set to 0.165
5. Changed Kp to 1.0 - drift almost zero
�	   
01-08-14	1. Completed coding ZARA ZUPT for Zero velocity detemination - added code to the processing sketch
�	   
01-09-14	1. Added a Reset Quaternion matrix only - option 2 in the sketch - to allow reset of matrix after rapid movement.
�	   
�1-20-14	Summary of Processing sketch 
1.	updated to incorporate Altitude-Accelerometer complimentary filter
2.	motion detection indicator based on Zara-Zupt
3.	read additional fields from Arduino sketch
4.	Heading stability routine for LSM303 heading.
5.	Reset MPU-6050/Quaternion matrix by sending serial commands 1 or 2 respectfully.	 