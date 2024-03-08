EXPERIMENT-NO--03-PRESSURE-MEASUREMENT-USING-ARDUINO-AIM-To-interface-an-FSR-force-sensitive-resistor
DATE : 08-03-2024
NAME : HEMADHARSHINI M
ROLLNUMBER : 212222040053
DEPARTMENT : BE CSE
AIM:
To interface an FSR(force sensitive resistor) and scale the output voltage obtained to pressure applied

COMPONENTS REQUIRED:
FSR (force sensitive resistor)
1 KΩ resistor
Arduino Uno
USB Interfacing cable
Connecting wires
THEORY:
FSRs are basically a resistor that changes its resistive value (in ohms Ω) depending on how much it is pressed. These sensors are fairly low cost, and easy to use. They also vary some from sensor to sensor perhaps 10%. FSR's resistance changes as more pressure is applied. When there is no pressure, the sensor looks like an infinite resistor (open circuit), as the pressure increases, the resistance goes down. This graph indicates approximately the resistance of the sensor at different force measurements.

image

FIGURE 01 GRAPH OF FORCE vs RESISTANCE **
image

FIGURE 02 FORCE SENSITIVE RESITOR FOIL DISC TYPE
FSRs are often a polymer with conductive material silk-screened on. That means they're plastic and the connection tab is crimped on somewhat delicate material. The best way to connect to these is to simply plug them into a breadboard.

The easiest way to measure a resistive sensor is to connect one end to power and the other to a pull-down resistor to ground. Then the point between the fixed pull down resistor and the variable FSR resistor is connected to the analog input of a microcontroller such as an Arduino The way this works is that as the resistance of the FSR decreases, the total resistance of the FSR and the pull down resistor decreases from about 100Kohm to 10Kohm. That means that the current flowing through both resistors increases which in turn causes the voltage across the fixed 10K resistor to increase.

image

TABLE -01 FORCE AND OUTPUT VOLTAGES**
Table -01 indicates the approximate analog voltage based on the sensor force/resistance w/a 5V supply and 10K pull down resistor.

Vo = Vcc ( R / (R + FSR) ) Eq-01
****Where R= 1KΩ in this experiment ****That is, the voltage is proportional to the inverse of the FSR resistance.

image

FIGURE-03 CIRCUIT DIAGRAM
OFF:
image

ON:
image

SCHEMATIC DIAGRAM:
image

PROCEDURE:
Connect the circuit as per the circuit diagram
Connect the board to your computer via the USB cable.
If needed, install the drivers.
Launch the Arduino IDE.
Select the board (If you the board is arduino uno, select accordingly).
Select your serial port, accordingly ( E.g. COM5 )
Open the file of the program and verify the error , clear if any errors that are existing
Upload the program and check for the physical working.
Ensure safety before powering up the device
Plot the graph for the output voltage vs the resistance
PROGRAM
int LED=7;
int FSR;
void setup()
{
 pinMode(LED,OUTPUT);
 Serial.begin(9600);
}
void loop()
{
 FSR =analogRead(A0);
 Serial.print("RAW VALUE=");
 Serial.println(FSR);
 delay(500);
 int m;
 m=map(FSR,0,159,0,10);
 Serial.print("mapped value=");
 Serial.println(m);
 if(FSR>50)
 {
   digitalWrite(LED,LOW);
   delay(500);
   digitalWrite(LED,HIGH);
   delay(500);
 }
}
image

Figure 04 COMPARISION OF APPLIED AND MAPPED FORCES
image

Population Standard Deviation
The population standard deviation, the standard definition of σ, is used when an entire population can be measured, and is the square root of the variance of a given data set. In cases where every member of a population can be sampled, the following equation can be used to find the standard deviation of the entire population:

Where xi is an individual value μ is the mean/expected value N is the total number of values

For those unfamiliar with summation notation, the equation above may seem daunting, but when addressed through its individual components, this summation is not particularly complicated. The i=1 in the summation indicates the starting index, i.e. for the data set 1, 3, 4, 7, 8, i=1 would be 1, i=2 would be 3, and so on. Hence the summation notation simply means to perform the operation of (xi - μ)2 on each value through N, which in this case is 5 since there are 5 values in this data set.

CALCULATION
	  
μ = (1+3+4+7+8) / 5 = 4.6        
σ = √[(1 - 4.6)2 + (3 - 4.6)2 + ... + (8 - 4.6)2)]/5
σ = √(12.96 + 2.56 + 0.36 + 5.76 + 11.56)/5 = 2.577
RESULTS :
Arduino uno is interfaced with FSR and output values are indicated on a graph.


 
 
 
 
 
 
 
 
 
 
