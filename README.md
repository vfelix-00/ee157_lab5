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

