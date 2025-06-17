**Robocar Project.**

**# Working Of Code - Robocar !!**

**Arduino Board : UNO**

Here the arduino programming code is divided into three main parts:

- Functions
- Values (variables and constants)
- Structure

**Functions:**

For controlling the Arduino board and performing computations.

Digital Read : Reads the value from a specified digital pin .

In this code 6 digital pins have been defined. These are defined as integer data types. Here const keyword is used to make that variable as read only. Hence it’s value cannot be changed.

- Trigger Pin No. = 6. - It is used to trigger the ultrasonic sensors sound pulses.
- Echo Pin No.= 10. - It produces a pulse when the reflected signal is received from ultrasonic sound sensor through trigger pin.
- Left IR Sensor Pin No.= 2.
- Right IR Sensor Pin No.= 8.
- Left Motor Pin No.= 3.
- Right Motor Pin No.= 4.

After this function void setup is used which sets these pins as outputs.

Command - Serial.Begin (9600), sets the baud rate. So that the Arduino can send out commands through the USB connection at this speed.

Digital Write: Writes a HIGH or a LOW value to a digital pin.

Pin Mode function has already been defined for the purpose of output on digital write function.

In this code a delay of 500 milliseconds has been provided for the Trigger Pin on low/high states I.e. ( Turn Off/Onn) which pause the execution of program for this particular period of time. When trigger pin is low then it reads the echo pin and returns the value of sound wave travel time in microseconds. Echo Pin when in high state returns the duration pulse in microseconds & then calculates the distance with the formula as - duration\*0.034/2.

**Values (variables and constants):**

Constants are predefined expressions in the Arduino language. They are used to make the programs easier to read.

- long duration; - Data Type – Long. Width 64 bits.

Tells us the value for duration of pulse in echo pin when on high state.

- int distance; - Data type – Integer. Width 32 bits

Tells us the distance from the obstacle. Formula used = duration\*0.034/2.

- Char String:- character string (text) defined to operate manual functions.

**Structure:**

- **With Sensors : Functions Used - Void Automatic**

IF – Control structure.

Else If – Control structure. (used in Manual) Else - Control structure.

The if statement checks for a condition and executes the following statement or set of statements if the condition is 'true'.

An else clause will be executed if the condition in the if statement results in false.

In this code. If the distance turns out to be less than 10 cm.

Then:

If the left ir sensor is equal to high then the left motor turns low and right motor turns high with a delay of 300 milliseconds.

If the right ir sensor is equal to high then the left motor turns high and right motor turns low with a delay of 300 milliseconds.

- Manually: **Functions Used - Void Manual.**

In this code String == operator has been used.

== (Equal to) operator compares the variable on left and right, if true then performs the functions.

To move the car:

If

F=Forward (Right Motor Low, Left Motor High)

Else If

B=Back (Right Motor High, Left Motor Low) Else If

R=Right (Right Motor High, Left Motor Low) Else IF

L=Left (Right Motor Low, Left Motor High) Else IF

S=Stop (Stops The Car)

Delays Provided = 500 Milliseconds.

- **Loop Structure – Function used void loop ()**

It allows the program to change and respond actively.

In this code. Function Void loop has been used between manual and sensor control. With a delay of 50 milliseconds.

Function Serial.available() is used in order to read the incoming data byte. If it is greater than 0 then Bluetooth reads the data with the function serial.read().

Now conditions are applied :

If bt (Manual) == 'A, then variable last=1; turns automatic(); - Sensors. Else, last=0; then Turns manual(bt); - Manual.

Else If, last==1 Turns automatic(); - Sensors.
