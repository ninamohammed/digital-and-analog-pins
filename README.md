# digital-and-analog-pins

 Task, Electric: Design and programming of an electronic circuit for a sensor of two types, Analog & Digital
 
 ### Analog Sensor:
 
 it's a sensor that produces a continuous analog output , that can be even fractional numbers. The sensor we will use for our example is an LDR (light-dependent resistor) , which is a component that decreases resistance with respect to receiving luminosity (light) on the component's sensitive surface.
 

### Component List :

* Arduino UNO
* IR Sensor
* IR Remote
* 3 Pull Down Resistors (1 kΩ)
* 3 LEDs

### Circuit Diagram:

<img width="806" alt="analog" src="https://user-images.githubusercontent.com/103388162/187053262-5661407a-0bda-4f2c-a259-dc8c56595af1.png">


### The Code:

```
 
//Digital Analog Input 
 
#define buttonPin 8 
#define led1Pin 12 
#define potPin A5 #define led2Pin 11 bool buttonStatus; int potValue; 
int ledValue; 
 
void setup(){ 
  pinMode(led1Pin,OUTPUT);   pinMode(led2Pin,OUTPUT);   pinMode(buttonPin,INPUT); 
  pinMode(potPin,INPUT); 
} 
void loop(){ 
  buttonStatus = digitalRead(buttonPin); 
    if(buttonStatus == 0){ 
    digitalWrite(led1Pin,HIGH); 
    }else{ 
      digitalWrite(led1Pin,LOW); 
    } 
   
  potValue = analogRead(potPin);   ledValue = map(potValue,0,1023,0,255);   analogWrite(led2Pin,ledValue); 
   
  delay(100); 
} 
```

### Digital Sensor:

it's an electronic or electrochemical sensor, where data is digitally converted and transmitted. We will be using an IR (IR stands for Infra red) for this part.

### Component List :
* Arduino UNO
* IR Sensor
* IR Remote
* 3 Pull Down Resistors (1 kΩ)
* 3 LEDs
### Circuit Diagram:

<img width="709" alt="dig" src="https://user-images.githubusercontent.com/103388162/187053420-986afc7a-7762-4258-9494-9f6fb914abf9.png">


### Practical application in Jeddah headquarters with Eng. Shoroug:

---
https://user-images.githubusercontent.com/103388162/186001466-dd472678-951e-481a-bdf9-755931baa751.mp4



