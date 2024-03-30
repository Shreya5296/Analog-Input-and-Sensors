# Analog-Input-and-Sensors

whichever signal we see in the waveform is called an Analog signal
In our IoT kit, we have the rotary potentiometer

Potentiometer: A potentiometer is a 3 terminal device in which the resistance is manually varied to control the flow of electric current.
A potentiometer usually has 3 pins:
1. VCC pin: Connect this pin to VCC (5V or 3.3v)
2. GND pin: connect this pin to GND (0V)
3. DATA pin: Data pin is used to communicate between the potentiometer and ESP32, Data pin outputs the voltage to ESP32's input pin.

How does Potentiometer Work?
The potentiometer's shaft can be rotated from 0 (Minimum) to 270(Maximum)
The voltage in the output pin is in direct proportion to the angle varying from 0 to VCC.

Step -1:Gather the material from the IoT kit:
● 1 x ESP32
● 1 x USB Cable
● 1 x Breadboard
● 4 x Jumper wires
● 1 x Potentiometer

Step -2: Let’s do connections:
● Supply positive(VCC (+ve)) from the ESP 32 to breadboard +ve terminal
● Supply negative (GND (-ve)) from the ESP 32 to breadboard negative terminal
● Now our breadboard have (VCC (+ve)) and (GND (-ve)) supply
● Insert potentiometer into the breadboard
● Keep track of all three pins, Ist and last pin of potentiometer are used for (VCC (+ve)) and (GND (-ve)) respectively

Note : (VCC (+ve)) and (GND (-ve)) of the potentiometer can be interchangeable.

● Provide supply to the potentiometer from the breadboard

Note: In Breadboards power rail first five are connected, to make other connected provide jumper wires as shown in the circuit diagram.

● Now it's time to connect the middle pin i.e output of potentiometer. connect the potentiometer's output pin to an ESP32's analog input pin 36. The ESP32's analog input pin converts the voltage (between 0v and 3.3V) into integer values (between 0 and 4095),
or analog values.

Note: Multifunctionality of GPIO input pins, here pin 36 will acts as an Analog pin

Step-3 Let’s write a code:
To Map value of voltage with potentiometer we need to use float map() function. It will map 0 to 3.3V/5V according to the rotation of the potentiometer. It will map value from low
to high or high to low.
floatMap() is used to get all decimal value
Initialize using void setup() function
● Serial. begin(9600) is used for data exchange speed. speed parameters. This tells the Arduino to get ready to exchange messages with the Serial Monitor at a data rate of 9600 bits per second. That's 9600 binary ones or zeros per second and is commonly called a baud rate.

To execute the main process write the void loop()
● The output pin of the potentiometer is connected to the ESP32 analog input pin. To read this value we need to use the analogRead() function. analogRead() function is used to read the value of the potentiometer reading. This means that it will map input voltages between 0 and the operating voltage(5V or 3.3V) into integer values between 0 and 1023
● Rescale to the potentiometer's angle by using the float map() function.
● Rescale to the potentiometer's voltage:
● Serial. print() is used to print the value, print Analog, and then analog value, voltage
● Serial.printIn(volage*1000) is used to show voltage in terms of 1.00

Output:
Compile and upload the program to ESP32 board using Arduino IDE
● Verify the program on clicking Tick option
● Upload the program on clicking arrow option

Note: If the port is not selected, insert the USB cable in Computer’s port and select the port
● Go to Tools and select Serial Monitor
● Rotate the potentiometer and see the output
By rotating the potentiometer knob, the voltage value will rise or fall.
