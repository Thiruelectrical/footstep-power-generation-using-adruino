\\Features

*Step detection using piezoelectric discs  
*Voltage monitoring from footstep energy  
*Real-time display on 16x2 I2C LCD  
*LED indicator on each step  
*Modular code design (user.c, user.h)

\\Hardware Components

| Component               | Quantity |
|-------------------------|----------|
| Arduino Uno             | 1        |
| 35mm Piezo Disc         | 6        |
| IN4007 Diode            | 4        |
| 10µF Capacitor          | 1        |
| 10kΩ Resistor           | 2        |
| 100kΩ Resistor          | 1        |
| BC547 Transistor        | 1        |
| 16x2 LCD with I2C       | 1        |
| LED Strip (Raindrop)    | 1        |
| 18650 Cell Holder       | 1        |
| 9V Battery (HW)         | 1        |
| Mini Breadboard (400pt) | 1        |
| Wires, Connectors       | As needed |


\\Circuit Diagram

*A full circuit diagram is available in the project folder  
*(e.g., Footstep_Power_Circuit.png)



\\How to Use

*Connect all components as per the circuit diagram.
*Load the main.ino sketch in the Arduino IDE.
*Ensure user.c and user.h are in the same folder.
*Compile and upload the sketch.
*Step on the piezo discs and observe step count and voltage on the LCD.



\\Libraries Used

*LiquidCrystal_I2C.h
*Wire.h
*Install them via Library Manager in Arduino IDE.

\\Algorithm

*Initialize LCD and Serial monitor  
*Continuously read analog value from piezo input  
*If value crosses a threshold and was previously 0 → increment step count  
*Calculate voltage from analog value  
*Display step count and voltage on LCD  
*Blink LED on each step

\\Notes

* Arduino IDE requires .ino file to match folder name exactly.
* You **cannot open .c or .h directly**—they must be in the same sketch folder and get compiled automatically


\\Author

Designed by an aspiring embedded systems engineer  


\\Problem facing 

Hardware problems

*Low Power Output	Piezoelectric discs generate only a small amount of voltage and current, not enough to power heavy loads. 
Boost converters are usually needed.
*Component Damage	Piezo discs are fragile and can crack under excessive pressure or improper mounting.
*Unstable Output	The voltage from piezo is AC and very inconsistent. Without a proper bridge rectifier and capacitor filter, 
*it may damage the Arduino or give erratic readings.

Real-World / Practical Problems

*Not Scalable	The energy output from footsteps is too low to charge large batteries or power homes. 
*It can only charge small devices like an LED or mobile phone.
*Uneven Force Distribution	If the pressure is not applied uniformly on all piezo discs, energy generation becomes inconsistent.
*Weatherproofing	The system must be protected from dust, water, or other environmental factors if used outdoors.

Solutions 

*Use step-up converters boost converters to increase output voltage.
*Add supercapacitors or rechargeable batteries for energy storage.
*Use more efficient diodes like Schottky to reduce voltage drop.
*Ensure proper pressure distribution plate above the piezo layer.
*Use solid casing and moisture protection for outdoor use.
