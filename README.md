# Lab-5-Report

**Names of People Involved (Group Members):**  
Faith Cox & Quinn Rison 

**Date Submitted:**  
3/5/2025

---

## Introduction / Summary

This lab aims to introduce the basics of using microcontrollers, specifically through the Arduino platform. Participants will use the Arduino IDE software to program and upload code to the RedBoard controller from the SparkFun inventor’s kit. The lab involves controlling an LED's intensity using a timer, comparing circuit, and Pulse Width Modulation (PWM). Arduino's extensive documentation and community support are valuable resources for troubleshooting.
The Arduino system includes both hardware and software, with different boards using various microcontrollers and peripherals. The lab also incorporates a photoresistor, which changes resistance based on light exposure. PWM is used to generate analog signals from digital codes by adjusting the duty cycle, allowing digital outputs to simulate analog signals effectively. This technique is crucial for controlling devices like LEDs.

---

## Methods / Tests
This lab exercise aims to familiarize participants with the Arduino IDE and RedBoard (Arduino UNO). The required components include a 330Ω resistor, an oscilloscope, a computer running Arduino IDE,  RedBoard, photoresistor, LED, 10 kΩ potentiometer, momentary button, and 10 kΩ resistors.
As always, before starting any lab, measure the resistances of the different resistors that will be used in the lab. This is important to confirm participants are using the correct resistor as well as to compare to the theoretical values or for calculations. The measured vs. expected resitances table is shown below:

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%201.jpg" width="500">
  <br>
  <b>Figure 1:</b> MEASURING TRUE RESISTOR MEASUREMENTS
</p>


| Expected Resistance (Ohms) | Measured Resistance (Ohms) |
|---------------------------|---------------------------|
| 330                       | 324.7                     |
| 10                        | 9.9                      |

**TABLE 1: Pre-Lab Resistance Measurements**

The first task involves uploading a program to blink an LED, converting analog inputs to digital signals, and understanding pulse width modulation. The first part of the task includes assembling the RedBoard and breadboard, connecting the RedBoard to the computer, selecting the correct board and COM port in the Arduino IDE, and downloading the blink program. 
Once the RedBoard and breadboard have been constructed as well as properly hooking the redboard up to the laptop and installing the blink program the first circuit can be constructed. 
The first circuit should look as follows:


<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Schematic%201.jpg" width="500">
  <br>
  <b>Schematic 1:</b> PART 1-SIMPLE LED CIRCUIT
</p>


<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%202.jpg" width="500">
  <br>
  <b>Figure 2:</b> PART 1-SIMPLE LED CIRCUIT ASSEMBLED
</p>


When running the blink program, record what it does. Analyze the code and try to understand what each section of the code is trying to accomplish. The provided code is shown below:

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Code%201.png" width="500">
  <br>
  <b>Code 1:</b> PART 1-PROVIDED CODE
</p>


The next task is going to involve controlling the LED with a potentiometer. To do so, the sample program "Analog Read Serial" will need to be opened and run on the Arduino. First, ensure the previous circuit remains intact and connect the potentiometer to power (5V and Ground) with the variable resistance pin connected to A0. Detailed instructions for this connection can be found in the program.
The circuit should look as follows:

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Schematic%202.jpg" width="500">
  <br>
  <b>Schematic 2:</b> PART 2- CIRCUIT WITH POTENTIOMETER
</p>

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%203.jpg" width="500">
  <br>
  <b>Figure 3:</b> PART 2- CIRCUIT THAT CONTROLS LED WITH POTENTIOMETER
</p>

Next, demonstrate the program's proper operation using the serial monitor, ensuring the Baud Rate is set to 9600bps. Finally, modify the code to control the LED, adjusting the blinking time based on the value read from the potentiometer.  The following code is the code that has been modified to meet these requirements:

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Code%202.png" width="500">
  <br>
  <b>Code 2:</b> PART 2- CODE FOR POTENTIOMETER CIRCUIT
</p>

The third task is now going to involve controlling the LED with a photoresistor. To start, the program from part 2 is modified by replacing the potentiometer with a photoresistor in series with a 10 kΩ resistor. The 5V pin is connected to the photoresistor, ground to the resistor, and A0 to the node between them. The analog input is connected to the node between the photodetector and the resistor. The circuit should look as follows: 

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Schematic%203.jpg" width="500">
  <br>
  <b>Schematic 3:</b> PART 3- CIRCUIT WITH POTENTIOMETER AND PHOTORESISTOR
</p>

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%203.jpg" width="500">
  <br>
  <b>Figure 3:</b> PART 3- CIRCUIT THAT CONTROLS LED WITH POTENTIOMETER
</p>

Different objects are used to block the light on the photoresistor to determine the minimum and maximum analog values detectable with this circuit. An if-else statement is used to turn on the LED only when the brightness sensed by the photoresistor is low, similar to how a night light operates.

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%204.jpg" width="500">
  <br>
  <b>Figure 4:</b> PART 3- CIRCUIT THAT CONTROLS LED WITH PHOTORESISTOR
</p>


<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%205.jpg" width="500">
  <br>
  <b>Figure 5:</b> PART 3- PAPER BLOCKING PHOTORESISTOR
</p>


<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%206.jpg" width="500">
  <br>
  <b>Figure 6:</b> PART 3- THUMB COVERING PHOTORESISTOR
</p>

The fourth part of the lab involves creating an LED dimmer using Pulse Width Modulation (PWM). The circuit from Part 2, which includes the potentiometer, is used again. The LED pin is changed to one that supports PWM. One of the PWM pins would be one of the pins on the right-hand side of the Arduino with a small line beside it. For example, -9, -6, -5, and -3 are all usable. 

The voltage from the potentiometer is read and mapped from a range of 0 to 1023 to a range of 0 to 255 using the map(value, fromLow, fromHigh, toLow, toHigh) function. This mapped value is then written to the LED pin using the analogWrite(pin, mappedvalue) function, allowing the LED brightness to be adjusted based on the potentiometer's position.

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Code%202.png" width="500">
  <br>
  <b>Code 2:</b> PART 4- LED DIMMER USING PWM CODE
</p>

---

## Results

In Part 1, the Blink program was successfully uploaded to the Arduino, making the built-in LED turn on for one second and off for one second in a continuous loop. Adjusting the delay to 11 milliseconds made the LED appear constantly illuminated due to the persistence of vision.

In Part 2, the difference between analog and digital signals was explored. Analog signals, such as sound waves and temperature values, vary smoothly over time, while digital signals have specific values, often binary 0 and 1. Adjusting the potentiometer affected the LED blinking rate, demonstrating how analog inputs can control digital outputs. The Serial Monitor Refresh rate changed with the potentiometer's position, showing faster blinks at lower values and longer delays at higher values.

In Part 3, replacing the potentiometer with a photoresistor allowed the LED to turn on and off based on light exposure. The LED responded immediately to changes in light, turning on when the photoresistor was covered and off when uncovered. This behavior was due to the threshold set in the code to turn on the LED if the photoresistor read below 600.


| Object           | Min Analog Value | Max Analog Value |
|-----------------|-----------------|-----------------|
| Finger         | 448             | 932             |
| Paper | 824             | 932             |

**TABLE 2: ANALOG VALUES FROM PHOTORESISTOR BLOCKAGES**

In Part 4, using PWM to control the LED brightness involved mapping the potentiometer's voltage range (0 to 1023) to a PWM value range (0 to 255). Increasing the pulse width made the LED brighter without flickering, while the period and frequency of the signal remained constant. This demonstrated the effectiveness of PWM in simulating analog output for controlling LED brightness.


<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%207.jpg" width="500">
  <br>
  <b>Figure 7:</b> PART 4- OSCILLOSCOPE RESULTS WHEN CONNECTED TO LED
</p>

<p align="center">
  <img src="https://github.com/faco229/Lab-5-Report/blob/main/Figure%208.jpg" width="500">
  <br>
  <b>Figure 8:</b> EXPLANATION OF INPUTS AND OUTPUTS
</p>
---

## Discussion
**Part 1**
After opening the blink program and downloading it to the Arduino there were two questions related to the provided code.
**a.	What does this program do?**

The Blink program makes the built-in LED on the Arduino board turn on for one second and then off for one second in a continuous loop.

**b.	What are the major sections of the computer program and what does each section do?**

Global Declarations: Defining variables and constants
Setup() function: Runs once at the start, used for initial setup.
Loop() function: Runs repeatedly, containing the main logic. It turns the LED on

**Discussion Question:**
Your LED flashes with a delay from the uploaded code. Decrease this delay (after both write instructions) until the LED just stops blinking—that is until the light is still blinking but appears to stay constantly illuminated. 

**c.	What is the value of your delay now?**

Delay(11) or 11 milliseconds. LED was technically blinking at this speed, but the human eye sees this as constant illumination. 

**d.	What field may this “persistence of vision” play a greater role in?**

Television and computer screens refresh their pixels very quickly, which means they rely on “persistence of vision” to seem like seamless illumination. 

**e.	Discuss this further in your lab report.**

The concept of persistence of vision explains why a rapidly blinking LED can appear to be continuously on when the blinking rate exceeds human detection, which is around 60 Hz or higher. This idea is used in modern display systems, optical illusions, and animations to create a smooth visual experience.


**Part 2**
**Discussion Question:** 
**a.	What is the difference between an analog and a digital signal?**

An analog signal is a continuous signal that varies smoothly over time. It holds an infinite amount of numbers within any given range.
Digital is a discrete signal that only has specific values, most often binary 0 and 1.

**b.	In your lab report, list a few examples of real-world examples that can be described by an analog signal. Likewise, what are the two states which can be conveyed by a digital signal?**

Analog signal examples:
-Sound waves
-Temperature values 
-Voltage readings in electric circuits

The two states digital signals can be conveyed are HIGH (1 or ON) and LOW (0 or OFF)

**c.	What happens to the Serial Monitor Refresh rate as you move the potentiometer to control the LED blinking time?**

When the potentiometer is closer to 0, the light blinks faster with less time in between each blink. As the potentiometer increases, the blinking delay is longer, and the light stays on longer.

**Part 3**
**Discussion Question:**

a.	Does the LED turn on immediately after blocking the light? What about when you remove the object blocking the light, does the LED turn off immediately? Why?
When we put our finger on the photoresistor, the light immediately turns on. When the object blocking the light is removed, the light immediately turns off. This is due to the threshold we set in our code to turn on if the serial monitor reads the photoresistor under 600. 

**Part 4**
**Discussion Question:**

Connect the oscilloscope to the LED pin and observe and record what happens to the signal and the LED brightness when you turn the knob of the potentiometer.
Pulse width gets bigger (changes the average of the whole signal) as LED gets brighter. Period and frequency stay the same. LED is not flickering, it is a constant light

---

## Conclusion

This lab served as an introduction to microcontrollers, particularly the Arduino RedBoard, and their ability to process both digital and analog signals for practical purposes and problems. Through various circuit implementations, we examined how microcontrollers utilize Pulse Width Modulation (PWM) to simulate analog outputs, how sensors (potentiometers and photoresistors) can influence external components, and how digital logic is applied in real-world electronics. The experiment highlighted the importance of persistence of vision when dealing with high-frequency LED blinking, displaying how rapid state changes can appear as continuous signals to the human eye. Additionally, working with both digital and analog signals reinforced the understanding that while digital signals operate with distinct HIGH and LOW states, analog signals offer a continuous range of values, which is crucial in sensor-based applications.

Beyond theoretical knowledge, this lab also emphasized practical troubleshooting, circuit assembly, and programming within the Arduino IDE. Measuring resistor values before circuit construction emphasized the importance of component testing to ensure accuracy in electronic designs. Modifying the provided Arduino codes helped enhance the understanding of coding structures, including the use of setup() and loop() functions. In addition, analyzing oscilloscope readings while adjusting PWM confirmed the role of duty cycles in controlling brightness levels. Overall, the lab effectively demonstrated how microcontrollers act as the "brain" of modern embedded systems, providing a foundation for more advanced electronic applications.


**Citations**

Introduction - Copilot. (2025). Summary of Arduino Microcontroller Lab. Retrieved from [Quinn’s conversation with Copilot].

Part of Methods - Copilot. (2025). Summary of Arduino Lab Exercise. Retrieved from [Quinn’s conversation with Copilot].

Copilot. (2025). Summary of Arduino Analog Read Serial Task. Retrieved from [Quinn’s conversation with Copilot].

Copilot. (2025). Summary of Arduino Photoresistor Task. Retrieved from [Quinn’s conversation with Copilot].

Copilot. (2025). Summary of Arduino LED Dimmer Task. Retrieved from [Quinn’s conversation with Copilot].

Copilot. (2025). Summary of Arduino Lab Discussion Questions. Retrieved from [Quinn’s conversation with Copilot].

Copilot. (2025). Summary of Arduino Lab Results. Retrieved from [Quinn’s conversation with Copilot].

SparkFun Electronics. (2024). Blink Example Code. Retrieved from https://www.sparkfun.com

---

*End of Lab Report*
