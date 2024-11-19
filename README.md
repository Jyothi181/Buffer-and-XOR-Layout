# Buffer-and-XOR-Layout
This repository explains the layout of a buffer and XOR using Glade. Here, Buffer and XOR are implemented in CMOS logic. It primarily focuses on the layout design and check for the DRC errors if any exist. 

# Table of Contents

- Introduction  
- Objectives
- Project Structure  
- Circuit Details
- Buffer
- XOR
- Stick Diagram
- Layer information through colour codes
- Layer information through Monochrome Encoding
- Layouts
- Initial Setup
- Steps to create Layout
- Layout of CMOS Buffer
- Layout of XOR
- Verification
- Extraction of Layout


# Introduction

**Buffer:** A digital buffer/logical buffer is an electronic circuit whose output is same as the input
- Buffers are used to introduce delays in the circuit
- It isolates one circuit from another
- To increase the fanout of the circuit
- To match the impedances between two circuits
- To prevent signal distortions and power loss
- To use it as repeaters

**XOR Gate:** It is an Exclusive OR gate. It takes two inputs and produces an output which is the result of the exclusive OR operation performed on the combination of inputs. This logic gate produces a high or logic 1 output when both of the inputs are dissimilar, otherwise, it produces a logic 0 output. XOR gate hass several applications including data encryption, error detection and correction, arithmetic operations and magnitude comparision.

**CMOS:** Complementary metal–oxide–semiconductor (CMOS) is a type of MOSFET that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. Input is applied at the common gate of PMOS and NMOS transistors.Output is taken from the PMOS and NMOS drain. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits. Two important characteristics of CMOS devices are high noise immunity and low static power consumption.

**PMOS:** The PMOS transistor is a p-channel device. It conducts current when a negative voltage (logic low) is applied to its gate terminal with respect to the source terminal. In CMOS, PMOS acts as pull up network in which the source is connected to VDD. When logic low(0) is applied is CMOS, the PMOS transistor turns on and connects the VDD to output which makes the output to logic high(1).

**NMOS:** The NMOS transistor is an n-channel device. It conducts current when a positive voltage (logic high) is applied to its gate terminal with respect to the source terminal. In CMOS, MMOS acts as pull down network in which the source is connected to ground. When logic high(1) is applied is CMOS, the NMOS transistor turns on and connects the output to ground which makes the output to logic low(0).

# Objectives
The main goals of this project are given below

- To design the layout of buffer and XOR Gate
- To verify the DRC errors

# Project Structure

- **Tool** : Glade 
- **Technology** : C5N technology
- **Buffer_layout** : Glade Layout File for Buffer.
- **XOR_layout** : Glade Layout File for XOR Gate.

# Circuit Details

## Buffer

From the truth table, the buffer produces a high(1) output when input A is 1, a low(0) output when input A is 0. The logic symbol and truth table of buffer is shown below.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture36.png)     ![image](https://github.com/Jyothi181/Pictures/blob/main/Picture37.png)

***Figure 1: Logic Symbol, Truth table and Logic Circuit of buffer***

## XOR Gate

From the truth table, the XOR gate produces a high(1) output when the inputs A and B are different, and a low(0) output when the inputs are the same. The logic symbol and truth table of buffer is shown below.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture38.png)     ![image](https://github.com/Jyothi181/Pictures/blob/main/Picture39.png)

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture40.png)

***Figure 2: Logic Symbol, Truth table and Logic Circuit of XOR***

## Stick Diagram

- Before fabrication of any IC, the designer prepares the layout of the IC. To draw the layout, one has to captures the complete structure of the circuit, layers used, type of topology. To capture all these information, stick diagram is used.

- VLSI aims to translate the circuit concepts onto the silicon.Stick diagrams are the means of capturing topography and layer information. Stick diagrams are convey layer information through colour codes (or monochrome encoding)

- There are 4 layers : N diffusion, P diffusion, poly silicon and metal

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


![image](https://github.com/Jyothi181/Pictures/blob/main/Picture41.png)

***Figure 3: Stick Diagram of buffer***

# Layouts

- Glade Interface Designer is a graphical user interface builder for GTK, with additional components for GNOME.
- Toolbar -> Library browser, LSW
- Library browser – All created libraries can be viewed and accessed.
- LSW – All metal layers and contacts are picked up from this toolbar.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture42.png)

***Figure 4: LSW window*** 

## Initial Setup
Choose the settings for project window.
- Initially activate the library browser
- All settings can be done in view option of the tool bar.
- View -> 
   - `Display options -> Display settings -> Display Grid – Dotted`  `Display Grid settings -> major -4 and minor 0.3`
   - Because in C5N technology file, length is 0.6um and width is 1.8um and lambda is l/2 so, 0.3um is set.
   - `Display options -> Snap settings -> snap Grid X and Y as 0.3`
   - `Display options -> Miscellaneous -> Uncheck the always pop up option dialogs`
- Between two minor nodes l is 0.3um and between two major grids l is 1.2um
- Minimum length is 2lambda = 6um
- Minimum width is 1.8um

## Steps to create Layout

### Layout of CMOS Buffer

- To create a new file in glade, select new library and new cell as mentioned.
- To create a new library => `File -> Newlib` -save as Inverter_demo – C5N.tch(Technology library)
- To create new cell => `File -> Newcell` – save as buffer
- Draw the active layer of length – **0.3 * 20 = 6um** and width - **0.3 * 6 = 1.8um**
- Minimum size of polysilicon is length should be 2lambda or the length of transistor.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture43.png)  

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture44.png)

***Figure 5: substrate layout***

- Draw the NMOS transistor width of 3.6um
- Minimum separation of nwell from the active region is 6lamda
- Minimum sizing of via should be 2lambda*2lambda
- Minimum sizing of poly contact is 2lambda * 2lambda
- Draw the PMOS transistor width of 7.2um.
- PMOS width should be twice of the NMOS width
- Draw the Nwell for the pmos structure

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture45.png)    ![image](https://github.com/Jyothi181/Pictures/blob/main/Picture46.png)

***Figure 6: nmos and pmos layout***

Make the connections by using metal layers and connect the input and output. The buffer is formed by connecting two inverters.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture47.png)

***Figure 7: Layout of Buffer***

## Layout of XOR

- To create a new file in glade, select new library and new cell as mentioned.
- To open an existing library => `File -> Open Lib` and open Inverter_demo library
- To create new cell => `File -> Newcell` – save as xor

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture48.png)

***Figure 8: Layout of XOR***

# Verification
- Once the layout is done, check the DRC(Design Rule Checks) errors
`Verify DRC – Run DRC - select C5N_DRC.py and run`
- Both the layouts are done with no DRC errors.

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture49.png)

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture50.png)

***Figure 9: DRC checks of Buffer and XOR***

# Extraction of Layout

Extract the layout by using below options
`Verify -> extract – Run LPE select`


![image](https://github.com/Jyothi181/Pictures/blob/main/Picture51.png)

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture52.png)

***Figure 10: Extraction of Buffer and XOR***

