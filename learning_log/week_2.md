## Week 2

This week we learned more about computing the LED and also tried to use the RGB LED for the first time (which didn’t work for me, but I’ll try to make it work another time.)
We also learned about resistors and that from the colored bands on the resistor, one can see what amount of Ohm that are in there. Additionally we discussed Ohms law and series as well as parallel circuits.

#### Some of the code from class
I wanted it to look like a traffic light, but that would need some more refinements. I really liked working with the LEDs and thought about whether a piece of at using LEDs would be cool as a final project.

```cpp
const int redLED = 2;
const int yellowLED = 3;
const int greenLED = 4;
void setup() {
  pinMode(redLED, OUTPUT);
  pinMode(yellowLED, OUTPUT);
  pinMode(greenLED, OUTPUT);
  // put your setup code here, to run once:
}

void loop() {

  digitalWrite(redLED, HIGH); // on - 5v
  delay(500); // 1000 milisecond
   digitalWrite(redLED, LOW); // off - 0v
  delay(70);

  digitalWrite(yellowLED, HIGH); // on - 5v
  delay(500); // 1000 milisecond
   digitalWrite(yellowLED, LOW); // off - 0v
  delay(70); 

  digitalWrite(greenLED, HIGH); // on - 5v
  delay(500); // 1000 milisecond
  digitalWrite(greenLED, LOW); // off - 0v
  delay(70);

  digitalWrite(redLED, HIGH);
  delay(1000);

  digitalWrite(yellowLED, HIGH);
  delay (1000);

  digitalWrite(greenLED,HIGH);
  delay (1000);
  
  digitalWrite(redLED, LOW); // off - 0v
  delay(70);  
  digitalWrite(yellowLED, LOW); // off - 0v
  delay(70);  
  digitalWrite(greenLED, LOW); // off - 0v
  delay(70);
```
#### analogWrite vs. digitalWrite
digitalWrite can only have two states HIGH and LOW. AnalogWrite can control voltage (thus brightness for LED) more precisely.

analogWrite_ is in this code used to dim the lights in the
 lamps. With it, the input of voltage can be controlled. It is used, 
because the 'digitalWrite' only knows high and low = one and off.




https://github.com/user-attachments/assets/c0284531-730b-40bc-bd43-64123db0b62f

