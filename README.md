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



--------------------------------------------------------------------------------------------------------------------------------------------------------------------

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

### Idea Of The Code :
General :
Pressing the remote buttons will send a signal to the IR sensor , which will be translated through the code to any action we want.
I programmed 6 buttons to present a simple example :

button 1 : will turn blue led ON for 0.5 sec.
button 2 : will turn green led ON for 0.5 sec.
button 3 : will turn orange led ON for 0.5 sec.
button 4 : will turn all LEDs ON (from left to right) , each for 0.5 sec.
button 5 : will turn all LEDs ON, green first then the other two , each for 0.5 sec.
button 6 : will turn all LEDs ON (from right to left) , then it will all go OFF together.

Explaining The Code :
1 - Pins

Connecting the LEDs to pins 8 , 9 and 10.
Connecting the IR sensor to pin 3.
int BlueLed = 10;
int GreenLed = 9;
int OrangeLed  = 8;

int RECV_PIN = 3;
2 - Initializing
Librarary lines :

define the input pin that connected to the IR sensor.
assigning a "true" value to the variable results (if any signal is received , a "true" value will come up)
IRrecv irrecv(RECV_PIN);
decode_results results;
set up

Initializing status of each used pins for all LEDs (all OUT for sure).
Starting the serial monitor to see the input value changes on the screen. will need this absolutely to know the value of each button , to determine the cases in the code.
also , printing the string in the serial monitor to indicate when it's started.
void setup()
{
  //Set Led Pins
  pinMode(BlueLed, OUTPUT);
  pinMode(GreenLed, OUTPUT);
  pinMode(OrangeLed   , OUTPUT);
  
  
  //Enable serial usage and IR signal in
  Serial.begin(9600);
  Serial.println("Enabling IRin");
  irrecv.enableIRIn(); 
  Serial.println("Enabled IRin");
}
3- Main Code / Loop in simple & breif words :

Using an if which will will check if there is signal coming from the remote , if yes then assign its value to variable value.
compare the value of value with the written cases , if any match , then run it. (all cases mentioned previously)
void loop()
{
  if (irrecv.decode(&results)) {//irrecv.decode(&results) returns true if anything is recieved, and stores info in varible results
    unsigned int value = results.value; //Get the value of "results" as an unsigned int, so we can use switch case
    Serial.println(value);
    switch (value) {
      case 2295: 
      digitalWrite(BlueLed , HIGH);
      delay(500);
      digitalWrite(BlueLed , LOW);
      break;   

      case 34935:
      digitalWrite(GreenLed  , HIGH);
      delay(500);
      digitalWrite(GreenLed  , LOW);
      break;
      
      case 18615:
      digitalWrite(OrangeLed , HIGH);
      delay(500);
      digitalWrite(OrangeLed   , LOW);
      break;
      
      // 3 more cases , no need to present them ... it's too long to be showed & nothing new
      
    
    }
    irrecv.resume(); // Receive the next value
  }
}
--------------------------------------------------------------------------------------------------------------------------------------------------------------

### Practical application in Jeddah headquarters with Eng. Shoroug:

---
https://user-images.githubusercontent.com/103388162/186001466-dd472678-951e-481a-bdf9-755931baa751.mp4



