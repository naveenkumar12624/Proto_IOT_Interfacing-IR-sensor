# EX.NO-05 - Interfacing-IR-sensor

##  AIM:
To Interface the IR sensor module with Arduino UNO controller.

## Components required:
Arduino IDE </br>
Jumper wires </br>
Bread board </br>
IR sensor module </br>
LED </br>

## PROCEDURE:
### Arduino IDE
Step1:Open the Arduino IDE </br>
Step2: Go to file and select new file option </br>
Step3:Type the program </br>
Step4:Go to file and select save option to save the program </br>
Step5:Go to sketch and select verify or compile options </br>
Step6:If no error Hex file will be generated in the temporary folder </br>

## THEORY:

An infrared proximity sensor or IR Sensor is an electronic device that emits infrared lights to sense some aspect of the surroundings and can be employed to detect the motion of an object. As this is a passive sensor, it can only measure infrared radiation. This sensor is very common in the electronic industry and if you’ve ever tried to design an obstacle avoidance robot or any other proximity detection-based system.

### IR Sensor Pinout

The IR sensor has a 3-pin connector that interfaces it to the outside world. The connections are as follows:

![image](https://github.com/anishkumar-Embedded/Interfacing-IR-sensor/assets/71547910/21d42151-d3ac-49e8-83bf-863753120c6f)

VCC  is the power supply pin for the IR sensor which we connect to the 5V pin on the Arduino.

OUT pin is a 5V TTL logic output. LOW indicates no motion is detected; HIGH means motion is detected.

GND Should be connected to the ground of the Arduino

### How Does an IR Motion Sensor Module Work?

The working of the IR sensor module is very simple, it consists of two main components: the first is the IR transmitter section and the second is the IR receiver section. In the transmitter section, IR led is used and in the receiver section, a photodiode is used to receive infrared signal and after some signal processing and conditioning, you will get the output.

![image](https://github.com/anishkumar-Embedded/Interfacing-IR-sensor/assets/71547910/56fac58f-ea00-4f57-ba6f-1ceeda4ef437)

An IR proximity sensor works by applying a voltage to the onboard Infrared Light Emitting Diode which in turn emits infrared light. This light propagates through the air and hits an object, after that the light gets reflected in the photodiode sensor. If the object is close, the reflected light will be stronger, if the object is far away, the reflected light will be weaker. If you look closely toward the module. When the sensor becomes active it sends a corresponding Low signal through the output pin that can be sensed by an Arduino or any kind of microcontroller to execute a particular task. The one cool thing about this module is that it has two onboard LEDs built-in, one of which lights on when power is available and another one turns on when the circuit gets triggered.

### IR Motion Sensor Module – Parts

For most of the Arduino projects, this sensor is used to detect proximity or to build obstacle avoidance robots. This Sensor is popular among beginners as these are low power, low cost, rugged, and feature a wide sensing range that can be trimmed down to adjust the sensitivity.

![image](https://github.com/anishkumar-Embedded/Interfacing-IR-sensor/assets/71547910/900efe19-3953-4492-9403-042bdf6c3413)

This sensor has three pins two of which are power pins leveled VCC and GND and the other one is the sense/data pin which is shown in the diagram above. It has an onboard power LED and a signal LED the power LED turns on when power is applied to the board the signal LED turns on when the circuit is triggered. This board also has a comparator Op-amp that is responsible for converting the incoming analog signal from the photodiode to a digital signal. We also have a sensitivity adjustment potentiometer; with that, we can adjust the sensitivity of the device. Last and finally, we have the photodiode and the IR emitting LED pair which all together make the total IR Proximity Sensor Module.

## PROGRAM:
```
#define IR_sensor 8
#define LED 13
int IR_value;
void setup ()
{
  pinMode (IR_sensor, INPUT);
  pinMode (LED, OUTPUT);
  Serial. begin (9600) ;
}
void loop ()
{
  IR_value=digitalRead (IR_sensor);
  if (IR_value==0)
  {
    digitalWrite (LED, HIGH);
    Serial.print ("\nSensor Value: ");
    Serial.print (IR_value);
    Serial.println("Person Detected: ");
    delay (1000);
  }
else
{ 
  digitalWrite(LED, LOW);

  Serial.print("\nSensor Value: ");

  Serial.print(IR_value);

  Serial.println("Person Not Detected: "); delay(1000);
 }
}
```
## CIRCUIT DIAGRAM:
![image](https://github.com/VarshaAjith1110/Interfacing-IR-sensor/assets/94222288/4e1ebf79-9856-4252-8cd5-09c74381c358)

## OUTPUT:
![image](https://github.com/VarshaAjith1110/Interfacing-IR-sensor/assets/94222288/f0cc366f-ffdd-4654-8ed9-43a6dfa15f57)

## RESULT:
Thus the IR sensor module is interfaced with Arduino UNO controller and output is verified.
