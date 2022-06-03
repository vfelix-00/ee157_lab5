# Lab 5: Working with Stepper Motors

Vanessa Felix 

Lab Partner: Vivian Auduong

## Overview

In this lab, the objectives were to measure the winding configuration of our stepper motor, measure the back-EMF of our stepper motor, generate a schematic that enables the Toshiba TB6674PG to drive the stepper motor, and to wire the circuit and generate the code that will drive our stepper motor in both clockwise (CW) and counterclockwise (CCW) directions.

In this lab the major themes were to learn about stepper motor construction, learn how to read a datasheet and generate a schematic diagram, and learn how to program an Analog Discovery 2 so that it could drive a stepper motor.

## Introduction 

We started off by making sure we understood how the internal windings of the stepper motor were connected. We did this by measuring the resistance between different colored wires using a digital multimeter. 

| Wires | Resistance (ohms) |
| ------|---------------|
| Red to Green | 0 |
| Red to Blue | 20 ohms |
| Red to Black | 0 |
| Black to Green| 21 ohms|
| Black to Blue | 0 |
| Green to Blue | 0 |

Given this table, we concluded that the red to blue and green to black wires were connected, while the red to green, the red to black, black to blue, and green to blue were not connected. With this information in hand, we drew a diagram of what the winding pattern seemed to be.

![EE+157_Lab_5](https://user-images.githubusercontent.com/71578472/171357926-6cb5f8bf-7f1a-448a-860f-3dd3af5ff324.jpeg)
Figure: Stepper motor schematic

## Captured back-EMF waveforms

We then captured the back-EMF of the stepper motor. We did this by connecting 2 voltage scopes to the red to blue and green to black wire pairs and then capturing the spin-down voltage of the motor as depicted below. 

<img width="700" alt="back-EMF of stepper motor" src="https://user-images.githubusercontent.com/71578472/171360233-0c26bdcb-3e02-4340-a3b7-374ad54d5b71.png">
Figure: Back-EMF waveform of the stepper motor via a scope capture 

From this capture and peak value of the back-emf waveform, we estimate the back-emf voltage to be around 14.61 V.

## Generating our circuit schematic

We implemented one of the simplest ways to drive stepper motors. In this simple stepper motor application, we did not try to control the current or voltage. Stepper motors are not designed for efficiency, but rather for holding torque.

The Toshiba TB6674PG Stepping Motor Driver IC we used did not have a bunch of logic circuitry. Its major functionality was to provide H-bridges implemented in 130nm BiCD MOS along with some “protection” diodes and over-current / over-temperature circuitry. 

We reviewed the datasheet for the TB6674PG, once we were familiar with all the pins and how they should be connected / configured, we drew out the schematic we planned to implement.  

![EE+157_Lab_5-4](https://user-images.githubusercontent.com/71578472/171797809-1a6309de-7874-478f-9924-21e12ebb83a3.jpeg)
Figure: Circuit schematic of Toshiba TB6674PG chip, power supply, passive components, and stepper motor

Before plugging it into the power supply, we confirmed the electrical connectivity with a handheld DMM to save debugging time as well as burnt ICs.

## Generating the logic signals

The TB6674PG will need two digital signals to control the state of each full bridge module on the chip. We need one signal for the IN A pin and one signal for the IN B pin. To supply these signals, we used the Analog Discovery 2 with the Waveforms software. Following the guidelines of the datasheet, we created digital patterns for our motor. The timing sheet also shows us that PS should be low voltage.

<img width="527" alt="Toshiba TB6674PG chip " src="https://user-images.githubusercontent.com/71578472/171724207-eb278d10-6a2c-49b5-869b-5484bc4c0544.png">
Figure: Sample timing chart from Toshiba TB6674PG chip with signal A and signal B 90 degrees out of phase

## Results 

### A short video of our motor turning one direction, AND a short video of our motor turning the other direction.


![IMG_3196-1](https://user-images.githubusercontent.com/71578472/171789468-94166eff-aea2-4946-98ec-f10129b9fd95.gif)


Figure: Video of our motor turning clockwise with digital signals' frequencies of 1 kHz.

![IMG_3195-1](https://user-images.githubusercontent.com/71578472/171790654-7b7ae943-3da4-461e-917a-32a4b723d4d7.gif)


Figure: Video of our motor turning counterclockwise with digital signals' frequencies of 1 kHz.

I converted the videos into Gifs because the embedded video was not loading.

### A screenshot of the waveforms you used to turn the motor in each direction


<img width="969" alt="Waveform patterns to turn motor clockwise" src="https://user-images.githubusercontent.com/71578472/171792089-127a9b73-3e26-48b5-957c-67c6c37ef56d.png">
Figure: Clockwise waveform patterns


<img width="965" alt="Waveform patterns to turn motor counterclockwise" src="https://user-images.githubusercontent.com/71578472/171792219-79650adc-4750-47d1-845f-ba98e7987c78.png">
Figure: Counterclockwise waveform patterns

## Conclusion

 

