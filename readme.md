# Intel SD Training

## Table of contents

* [ Day 0 - System/Tool Setup Check. GitHub ID creation ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-0)
* [ Day 1 - Introduction to Verilog RTL design and Synthesis ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-1)

## Day-0

### Topic: System/Tool Setup Check. GitHub ID creation

**What is package?**

It is the material that contains semiconductor device attached with a die using wire bonding. The chip is also correlated with the pads, core, macros and foundry IPs.

**Example of the package structure**

![image](https://user-images.githubusercontent.com/118953917/203911782-55c10619-7900-404e-9775-ef5f0ba97625.png)

**Pad**: surface mount of pins connected

**Core**: all NMOS and PMOS are in the core area

**Macros**: protocol to transfer data using simple codes and can be found online

**Foundry IPs**: has specific functionality and cannot be found online

###############################################################################################

**Communication of Software and Hardware**

Undergo synthesis process which convert software’s instructions in HLL to machine language in binary format

Software (HLL) -> System software (assembly language) -> Hardware (machine language)

![image](https://user-images.githubusercontent.com/118953917/203914970-87aa56d5-4e03-408d-8745-709810468620.png)

###############################################################################################

#### Lab Result

This is my first repository

![day0lab](https://user-images.githubusercontent.com/118953917/205441391-ee1d548a-1eb0-48d3-a22e-080881c0d0d9.JPG)



## Day-1 

### Topic: Introduction to Verilog RTL design and Synthesis

#### Lab Result

**Lab introduction**

Clone the github.
*	git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git

![day1labintro](https://user-images.githubusercontent.com/118953917/205478289-f1f31100-d90c-42d8-ab91-404251bc7237.JPG)

**Lab part 1**

**Scripting**

Change directory to verilog_files, make a compiler/driver takes the Verilog input and generate the output format.
*	iverilog good_mux.v tb_good_mux.v

Operating system that are executables, object code, and, in later systems, shared libraries.
*	./a.out

To view the output waveform of the design.
*	gtkwave tb_good_mux.vcd

![day1labpart1a](https://user-images.githubusercontent.com/118953917/205478292-37015dc0-e14f-4e31-91fe-8e3df12f4000.JPG)

**Output**

When sel=0; the output is toggling and following input i0 which is 0. Whereas, when sel=1; the output is following i1 which is 1.

![day1labpart1](https://user-images.githubusercontent.com/118953917/205478290-20276c56-01f4-427e-a70d-2a2ad3acfdcc.JPG)

**Lab part 2**

**Scripting to open GVIM**

To view the design and test bench RTL codes.
*	vim tb_good_mux.v -o good_mux.v

![day1labpart2vim](https://user-images.githubusercontent.com/118953917/205478288-b38d4f85-aa00-450a-a0ad-a8f67978de91.JPG)

**RTL code for design**
-	Multiplexer design codes.
-	If there is select (sel=1), the output design follows i1. If there is no select (sel=0), the output design follows i0.

![day1labpart2design](https://user-images.githubusercontent.com/118953917/205478285-dd6a5cd0-7994-4e97-b63b-b80663691645.JPG)

**RTL code for test bench**
-	Test bench instantiated the design. TB do not have primary inputs/outputs. 
-	Must dumping the VCD file and have a stimulus generator based upon the stated duration. 

![day1labpart2tb](https://user-images.githubusercontent.com/118953917/205478287-a7b8c191-4274-40a8-b4b1-a0c627ca6c92.JPG)



