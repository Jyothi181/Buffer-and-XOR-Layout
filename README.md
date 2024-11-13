# Buffer-Layout
This repository explains the layout of a buffer using Glade. Here, Buffer is implemented in CMOS logic. It primarily focuses on the layout design and check for the DRC errors if any exist. 

# Table of Contents

Introduction  
Objectives  
Circuit Details  
Simulation  
Results  


# INTRODUCTION
A digital buffer/logical buffer is an electronic circuit produces the output which exactly matches the input. A digital buffer can be implemented in CMOS logic.

Complementary metal–oxide–semiconductor (CMOS) is a type of MOSFET that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. Input is applied at the common gate of PMOS and NMOS transistors.Output is taken from the PMOS and NMOS drain. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits. Two important characteristics of CMOS devices are high noise immunity and low static power consumption.

PMOS: The PMOS transistor is a p-channel device. It conducts current when a negative voltage (logic low) is applied to its gate terminal with respect to the source terminal. In CMOS, PMOS acts as pull up network in which the source is connected to VDD. When logic low(0) is applied is CMOS, the PMOS transistor turns on and connects the VDD to output which makes the output to logic high(1).

NMOS: The NMOS transistor is an n-channel device. It conducts current when a positive voltage (logic high) is applied to its gate terminal with respect to the source terminal. In CMOS, MMOS acts as pull down network in which the source is connected to ground. When logic high(1) is applied is CMOS, the NMOS transistor turns on and connects the output to ground which makes the output to logic low(0).

# OBJECTIVES
The main goal of this project are given below

To design the layout of buffer
To verify the DRC errors

# PROJECT STRUCTURE

**Tool** : LTspice  
**Technology** : C5N technology

Glade Layout Files: Files with .asc extension represents LTspice simulation files for each logic gate. AND.asc : LTspice simulation file for the AND gate. OR.asc : LTspice simulation file for the OR gate. NOT.asc : LTspice simulation file for the NOT gate.

CIRCUIT DETAILS
The output of AND gate produces 1 if and only if all the input states are 1 else it produces 0. The logic symbol and truth table of 2-input AND gate is shown below.

# STICK DIAGRAM

- Before fabrication of any IC, the designer prepares the layout of the IC. To draw the layout, one has to captures the complete structure of the circuit, layers used, type of topology. To capture all these information, stick diagram is used.

- VLSI aims to translate the circuit concepts onto the silicon.Stick diagrams are the means of capturing topography and layer information. Stick diagrams are convey layer information through colour codes (or monochrome encoding)

- There are 4 layers : N diffusion, P diffusion, poly silicon, metal

## Layer information through colour codes

| Layers | Colors |
| ------ | -------|
| Metal | blue |
| Poly silicon | red|
| n diffusion | green |
| p diffusion | yellow |
| via | black |

## Layer information through Monochrome encoding

| Layers | Encoding |
| ------ | -------|
| Metal | ........ |
| Poly silicon | ______ |
| n diffusion | -------- |
| p diffusion | _ _ _ _ _ |

# CIRCUIT DETAILS 

![image](https://github.com/user-attachments/assets/49dc9989-dadc-42d0-becf-9695dd3626f4)

![image](https://github.com/user-attachments/assets/2d88eff0-a88a-4be8-8bc7-2dfb1172c2b9)

![image](https://github.com/user-attachments/assets/942fc757-d0f2-48ae-a9c0-c7288d9d2c07)




