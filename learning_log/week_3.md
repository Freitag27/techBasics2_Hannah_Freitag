## week 3:

This week we started new resistors. We worked with the oscilloscope and photoresistor, potentiometer and the tilt switch. We started using analogWrite, digitalWrite, for-loops and map() in C++.

notes: 

PWM: pulse width modulation (all PWM pins have tilde ~)

duty cycle: the proportion of “on time” in each cycle 

oscilloscope: device that measures voltage and displays it graphically

cant do analogWrite on pwm, only select pins can do that

**small demo, makes leds fade from dark to light:** 

```cpp
void setup() {
  // put your setup code here, to run once:
pinMode (3, OUTPUT)
}

void loop() {
  // put your main code here, to run repeatedly:
for (int i=0; i < = 255; i +=1)
analogWrite (3,i)
delay(50);
}

```

serial begin has to match the same speed as the board, so when there’s weird symbols, the speed of communication might be wrong.

```cpp
void setup() {
Serial.begin(9600);
delay(500);
Serial.println("Hello");
}

void loop() {
  // put your main code here, to run repeatedly:
delay(1000)
}

```

```cpp
const int tiltsensor = 2;
int value = 0;
void setup() {
pinMode(tiltSensor, INPUT);
Serial.begin(9600);
}

void loop() {
 value= dogotalRead(tiltSensor);
 Serial.println("Tilt sensor:"); 
 Serial.println(value);
 
}
```

input_pullup 

pull up resistor: resistor connecting to power source 

prevents floating pins: prevents pins from not being connected anywhere and thats why we want to use pull up or pull down resistors 

potentiometer: adjustable resistor, most common use case: volume adjustement

excersise 3 AnalogRead()

```cpp
const int pot = A0;
int value = 0;
void setup() {
pinMode(tiltSensor, INPUT_PULLUP);
Serial.begin(9600);
delay(500);
}

void loop() {
 value= dogotalRead(pot);
 Serial.println("pot:"); 
 Serial.println(value);
 
}

```

potentiometer shouldn’t get hot, otherwise there's something wrong

photoresistor: also called a light depended resistor: LDR , you can put your hand over it and the number will get smaller in he code
