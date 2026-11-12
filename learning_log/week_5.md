## Week 5
### Servo Motors
This week was all about servo motors.
Servo motors: 
works with gears, potentiometer, control unit, dc motor, servo horn, 
electrictiy= translates electricity into movement

there are screws with which you could screw the servo horn onto the motor, but that’s not necessarily a must.


#### Connecting a servo: 
```cpp
#include <Servo.h> // include servo library 
Servo myservo; // declaring a variable from the library (Class Servo) with the title 'mysevo'(Variable). Can also control multiple servos so naming them is good especially then.
void setup() {
  // put your setup code here, to run once:
myservo.attach(9);// attach myservo at pin 9 doesnt have to be a pwm pin
}

void loop() {
  for (int i=0; i<=180; i+-5 )//to make the turning slower
  myservo.write(i); // initiates the signal, needs a delay otherwise motor gets confused
  delay(200);
 // put your main code here, to run repeatedly:

}
delay (2000)
// zero and 180 may shift when you stop the motor while it is in the middle, 
```

#### We used two servo motors to explore how the can work together in 3 dimensions.
```cpp
 #include <Servo.h>
Servo servo1;
Servo servo2;

const int VRX = A0;
const int VRY = A1;
const int SW = 2;
int x = 0;
int y = 0;
int button = 0;
int servoValue1 = 0;
int servoValue2 = 0;




void setup() {
  servo1.attach(12);
  servo2.attach(10);
  delay (200);

  Serial.begin(9600);
  pinMode (SW,INPUT_PULLUP);
}
void loop (){

  x = analogRead(VRX);
  y = analogRead(VRY);
  button = digitalRead(SW);

  servoValue1 = map(x,0,1023,0,180);
  servoValue2 = map(y,0,1023,0,180);
  servo1.write(servoValue1);
  servo2.write(servoValue2);

  Serial.print ("x=");
  Serial.print (x);
    Serial.print ("y=");
  Serial.print (y);
  Serial.print("\t");//tab
  Serial.print(" ");
    Serial.print ("button");
 Serial.println (button);
```
