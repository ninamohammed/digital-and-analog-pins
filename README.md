# digital-and-analog-pins

 Task, Electric: Design and programming of an electronic circuit for a sensor of two types, Analog & Digital
 
 #### More information on the topic can be found here:
 
*  https://www.circuito.io/blog/arduino-uno-pinout/#:~:text=The%20Arduino%20Uno%20pinout%20consists,LEDs%2C%20reading%20sensors%20and%20more.

#### The difference between digital and analog:

* https://thecustomizewindows.com/2018/05/difference-between-analog-and-digital-pins-in-arduino-uno/
----------------------------------------

### Tools:

* Arduino board
* breadBoard
* Jumper wires
* Potentiometer
* Led
* Resistor
* bush button

### Circuit layout:

![digital   analog](https://user-images.githubusercontent.com/103388162/186000041-274dd270-38e0-4f38-863f-06eba434cfbf.jpeg)

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

#### Practical application in Jeddah headquarters with Eng. Shoroug:

-------


https://user-images.githubusercontent.com/103388162/186001466-dd472678-951e-481a-bdf9-755931baa751.mp4



