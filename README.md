# EXPERIMENT-NO--05-Distance measurement using Ultrasonic sensor
# DATE : 08/03/2024
# NAME : CHANDRAMOHAN S
# ROLLNUMBER : 212221223002
# DEPARTMENT : INFORMATION TECHNOLOGY
## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 

![Screenshot 2024-03-08 160230](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/006870b1-fc87-468a-a8ab-8a755ddcb363)

![Screenshot 2024-03-08 155922](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/e345d2e2-0e80-4c84-a040-66e669af3c25)






### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
```
int echopin=6;
int trigpin=7;
int red=8;
int green=9;
long duration;
float distance;
void setup()
{
  pinMode(echopin,INPUT);
  pinMode(trigpin,OUTPUT);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  digitalWrite(trigpin,LOW);
  delay(10);
  digitalWrite(trigpin,HIGH);
  delay(10);
  digitalWrite(trigpin,LOW);
  duration=pulseIn(echopin,HIGH);
  distance=duration*0.034/2;  //0.034=velocity of sound
  Serial.print("distance=");
  Serial.print(distance);
  Serial.println("cms");
  if(distance>50)
  {
    digitalWrite(green,HIGH);
    delay(500);
    digitalWrite(green,LOW);
    delay(500);
  }
  else
  {
    digitalWrite(red,HIGH);
    delay(500);
    digitalWrite(red,LOW);
    delay(500);
  }
}

```






### Distance vs measurement table 

![Screenshot 2024-03-08 155748](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/6ed9ba69-4682-4da2-bfc7-2a1927650f4d)

![Screenshot 2024-03-08 160411](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/3179ed29-a7f7-4598-a7ca-bd3a94562573)
Average error = sum/ number of readings 


### above 50cm:
![Screenshot 2024-03-08 162522](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/c0ff6456-c713-43d4-a5c3-4c6182f4a631)

### below 50cm:

![Screenshot 2024-03-08 162435](https://github.com/chandramohan3/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/142579775/1e458fe6-52ff-4c59-93a7-0ea648050c2b)


 








### RESULTS: The implementation of -Distance measurement using Ultrasonic sensor is successfully done



 
