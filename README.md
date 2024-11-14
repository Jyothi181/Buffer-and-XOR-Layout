# Buffer-Layout
This repository explains the layout of a buffer using Glade. Here, Buffer is implemented in CMOS logic. It primarily focuses on the layout design and check for the DRC errors if any exist. 

# Table of Contents

- Introduction  
- Objectives
- Project Structure  
- Circuit Details
- Stick Diagram
- Layer information through colour codes
- Layer information through Monochrome Encoding
- Simulation  
- Results  


# Introduction
A digital buffer/logical buffer is an electronic circuit produces the output which exactly matches the input. A digital buffer can be implemented in CMOS logic.

Complementary metal–oxide–semiconductor (CMOS) is a type of MOSFET that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. Input is applied at the common gate of PMOS and NMOS transistors.Output is taken from the PMOS and NMOS drain. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits. Two important characteristics of CMOS devices are high noise immunity and low static power consumption.

PMOS: The PMOS transistor is a p-channel device. It conducts current when a negative voltage (logic low) is applied to its gate terminal with respect to the source terminal. In CMOS, PMOS acts as pull up network in which the source is connected to VDD. When logic low(0) is applied is CMOS, the PMOS transistor turns on and connects the VDD to output which makes the output to logic high(1).

NMOS: The NMOS transistor is an n-channel device. It conducts current when a positive voltage (logic high) is applied to its gate terminal with respect to the source terminal. In CMOS, MMOS acts as pull down network in which the source is connected to ground. When logic high(1) is applied is CMOS, the NMOS transistor turns on and connects the output to ground which makes the output to logic low(0).

# Objectives
The main goal of this project are given below

To design the layout of buffer
To verify the DRC errors

# Project Structure

**Tool** : LTspice  
**Technology** : C5N technology

Glade Layout Files: Files with .asc extension represents LTspice simulation files for each logic gate. AND.asc : LTspice simulation file for the AND gate. OR.asc : LTspice simulation file for the OR gate. NOT.asc : LTspice simulation file for the NOT gate.

# Circuit Details
The output of AND gate produces 1 if and only if all the input states are 1 else it produces 0. The logic symbol and truth table of 2-input AND gate is shown below.

## Stick Diagram

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

## Layer information through Monochrome Encoding

| Layers | Encoding |
| ------ | -------|
| Metal | ........ |
| Poly silicon | ______ |
| n diffusion | -------- |
| p diffusion | _ _ _ _ _ |

# CIRCUIT DETAILS 

![image](https://github.com/user-attachments/assets/7e4bd363-c733-45fc-bb0a-5b58663e99c9)     ![image](https://github.com/user-attachments/assets/b5ffa1f4-f208-45f5-82fa-735b78d02481)

![image](https://github.com/user-attachments/assets/942fc757-d0f2-48ae-a9c0-c7288d9d2c07)




Glade Interface Designer is a graphical user interface builder for GTK, with additional components for GNOME.
Tools -> Activate Library browser, LSW
To create a new file in glade, select new library and new cell as mentioned.
File -> Newlib – C5N.tch(Technology library)
File -> Newcell – save as test file
After saving the test file, choose the settings for project window. 
All settings can be done in view option of the tool bar.
View -> 
Display options -> Display settings -> Display Grid – Dotted
			           		     Display Grid settings -> major -4 and minor 0.3 because in C5N technology file, length is 0.6um and width is 1.8um and lambda is l/2 so, 0.3um is set.
	                         Snap settings -> snap Grid x and y as 0.3
 	 	          Miscellaneous -> Uncheck the always pop up option dialogs
Between two minor nodes l is 0.3um and between two major grids l is 1.2um
Minimum length is 2lambda = 6um
Minimum width is 1.8um

Design of layout of CMOS Inverter

File -> Newlib -rename as Inverter_demo – C5N.tch(Technology library)
File -> Newcell – save as inverter

Active layer
Length – 0.3*20 = 6um
Width - 0.3*6 = 1.8um
Minimum size of polysilicon is length should be 2lambda or the length of transistor.

![image](https://github.com/user-attachments/assets/29a220ef-026f-4afd-958c-aad6a450979b)

![image](https://github.com/user-attachments/assets/0331e3f2-cb71-45e1-8eb2-b60d4b3c346a)

Minimum sizing of via should be 2lambda*2lambda
NMOS width of 3.6um and PMOS width of 7.2um 
PMOS width should be twice of the NMOS width

![image](https://github.com/user-attachments/assets/1070f32a-a8da-4561-bed2-35da691e3eef)

![image](https://github.com/user-attachments/assets/87b1fc2e-7a6b-4c7b-99f9-2005b6b7bc67)

![image](https://github.com/user-attachments/assets/4210b8bf-460a-4523-94c1-070dbd3b284b)

Nwell for the pmos structure
Min separation of nwell from the active region is 6lamda
Minimum sizing of poly contact is 2lambda * 2 lambda
Check the DRC Errors:
Verify DRC – Run DRC - select C5N_DRC.py and run
Verify -> extract – Run LPE select 


![image](https://github.com/user-attachments/assets/86b953b0-fc99-45bd-bc52-c7fd6de3f927)


![image](https://github.com/user-attachments/assets/38932941-1efc-4808-82cd-eaeb0f25817f)


![image](https://github.com/user-attachments/assets/b62c8caa-005e-4c94-9433-1334a4695d8c)

![image](https://github.com/user-attachments/assets/7c23046a-6c28-4a48-8485-ba43c2c6ee34)


![image](https://github.com/user-attachments/assets/8bf42874-bb30-4e26-aa63-9853abe2c844)


(https://github.com/Jyothi181/Basic-Gates-using-LT-Spice/tree/main?tab=readme-ov-file#steps-to-draw-schematics)

