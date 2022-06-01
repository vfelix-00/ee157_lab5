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


