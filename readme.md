# Intel SD Training

## Table of contents

* [ Day 0 - System/Tool Setup Check. GitHub ID creation ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-0)
* [ Day 1 - Introduction to Verilog RTL design and Synthesis ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-1)
* [ Day 2 - Timing libs (QTMs/ETMs), hierarchical vs flat synthesis and efficient flop coding styles ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-2)
* [ Day 3 - Combinational and sequential optimizations ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-3)
* [ Day 4 - GLS, blocking vs non-blocking and Synthesis-Simulation mismatch ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-4)
* [ Day 5 - Design For Testability (DFT) ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-5)
* [ Day 6 - Introduction to Logic Synthesis ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-6)
* [ Day 7 - Basic SDC constraints](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-7)
* [ Day 8 - Advanced SDC Constraints ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-8)
* [ Day 9 - Optimizations ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-9)
* [ Day 10 - Quality of Results (QOR) ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-10)
* [ Day 11 - Introduction to the BabySoC ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-11)
* [ Day 12 - BabySoC Modelling ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-12)
* [ Day 13 - Post-synthesis simulation ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-13)
* [ Day 14 - Synopsys DC and Timing Analysis ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-14)
* [ Day 15 - Inception of EDA and PDK ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-15)
* [ Day 16 - Understand importance of good floorplan vs bad floor plan and introduction to library cells ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-16)
* [ Day 17 - Design and characterise one library cell using Layout tool and spice simulator ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-17)
* [ Day 18 - Pre-layout timing analysis and importance of good clock tree ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-18)
* [ Day 19 - Final steps for RTL2GDS ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-19)
* [ Day 20 - Floorplanning and power planning labs ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-20)
* [ Day 21 - Placement and CTS labs ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-21)
* [ Day 22 - CTS analysis labs ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-22)
* [ Day 23 - Clock gating technique ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-23)
* [ Day 24 - Timing violations and ECO ](https://github.com/nurnazahah/sd-training/blob/main/readme.md#day-24)

## Day-0

### Topic: System/Tool Setup Check. GitHub ID creation

<details>
  <summary>Theory</summary>
 

### Theory

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

</details>

<details>
  <summary>Lab</summary>
 
### Lab
 
**Lab Result**

This is my first repository

![day0lab](https://user-images.githubusercontent.com/118953917/205441391-ee1d548a-1eb0-48d3-a22e-080881c0d0d9.JPG)
</details>


## Day-1 

### Topic: Introduction to Verilog RTL design and Synthesis
<details>
  <summary>Introduction to iverilog and GTKwave</summary>


### Introduction to iverilog and GTKwave

**What is simulator?**
* Tool used for checking design.

**What is RTL (Register Transfer Level)?**
* Implementation of the specifications where specifications need to be verified by simulating the design.
* Tool used: iVerilog

**Design**: Actual verilog code or the set of of verilog codes to meet the required specifications.

**Test bench**: Setup to apply stimulus/test vectors into the design to check its functionality as well as checking whether the design is obeying the required specifications or not.

**How simulator works?**
* Looks for changes in the input signals in which simulator is looking for changes in the values of the inputs.
* Output is evaluated based upon the changes in the input. If there is no change in the input, hence there is no change in the output.

![image](https://user-images.githubusercontent.com/118953917/205529453-f55fd8dc-02ba-4d61-8454-49294cf4c2fc.png)

*notes: Design may have one or more primary input/output. Test bench doesn't have primary input/output.

**iVerilog based simulation flow**

![image](https://user-images.githubusercontent.com/118953917/205529661-03507326-a34a-4a8e-8c28-f357ad5c721d.png)
</details>
  
<details>
  <summary>Lab 1</summary> 

**Lab 1 Introduction to iverilog and GTKwave**

Clone the github.
*	git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git

![day1labintro](https://user-images.githubusercontent.com/118953917/205478289-f1f31100-d90c-42d8-ab91-404251bc7237.JPG)



**Lab 1 part 1**

**Scripting**

Change directory to verilog_files, make a compiler/driver takes the Verilog input and generate the output format.
*	iverilog good_mux.v tb_good_mux.v

Operating system that are executables, object code, and, in later systems, shared libraries.
*	./a.out

To view the output waveform of the design.
*	gtkwave tb_good_mux.vcd

![day1labpart1a](https://user-images.githubusercontent.com/118953917/205478292-37015dc0-e14f-4e31-91fe-8e3df12f4000.JPG)

**Output**

Output is fixed from 0 ns to 300 ns. When sel=0; the output is toggling and following input i0 which is 0. Whereas, when sel=1; the output is following i1 which is 1.

![day1labpart1](https://user-images.githubusercontent.com/118953917/205478290-20276c56-01f4-427e-a70d-2a2ad3acfdcc.JPG)



**Lab 1 part 2**

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


### Introduction to yosys and logic synthesis

**What is synthesizer?** 
* Tool used to convert RTL to netlist.
* Tool used: yosys

**yosys setup**


![image](https://user-images.githubusercontent.com/118953917/205531090-c5df6743-c213-4e69-b5e4-7964e31f721b.png)



**Logic synthesis flow**
1. RTL to gate level translation.
2. Design is converted to gates and connections are made between gates.
3. Given out as a file called netlist.

![image](https://user-images.githubusercontent.com/118953917/205530184-b02d1853-e943-446f-b7e1-8ddfeb446dea.png)
</details>
  
<details>
  <summary>Lab 2</summary> 

**Lab 2 Introduction to yosys and logic synthesis**

**Scripting**

To invoke yosys
* yosys

To import liberty files
*	read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

To generate Verilog files of multiplexer.
*	read_verilog good_mux.v

Synthesize the required module
*	synth -top good_mux

![day1lab2part1a](https://user-images.githubusercontent.com/118953917/205480492-654d148a-fe13-4529-89ac-5aa4ee328d9f.JPG)

**Output**

![day1lab2part1b](https://user-images.githubusercontent.com/118953917/205480493-7ed726f9-69c3-4764-a3b5-0ab068172626.JPG)

To convert RTL file to the linked and specified gates design 
*	abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

![day1lab2part1c](https://user-images.githubusercontent.com/118953917/205480494-e1d1f3b2-2dfb-473a-8a9f-a9168437f5ed.JPG)

* internal signal = 0
* input signal = 3
* output signal = 1

![day1lab2part1d](https://user-images.githubusercontent.com/118953917/205480497-5f429c27-c9ac-4a65-9dae-c35b530aed6c.JPG)

**Scripting to open graphical design**

To show the graphical version of the design 
*	show

![day1lab2part1e](https://user-images.githubusercontent.com/118953917/205480499-ee2bda13-5ba5-4380-824b-c200e99fd540.JPG)

**Output of multiplexer design**

![day1lab2part1f](https://user-images.githubusercontent.com/118953917/205480486-3565c43d-8652-40f6-a0ba-d4bd9bc399eb.JPG)

**Scripting to open netlist**

To write netlist
*	write_verilog good_mux_netlist.v

To view the codes 
*	!vim good_mux_netlist.v

![day1lab2part3a-script](https://user-images.githubusercontent.com/118953917/205480489-e9c6bb72-7b29-4b26-9604-c230f6b801be.JPG)

**Output**

*	Got lots of extra inputs 

![day1lab2part3a-op](https://user-images.githubusercontent.com/118953917/205480488-f0d0d2ce-7f0e-43b6-be12-5c21e5c6ca8b.JPG)

**Scripting to open netlist**

To create more simplified netlist
*	write_verilog -noattr good_mux_netlist.v

![day1lab2part3b-script](https://user-images.githubusercontent.com/118953917/205480491-0db37af3-2766-4e3f-b8f4-49354d3f9cb0.JPG)

**Output**

* The outputs are more simplified
*	Wire: connecting nets to each element
* Example:	

i0 = wire_0 = primary input

i1 = wire_1 = primary input

sel = wire_2 = primary input

y = wire_3 = primary output


![day1lab2part3b-op](https://user-images.githubusercontent.com/118953917/205480490-1e99dd0e-1c56-4b55-b651-e195a2518717.JPG)

</details>


## Day-2 

### Topic: Timing libs (QTMs/ETMs), hierarchical vs flat synthesis and efficient flop coding styles
<details>
  <summary>Lab 1: Introduction to timing .libs</summary> 

**Lab 1: Introduction to timing .libs**

>To view the gvim 
>> vim ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>To turn off the syntax in gvim
>> :syn off

* Process: tt (typical average)
* Voltage: 1.80 V
* Temperature: 25°C

![day2lab1a](https://user-images.githubusercontent.com/118953917/205578983-1276c76a-be8e-4509-b3a3-dc3d4c373a72.JPG)

>To display the line number
>> :se nu

>To search specific words
>> /cell 

>To scan the specific words. Example: cell 
>> :g//

Identifying the structure of the cell

![day2lab1b](https://user-images.githubusercontent.com/118953917/205856602-25f0e698-b1ff-461d-8e89-dd00fb638a84.JPG)

>To split two vims vertically 
>> :vsp ../my_lib/verilog_model/sky130_fd_sc_hd.v

There are 2^5 = 32 possible inputs combinations of the design 

**Detailed information in vim**

![day2lab1c](https://user-images.githubusercontent.com/118953917/205851243-69ac4217-411a-461d-9aa3-87f6c007d624.JPG)

![day2lab1d](https://user-images.githubusercontent.com/118953917/205868197-77344994-1aa4-49fc-af46-181b7f65ad07.JPG)

![day2lab1e](https://user-images.githubusercontent.com/118953917/205868209-f02cb6ea-2b6b-4b25-99b7-f24515c4ea34.JPG)

>To search specific words
>> /cell .*and

>Split vertically to make comparisons
>> :vsp ../my_lib/verilog_model/sky130_fd_sc_hd.v

>Search for different types of flavours and inputs in the same cell
>> /and2_0

>> /and2_2

>> /and2_2

* The wider the cell, the greater the area, the larger the leakage power, resulting in less delay. Since it has small delay, it can operates faster.

* Contrarily, the narrower the cell, the smaller the area, the smaller the leakage power, resulting in more delay. Since it has small area, it only needs less power consumption.

![day2lab1f](https://user-images.githubusercontent.com/118953917/205929860-c9e146e9-d910-4abc-a65a-cbd8a59505f7.JPG)

</details>
  
<details>
  <summary>Lab 2: Hierarchical vs Flat Synthesis</summary> 

**Lab 2 Hierarchical vs Flat Synthesis**

>Open vim 
>> vim multiple_modules.v

![day2lab2a](https://user-images.githubusercontent.com/118953917/205945324-55bd0326-f8a5-4d03-a9ae-35fecba4d087.JPG)


>Invoke yosys, import liberty files, generate verilog file, synthesize module, convert RTL to gate design

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog multiple_modules.v

>> synth -top multiple_modules 

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show multiple_modules 

![day2labsnapshot](https://user-images.githubusercontent.com/118953917/206221522-0121818e-2323-45f1-b5ee-e4f90b282f58.JPG)

![day2lab2b](https://user-images.githubusercontent.com/118953917/205945334-4caede00-299d-491c-a7e0-39375bbe0cf0.JPG)

![day2lab2c](https://user-images.githubusercontent.com/118953917/205945612-b4ceba1a-0815-4e29-bfee-4997429f1674.JPG)

>Open and write netlist
>> write_verilog multiple_modules_hier.v 

>> write_verilog -noattr multiple_modules_hier.v 

![day2labsnapshot2](https://user-images.githubusercontent.com/118953917/206225754-05701bd7-5443-445d-aed8-8eb55e224e67.JPG)

>> !vim multiple_modules_hier.v 

*Notes: Scripting from instructor's video.

![day2lab2d](https://user-images.githubusercontent.com/118953917/206104807-8c01887a-463d-421c-8f15-a85f20bf1bf6.JPG)

*Notes: Scripting at my end

![day2lab2d1](https://user-images.githubusercontent.com/118953917/206105858-04b38d3a-5ddf-4936-b9ae-6f2c59e24ea1.JPG)

Why 2 inverter and NAND gates are constructed instead of OR gate? 

* Stacking PMOS of NAND gate is always bad since it has poor mobility.

* To improve the bad cell, the wider cell must be constructed to make a good logical effort. To compute the logical effort of a logic gate, pick transistor sizes
for it that make it as good at delivering output current as a standard inverter, and then tally up the input capacitance of each input signal.

![day2lab2e](https://user-images.githubusercontent.com/118953917/206087867-bfef5fef-2adf-47f2-a3c7-e9387a64525a.JPG)

>To flatten the design
>> flatten

>> write_verilog multiple_modules_flat.v 

>> write_verilog -noattr multiple_modules_flat.v 

![day2labsnapshot3](https://user-images.githubusercontent.com/118953917/206228210-253c783c-ab06-492c-a001-9e488cb1f726.JPG)

![day2labsnapshot2](https://user-images.githubusercontent.com/118953917/206226306-a7cb7e4b-198f-43b6-8cc3-b42bb7d60fe7.JPG)

>> !vim multiple_modules_flat.v 

>> :vsp multiple_modules_hier.v

>> show

* In hierarchy module, sub module 1 and sub module 2 is preserved.

* Whereas, in flattened module, it is a single netlist, we cannot see them. It has been flattened out. 

![day2lab2f](https://user-images.githubusercontent.com/118953917/206108677-5b6fd1ba-c0e2-45c1-9d65-5ae30b4a4159.JPG)

**Graphical circuit output**

![day2lab2g](https://user-images.githubusercontent.com/118953917/206109393-2adda35f-075f-4eb1-84f7-92358aa00aca.JPG)

![day2labsnapshot4](https://user-images.githubusercontent.com/118953917/206228219-fe0f4920-8508-46ba-a30a-16a5f3b29826.JPG)

>> synth -top sub_module1

![day2labsnapshot5](https://user-images.githubusercontent.com/118953917/206228224-a9440b9c-0b3d-4a87-87c9-28bcbdd08c02.JPG)

Why sub module synth is used?
* When we have multiple instances of the same module.

* To divide in corners. When the design is using a massive design, it is not doing a good job.

![day2lab2h](https://user-images.githubusercontent.com/118953917/206114375-27aaf964-105f-4116-b772-2f50f3cf9008.JPG)

 </details>
  
<details>
  <summary>Lab 3: Various Flop Coding Styles and optimization</summary> 

**Lab 3: Various Flop Coding Styles and optimization**

**Comparison of asynchronous-synchronous, asynchronous, synchronous set, and synchronous**

![day2lab3a](https://user-images.githubusercontent.com/118953917/206135645-d49bb437-a3cc-48a0-ab14-ecece5af6573.JPG)

>> iverilog dff_asyncres.v tb_dff_asyncres.v

>> ./a.out

>> gtkwave tb_dff_asyncres.vcd

![day2labsnapshot6](https://user-images.githubusercontent.com/118953917/206229906-ec0c32dc-e73e-45a9-9a0d-07cf1f2af180.JPG)

**Asynchronous output**

* Reset went low much before the clock. D is waiting for the clock to become "1" before it goes to "1" while output Q changes upon clock edge. Q is changing because of D. 

* The moment reset came from low to high, it was not waiting for the subsequent clock edge. The output Q will immediately went low. 

* Asynchronous behaviour is not awaiting for clock edge.

![day2lab3b-async](https://user-images.githubusercontent.com/118953917/206151237-1f37231a-32b4-4bcb-a267-84efd08eb881.JPG)

**Asynchronous_set output**

* The changes in the D pin trigger the output Q pin upon the changes of the clock edge.
 
* When set is high, the output Q will immediately went high irrespective to the clock edge. Q will remain high until set is toggle back to low.

![day2lab3b-asyncset](https://user-images.githubusercontent.com/118953917/206151248-4668c9dc-8af2-4eaf-a109-ad690b0acd98.JPG)

**Synchronous output**

* When reset is high, the output Q will go low subsequently upon the clock edge toggling. Q will remain low until reset is toggle back to low.
The output(q) will get trigger for each of the posedge clock

![day2lab3b-sync](https://user-images.githubusercontent.com/118953917/206151253-9bab416c-b665-410b-9f45-001837a711ea.JPG)

![day2labsnapshot7](https://user-images.githubusercontent.com/118953917/206230621-52ef6192-bf17-4e83-b4a6-c4f8d9fd299b.JPG)

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog dff_asyncres.v 

>> synth -top dff_asyncres 

>> dfflibmap -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

![day2labsnapshot8](https://user-images.githubusercontent.com/118953917/206231148-b9328505-72b6-4cbc-a9bd-610079ee6df8.JPG)

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

![day2lab3c](https://user-images.githubusercontent.com/118953917/206190275-be479c10-3040-4011-b9b8-ff17cc2e7661.JPG)

**Asynchronous output**

![day2lab3d-async](https://user-images.githubusercontent.com/118953917/206196175-28336cc0-8a31-4097-a0ca-3486cf849db2.JPG)

**Asynchronous_set output**

![day2lab3d-asyncset](https://user-images.githubusercontent.com/118953917/206196162-2ef4b434-8731-4138-8b8f-062878151528.JPG)

**Synchronous output**

![day2lab3d-sync](https://user-images.githubusercontent.com/118953917/206196172-869cfea8-cf91-4d28-9ea7-12d6f051ca2a.JPG)

Why there is no set/reset pin in flip flop?

*Notes: The explaination figure is taken from the instructor's video.

![day2lab3e](https://user-images.githubusercontent.com/118953917/206197685-b429be30-5e18-4473-8cc0-6c6be62521a7.JPG)

>> vim mult_*.v -o 

or

>> cat mult_*.v

![day2lab3f](https://user-images.githubusercontent.com/118953917/206202801-e03a746e-0e99-4391-baee-b6916a2e4a57.JPG)

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog mult_2.v

>> synth -top mul2

![day2labsnapshot9](https://user-images.githubusercontent.com/118953917/206231907-a80b18f5-a2e1-48d3-ba83-fb21f0ef31fe.JPG)

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show

![day2lab3g](https://user-images.githubusercontent.com/118953917/206206370-5364de09-32a3-4296-bb50-3d51f15fd47b.JPG)

*Notes: the figure at the left is taken from the instructor's video.

![day2lab3h](https://user-images.githubusercontent.com/118953917/206206375-5e37d68a-078c-488c-b4a2-79801a68fd44.JPG)

**Special case**

>> yosys

>> yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog mult_8.v 

>> synth -top mult8

![day2labsnapshot10](https://user-images.githubusercontent.com/118953917/206232431-8c004752-6d52-4921-a080-9aeb5f261db2.JPG)

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show

>> write_verilog -noattr mult8_net.v 

* Requires no hardware for special case since we can just rewiring the signal. 

* Any standard cell is not required to acquire the logic functionality.

*Notes: the figure at the top is taken from the instructor's video.

![day2lab3i](https://user-images.githubusercontent.com/118953917/206213266-f33aa64a-7ad8-4d5c-a2f0-f22816f1445a.JPG)
</details>
 

## Day-3


### Topic: Timing libs (QTMs/ETMs), hierarchical vs flat synthesis and efficient flop coding styles

<details>
  <summary>Introduction to optimisations</summary> 

#### Introduction to optimisations

Combinational logic optimisation
* To squeeze the logic to get the most optimised design in terms of Area and Power saving.
* Constant propagation technique used: Direct optimisation.
* Boolean logic optimisation technique: K-map and Quine McKluskey.

*Notes: Circuit diagram is taken from instructor's video.
![day3lab1a](https://user-images.githubusercontent.com/118953917/206355330-fdaec931-c9f2-49f2-9cb8-3e87eb3a6b01.JPG)

![day3lab1b](https://user-images.githubusercontent.com/118953917/206356348-7c897af2-e544-4eb7-946f-67271949fb23.JPG)

Sequential logic optimisation
* Basic: Sequential constant propagation. **will be covered in the lab**
* Advanced: State optimisation, retiming, and sequential logic cloning (floor plan aware synthesis). **not covered in the lab**

Sequential constant
* When RST is applied, Q = 0.
* When there is no RST applied, Q = 0 because D = 0.
* Q will always be 0 whether RST or clock is being applied or not. 

*Notes: This is example of sequential constant.

![day3lab1c](https://user-images.githubusercontent.com/118953917/206372398-19416e10-8f26-43ce-92b8-7514a7cd1b01.JPG)

* When set is applied, Q = 1.
* When there is not set applied and there is a clock, Q = 0. 
* Q can be both value 0 and 1 depending on the set situation.
* Cannot simply assume Q = set because Q will toggle for the next clock period cycle. For example, when set is going from '1' to '0', the output Q will wait for the next positive clock cycle to be '1' before toggling from '1' to '0'. Q is waiting for the clock to become '0' in Q.

*Notes: This is example of not sequential constant.
* This flop cannot be optimised, it must be retained. The sequential logic cannot be propagated and should be retained.
* To make the flop be sequential, the output Q will be always be a constant value whether rst or clock or any other thing are applied.

![day3lab1d](https://user-images.githubusercontent.com/118953917/206372423-7917ac79-ada9-4885-be3e-530dd1d6faee.JPG)

State optimisation, retiming, and sequential logic cloning
* State optimisation: Optimisation of unused state.
* Cloning (Physical aware): clock-gate (a special gate in the clock tree that switches of the clock signal to a number of flip-flops to save power when they are not needed) is duplicated so that one clock-gate driving, for example, 40 flip-flops can be "cloned" to become 2 clock-gates driving 20 flip-flops each.
* Retiming: a technique for optimizing sequential circuits. It repositions the registers in a circuit leaving the combinational portion of circuitry untouched. The objective of retiming is to find a circuit with the minimum number of registers for a specified clock period.

![day3lab1e](https://user-images.githubusercontent.com/118953917/206386303-6b5a0417-de0c-4f40-afca-cb20ed45878d.JPG)
 
 </details>
  
<details>
  <summary>Lab 1: Combinational Logic Optimisations</summary> 

#### Lab 1: Combinational Logic Optimisations

>> ls *opt_check* 

>> !gvim opt_check.v

>> !gvim opt_check2.v

>> !gvim opt_check3.v

>> !gvim opt_check4.v

![day3lab1f](https://user-images.githubusercontent.com/118953917/206479526-391ae3fe-5bc5-447f-9290-4d2e670be9de.JPG)

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog opt_check.v

>> synth -top opt_check

>> opt_clean -purge

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

![day3lab1g](https://user-images.githubusercontent.com/118953917/206456146-a2f707e4-1af4-42ab-bb70-91ba7aacd8ee.JPG)

>> show

![day3lab1h](https://user-images.githubusercontent.com/118953917/206459637-5b71b4bf-14df-469e-9ff4-c83eac82515f.JPG)
![day3lab1i](https://user-images.githubusercontent.com/118953917/206479602-5b84f7c9-b0b7-40c4-b0d7-078fed6f9e08.JPG)


>> ls *multiple_module_opt*

>> gvim multiple_module_opt.v

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog multiple_module_opt.v

>> synth -top multiple_module_opt

>> flatten

>> opt_clean -purge

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show

multiple_module_opt

![day3lab2l](https://user-images.githubusercontent.com/118953917/206708545-ce9576d2-fe97-4b98-818d-67cb921dd5f7.JPG)

multiple_module_opt2

![day3lab2m](https://user-images.githubusercontent.com/118953917/206708534-e7a7330b-fa5c-4cac-bf1f-f2bcb32e8c72.JPG)

 </details>
  
<details>
  <summary>Lab 2: Sequential Logic Optimisations</summary> 

#### Lab 2: Sequential Logic Optimisations

>> gvim dff_const1.v -o dff_const2.v

![day3lab2a](https://user-images.githubusercontent.com/118953917/206494320-917050c2-08b2-46e4-93f0-3ca71dd9145b.JPG)

>> iverilog dff_const1.v tb_dff_const1.v

>> ./a.out

>> gtkwave tb_dff_const1.vcd

![day3lab2b](https://user-images.githubusercontent.com/118953917/206495551-ca56a6ab-4045-478c-bb95-5e0d5cdd7214.JPG)

![day3lab2e](https://user-images.githubusercontent.com/118953917/206611412-0acdc45a-ee64-48f3-9d8c-466446f1ad34.JPG)

![day3lab2f](https://user-images.githubusercontent.com/118953917/206614858-48e7f4ba-fba1-4616-af6f-99ea8f1f3c5c.JPG)

![day3lab2h](https://user-images.githubusercontent.com/118953917/206616872-327adf53-23ee-4675-9abe-983595097cae.JPG)

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog dff_const1.v

>> synth -top dff_const1

>> dfflibmap -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show

![day3lab2c](https://user-images.githubusercontent.com/118953917/206499671-15d3b757-4b66-42f5-b05f-3fad2c2afb2f.JPG)

For dff_const1, it does inferred DFF, while for dff_const2, it does not inferred anything. 

![day3lab2d](https://user-images.githubusercontent.com/118953917/206605673-f9608abc-3ce2-4ba6-b6f8-0aca142799ed.JPG)

![day3lab2i](https://user-images.githubusercontent.com/118953917/206620003-c6c10f52-e7c4-449e-9f22-01a09ec53c26.JPG)

![day3lab2j](https://user-images.githubusercontent.com/118953917/206619992-7b4a6e69-7769-43b6-a1c3-c986c1d346a0.JPG)

![day3lab2k](https://user-images.githubusercontent.com/118953917/206620000-8254049a-3fdf-497d-a026-d3d04a3899da.JPG)

 </details>
  
<details>
  <summary>Lab 3: Sequential optimzations for unused outputs</summary> 

#### Lab 3: Sequential optimzations for unused outputs

Unused output optimisation

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog counter_opt.v

>> synth -top counter_opt

>> dfflibmap -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> show

![day3lab3a](https://user-images.githubusercontent.com/118953917/206634003-09270394-1a2b-4734-9f6a-6f0b4b8ae743.JPG)

![day3lab3b](https://user-images.githubusercontent.com/118953917/206633997-8e29b57b-536c-44a3-8359-9e4807365693.JPG)

>> cp counter_opt.v counter_opt2.v

>> gvim counter_opt2.v -> write Q value inside gvim

>> :wa! or :wq to save work

> open yosys and do the same steps as before

>> synth -top counter_opt

![day3lab3c](https://user-images.githubusercontent.com/118953917/206652215-e90e344e-65db-4936-8977-0e0b92fc1075.JPG)
 </details>


## Day 4

### Topic: GLS, blocking vs non-blocking and Synthesis-Simulation mismatch

<details>
  <summary>Introduction to GLS, blocking vs non-blocking and Synthesis-Simulation mismatch</summary> 

#### Introduction to GLS, blocking vs non-blocking and Synthesis-Simulation mismatch

What is Gate Level Simulation (GLS)?

* Running the test bench with netlist as Design Under Test (DUT).
* Netlist is logically same as RTL code - same test bench will allign with the design.

Why GLS?

* Verify the logical correctness of design after synthesis.
* Ensuring the timing of the design is met - for this GLS needs to be run with delay annotation.

GLS using iverilog

*Notes: Mindmap is taken from instructor's video.

![day4labintroa](https://user-images.githubusercontent.com/118953917/206889766-5e90e4dc-1a2a-48ba-82c0-440d9c2a13cf.JPG)

*Notes: Example is taken from instructor's video.

![day4labintroB](https://user-images.githubusercontent.com/118953917/206892298-58e8e0c8-fa62-4660-9bf0-0f271a3f96d6.JPG)

Synthesis simulation mismatch

* Missing sensitivity list.
* Blocking vs non-blocking assignments.
* Non standard verilog coding.

Simulator works based on activity where output will change based upon the changes in input. If there is no activity, output will not change at all. 

*Notes: Example is taken from instructor's video.

![day4labintroc](https://user-images.githubusercontent.com/118953917/206893907-72c992b3-22a9-4916-b429-c9877f3d4aa1.JPG)

**Blocking and non-blocking statements in verilog**

**Inside always block**

= : Bocking

* Executes the statements in the order it is written.
* So, the first statement is evaluated before the second statement.

<= : Non-blocking

* Executes all the Right Hand Side (RHS) when always block is entered and assigns to Left Hand Side (LHS).
* Parallel evaluation. 

Caveats with blocking statements

*Notes: Example is taken from instructor's video.

![day4labintrod](https://user-images.githubusercontent.com/118953917/206893381-678189a6-58fc-46ec-883c-68ef1c17a8c1.JPG)

![day4labintroe](https://user-images.githubusercontent.com/118953917/206893870-a8421413-8d09-4017-9738-c667fd4a17c4.JPG)

</details>
  
<details>
  <summary>Lab 1: GLS Synth Sim Mismatch</summary> 

#### Lab 1: GLS Synth Sim Mismatch

>> gvim ternary_operator_mux.v -o bad_mux.v -o good_mux.v 

**Ternary operator**

Example: assign y = sel?i1:i0

![day4lab1a](https://user-images.githubusercontent.com/118953917/206908420-a951d8ff-4fd9-4750-8d92-7550b705e0fe.JPG)

>> iverilog ternary_operator_mux.v tb_ternary_operator_mux.v

>> ./a.out

>> gtkwave tb_ternary_operator_mux.vcd

When sel = 0, the output Y follows input i0. Whereas, when sel = 1, Y follows input i0.

![day4lab1b](https://user-images.githubusercontent.com/118953917/206908435-e8004b40-240e-47c9-a44d-8f6eaa9e6739.JPG)

>> yosys

>> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> read_verilog ternary_operator_mux.v

>> synth -top ternary_operator_mux

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> write_verilog -noattr ternary_operator_mux_net.v 

>> show 

![day4lab1c](https://user-images.githubusercontent.com/118953917/206908445-2fb1e440-75ad-4d4c-80fc-f65a0c855d0a.JPG)

>> iverilog ../my_lib/verilog_model/primitives.v  ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v

>> ./a.out

>> gtkwave tb_ternary_operator_mux.vcd 

![day4lab1d](https://user-images.githubusercontent.com/118953917/206908455-ee27b998-7872-43be-afa5-a3e78081f96d.JPG)

![day4lab1e](https://user-images.githubusercontent.com/118953917/206908470-50e59616-13df-4a22-9865-d16bce93badf.JPG)


**Bad mux**

>> iverilog bad_mux.v tb_bad_mux.v 

>> ./a.out

>> gtkwave tb_bad_mux.vcd

**Synthesis simulation mismatch**

>> iverilog ../my_lib/verilog_model/primitives.v  ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_net.v tb_bad_mux.v

>> ./a.out

>> gtkwave tb_bad_mux.vcd 



>> read_verilog bad_mux.v

>> synth -top bad_mux

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> write_verilog -noattr bad_mux_net.v 

>> show


**Bad mux**

When there is activity on select, the inputs and output is toggling because it is depending on select.
* When select is low, i0 should be high based on the actual behavior of multiplexer. But, in this case, i0 is low because select is low (there is no activity in select).
* Whereas, when select is high, there is activity on select. Theoretically, i1 should be high and i0 should be low. But in bad mux, both inputs i0 and i1 is high since there is activity on select.
* Only when select is changing, the output Y is also changing based upon the select.

**Synthesis simulation mismatch**

The output Y is following both inputs i0 and i1 depending on select.
* When select is low, the output is following i0.
* Whereas when select is high, the output is following i1.


![day4lab1f](https://user-images.githubusercontent.com/118953917/206908481-a16c2c0f-c359-4482-bc26-667c1d6dac7e.JPG)

</details>
  
<details>
  <summary>Lab 2: Synth sim mismatch blocking statement</summary> 
                                         
#### Lab 2: Synth sim mismatch blocking statement

>> gvim blocking_caveat.v

>> iverilog blocking_caveat.v tb_blocking_caveat.v

>> ./a.out

>> gtkwave tb_blocking_caveat.vcd 

![day4lab2a](https://user-images.githubusercontent.com/118953917/206908531-668b8cf0-131a-40b7-a450-7d2217e154f2.JPG)

>> read_verilog blocking_caveat.v

>> synth -top blocking_caveat

>> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib 

>> write_verilog -noattr blocking_caveat_net.v

>> show

![day4lab2b](https://user-images.githubusercontent.com/118953917/206908538-b6def2eb-dbc3-4b9a-9e71-77935769ccd2.JPG)

>> iverilog ../my_lib/verilog_model/primitives.v  ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_net.v tb_blocking_caveat.v

>> ./a.out

>> gtkwave tb_blocking_caveat.vcd 

![day4lab2c](https://user-images.githubusercontent.com/118953917/206908549-ffe180e3-22e8-4088-a58e-79ac7255f582.JPG)
</details>
                                         
                                         
## Day-5
                                        

### Topic: Design for Testability (DFT)
</details>
  
<details>
  <summary>Theory</summary> 
                                         

![day5lab1a](https://user-images.githubusercontent.com/118953917/207813102-6edfd30b-864e-4dae-a1db-bf4eff618a24.jpg)

![day5lab1b](https://user-images.githubusercontent.com/118953917/207813106-cb877103-3856-4aa2-9450-fa35ed0bd670.jpg)

![day5lab1c](https://user-images.githubusercontent.com/118953917/207813111-51b1753f-7332-4acd-bf60-3eff0c563bd6.jpg)

![day5lab1d](https://user-images.githubusercontent.com/118953917/207813118-f930654f-3d77-4f67-a160-9fef6cb811b2.jpg)

![day5lab1e](https://user-images.githubusercontent.com/118953917/207813123-3a2a8bd8-dbf7-41a6-8da4-e4be9d6bff55.jpg)

![day5lab1f](https://user-images.githubusercontent.com/118953917/207813084-283beaa4-2b16-49e5-8aff-a45eb18a6faf.jpg)

![day5lab1g](https://user-images.githubusercontent.com/118953917/207813089-4ca1a08f-88f5-4848-bb12-52d4dda2575d.jpg)

![day5lab1h](https://user-images.githubusercontent.com/118953917/207813091-6f5503ab-ef9b-43a8-985c-bf80030a728b.jpg)

![day5lab1i](https://user-images.githubusercontent.com/118953917/207813093-acf01c53-82db-410c-8bf9-b1002a451019.jpg)

![day5lab1j](https://user-images.githubusercontent.com/118953917/207813096-8ffbe723-1e2b-44ee-ac7d-9434eb65822c.jpg)
</details>

## Day-6

### Topic: Introduction to Logic Synthesis

<details>
  <summary>Introduction to the course</summary>
 

### Introduction to the course
  
**Tools used**
* iVerilog: for verilog compilation and simulation
* gtkwave: for viewing the simulation output
* Synopsys design compiler: for logic synthesis
* skywater 130nm library
  
**Pre-requisites**
* Digital electronics
* Boolean algebra
* Verilog Hardware Description Level (HDL) coding 
* Idea of basic synthesis


**What to expect from the course?**
* Understand various steps involved in Digital Logic Synthesis
* Understand and write Synopsis Design Constrants (SDC) for the given module
* Perform synthesis and write out netlist using design compiler
* Generate and analyze the synthesis reports/STA reports
  
**Basics of digital logic design and synthesis**
* Digital logic: including switching function, and automation and decision making
* Behavioral model of the design written in HDL: using VHDL and verilog
  

![day6lab1a](https://user-images.githubusercontent.com/118953917/208397228-54fb7390-6628-48b6-a0cb-cb1261a9d4c7.jpg)
![day6lab1b](https://user-images.githubusercontent.com/118953917/208397248-154bc6cb-def8-438f-abe3-aa0a65d91014.jpg)

  
**Synthesis**
* RTL to gate level translation
* The design is converted into gates and the connections are made between the gates
* This is given out as a file called netlist
  
**What is .lib?**
* Collection of logical modules
* Includes basic logic gates like AND, OR, NOT, etc.
* Different flavors of the same gate
  

  ![day6lab1c](https://user-images.githubusercontent.com/118953917/208397598-1439cc60-2aba-4b9f-bbad-657a1d1dc4da.jpg)
  
Why different flavours of gate is needed?
* Combinational delay in logic path determines the maximum speed of operation of digital logic circuit
* So, we need cells that work faster to make Tcombi small


  ![day6lab1d](https://user-images.githubusercontent.com/118953917/208397629-eb571fb2-3cab-4509-8fb6-dfd46b1be8a0.jpg)
  
Why we need slow cells?
* To ensure there are no "HOLD" issues at DFF_B, we need cells that work slowly
* Hence, we need cells that work fast to meet the required performance and we need cells that work slow to meet HOLD
* The collection forms the .lib
  

  ![day6lab1e](https://user-images.githubusercontent.com/118953917/208397662-fc00fd56-8b85-4cee-808d-f8d9ad62d630.jpg)
  
**Selection of Cells**
* Need to guide the synthesizer to select the flavour of the cells that is optimum for the implementation of logic circuit
* More use of faster cells in bad circuit in terms of Power and Area
* More use of slower cells in sluggish circuit where it may not meet the performance needed
* The guidance offered to the synthesizer -> Constraints
  
**Synthesis illustration**

The circuit on the right is created from RTL using the gates available in the .Lib and given out as netlist
  

  ![day6lab1f](https://user-images.githubusercontent.com/118953917/208397692-66e2ffac-28b6-4861-8724-557b6923503d.jpg)
  
**Logic synthesis basics**
  
Notes: Example is taken from instructor's video


  ![day6lab1g](https://user-images.githubusercontent.com/118953917/208397735-a291b233-b804-47a8-b6a8-6859f50f7981.jpg)
  
**What to achieve in logic synthesis?**

  Working digital logic circuit is: 
* Logically correct
* Electrically correct
* Timing met

To give more delay to the circuit to meet setup/hold time, add buffers. However, additional buffers to meet hold, will add additional area. 
  
How to decide for the correct implementation of the design?
-> By using constraints
  * Constraints are the guide to the synthesizer to pick the correct library cells which is most appropriate for the design
  * The illustrations are picked based on the needs
</details>
  
<details>
  <summary>Introduction to DC</summary>
 

### Introduction to Design Compiler (DC)

**What is DC?**
* Design Compiler (DC): Synthesis tool targeted for ASIC design flow from Synopsys.
* Features of DC: 
 
  -> Established as a premium synthesis tool across semiconductor industry.
  
  -> Interoperability with various backend tools from Synopsys.
  
  -> Has the ability to perform DFT Scan stitch.
  
  -> Can handle huge designs with extreme complexity and provide very good Quality of Results (QoR).
  
  
**Common Terminologies associated with DC**
* Synopsis Design Constraints (SDC): Industry standard that is used across Electronic Design Automation (EDA) implementation tools. These are the design constraints which are supplied to DC to enable appropriate optimization suitable for achieving the best implementation.
* .Lib: Design library whicb contains the standard cells.
*DB: Same as .lib but in a different format. DC understands libraries in .db format.
* DDC: Synopsys proprietary format for storing the design information. DC can write out and read in DDC.
* DESIGN: RTL files which has the behavioral model of the design.
  
**Synopsys Design Constraints (SDC) format**
* Design intent in terms of timing, power and area constraints.
* Supported by different EDA tools across semiconductor industry.
* SDC is based on Tool Command Language (TCL).
  
**DC Setup**

  ![day6lab1h](https://user-images.githubusercontent.com/118953917/208397835-39698526-7852-4c02-96c3-03faa67aac11.jpg)
  
**Implementation flow of ASIC**

  Steps in converting RTL to the physical database (GDS format).


  ![day6lab1i](https://user-images.githubusercontent.com/118953917/208401949-378ad2bf-7629-4ffd-b903-a63c67810002.jpg)

  DC Synthesis Flow

  ![day6lab1j](https://user-images.githubusercontent.com/118953917/208399163-243a0652-8480-4e7f-b20b-e83201befc67.jpg)
 
</details>
  
<details>
  <summary>Lab 1: Invoking DC basic setup</summary>
 

### Lab 1: Invoking DC basic setup

>> Invoke DC setup
  
> git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
  
> cd sky130RTLDesignAndSynthesisWorkshop/
  
> /p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./



 ![day6lab2a1](https://user-images.githubusercontent.com/118953917/208399987-8d9285f4-2de4-409c-9c63-a33ccfa342f5.jpg)

.lib file location

  ![day6lab2a2](https://user-images.githubusercontent.com/118953917/208400030-9671d0ab-f3c3-4f93-99b7-9a25bb7db368.jpg)

> gvim sky130_fd_sc_hd__tt_025C_1v80.lib
  
> :syn off


  ![day6lab2b](https://user-images.githubusercontent.com/118953917/208400087-79079ea8-cbb5-451b-ae25-dc85146735b1.jpg)
  
> csh
  
> dc_shell


  ![day6lab2c1](https://user-images.githubusercontent.com/118953917/208400490-1c52f66b-b17e-48a0-84f3-9dc717f10abc.jpg)

> echo $target_library
  
> echo $link_library


  ![day6lab2c2](https://user-images.githubusercontent.com/118953917/208400514-4699ec22-4aa8-409f-bf92-2020511f68fb.jpg)

>> exit dc_shell and open gvim
  
> gvim DC_WORKSHOP/verilog_files/lab1_flop_with_en.v


  ![day6lab2d](https://user-images.githubusercontent.com/118953917/208400571-ee4bc5a8-6833-4551-8764-cb26aa07333d.jpg)
  
>> Invoke dc_shell 
  
> read_verilog DC_WORKSHOP/verilog_files/lab1_flop_with_en.v
  
> write -f verilog -out lab1_net.v
  
> sh gvim lab1_net.v


  ![day6lab2e](https://user-images.githubusercontent.com/118953917/208400606-c8fb67eb-d67c-40ac-98ff-69b48633ab42.jpg)
  
> read_db DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.db
  
> write -f verilog -out lab1_net.v
  
> sh gvim lab1_net.v


  ![day6lab2f](https://user-images.githubusercontent.com/118953917/208400650-8263cd08-2928-49b7-98b4-ca451dad1ccf.jpg)
  
> echo $link_library
  
> echo $target_library
  
> set target_library /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop/DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.db
  
> set link_library {* /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop/DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.db}
  
> link
  
> compile
  
> write -f verilog -out lab1_net.v
  
> sh gvim lab1_net.v
  

  ![day6lab2g](https://user-images.githubusercontent.com/118953917/208400680-3ef83f6d-f0ca-4341-aae5-5b97c96487fe.jpg)

</details>
  
<details>
  <summary>Lab 2: Introduction to DDC GUI with design_vision</summary>
 

### Lab 2: Introduction to DDC GUI with design_vision

>> Invoke GUI format of DC
  
> csh
  
> design_vision


  ![day6lab3a](https://user-images.githubusercontent.com/118953917/208400716-0832952a-1418-497c-98c9-780c8210187a.jpg)
  
> write -f ddc -out lab1.ddc
  

  ![day6lab3b](https://user-images.githubusercontent.com/118953917/208400893-12bee07a-6420-4933-8c74-ad2ff7da256d.jpg)
  
> design_vision > read_ddc lab1.ddc (loaded in one terminal)
  
> design_vision> read_verilog DC_WORKSHOP/verilog_files/lab1_flop_with_en.v (open in another terminal)
  

  ![day6lab3c](https://user-images.githubusercontent.com/118953917/208400932-87d31281-6818-4700-88a5-3a0234332495.jpg)
  
Schematic design output
  

  ![day6lab3d](https://user-images.githubusercontent.com/118953917/208401027-aabec6f2-1273-4534-b92e-a23bbea0089e.jpg)

</details>
  
<details>
  <summary>Lab 3: DC synopsys DC setup</summary>
 

### Lab 3: DC synopsys DC setup
  
>> Steps to invoke dc_shell everytime we need to reopen dc_shell
  
> cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop/
  
> /p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./
  
> csh
  
> dc_shell
  
> set target_library /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop/DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.db
  
> set link_library {* target_library}
  
> echo $target_library
  
> echo $link_library


  ![day6lab4a](https://user-images.githubusercontent.com/118953917/208401082-41810d7b-dca9-4271-bbd2-1d4f27924cd7.jpg)
  
>> Preconfigure at home directory and file name is .synopsys_dc.setup
  
> pwd -> to ensure it is at the home directory
  
> gvim .synopsys_dc.setup -> ensure the file name is as stated
  
>> Insert the contents inside gvim
  
> set target_library /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop/DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.db
  
> set link_library {* target_library}
  
>> Save and exit gvim
  
> :wq


  ![day6lab4b](https://user-images.githubusercontent.com/118953917/208401111-3ec2e644-451f-40ef-ba06-6b758b273c94.jpg)
  
>> Open dc_shell and display the output
  
> echo $target_library
  
> echo $link_library
  

  ![day6lab4c](https://user-images.githubusercontent.com/118953917/208401142-da2d1d55-e49c-42d3-9c55-411a36a237b4.jpg)

</details>
  
<details>
  <summary>TCL Quick Refresher</summary>
 

### TCL Quick Refresher

Advanced synthesis and STA using DC - TCL quick refresher
  
**TCL: Quick refresher**
  
* set 
  
  -> Used for creating/assigning values and storing information in variables
  
  -> Example: set a 5 --> a = 5
  
  -> set a [expr $a + $b] --> a = a + b
  
Note: square brackets [] are used for nesting the commands in TCL 
  
Notes: Example is taken from instructor's video
  

  ![day6lab5a](https://user-images.githubusercontent.com/118953917/208401199-4a32e760-56d2-41be-910f-deead81fe976.jpg)

**While loop**

Notes: Example is taken from instructor's video
  

  ![day6lab5b](https://user-images.githubusercontent.com/118953917/208401225-1e213365-e1d4-4e6f-b3e1-69f3ec30f403.jpg)
  
**For loop**

Notes: Example is taken from instructor's video
  

  ![day6lab5c](https://user-images.githubusercontent.com/118953917/208401247-12900240-0773-4f0a-a295-68fcff375432.jpg)

**Foreach in TCL**
  
Notes: Example is taken from instructor's video
  

  ![day6lab5d](https://user-images.githubusercontent.com/118953917/208401275-d94ab6f1-a9d6-451b-8d33-35f2d341cc3b.jpg)
  
**DC specific**
  
Notes: Example is taken from instructor's video
  

  ![day6lab5e](https://user-images.githubusercontent.com/118953917/208401299-0e0ed95c-59fa-4cc6-be77-454a942cb431.jpg)
  
</details>
  
<details>
  <summary>Lab 4:  TCL scripting</summary>
 

### Lab 4:  TCL scripting
  
>> Invoke dc_shell and try simple command in tcl scripting
  
> set i 0
  
> echo $i
  
> incr i
  
> echo $i 

**For loop**
  

  ![day6lab6a](https://user-images.githubusercontent.com/118953917/208401335-5e00a069-7a83-45bb-83f8-80c3ba67c2d2.jpg)
  
**While loop**
  

  ![day6lab6b](https://user-images.githubusercontent.com/118953917/208401355-bde4791c-60fc-4976-aacd-fe66af6c394f.jpg)
  
**Foreach loop**
  

  ![day6lab6c](https://user-images.githubusercontent.com/118953917/208401376-ae485660-2a5e-4e4b-be22-59fcddf41412.jpg)
  
**Foreach in collection**
  

  ![day6lab6d](https://user-images.githubusercontent.com/118953917/208401416-59907eba-3d11-46b1-aca1-46f989054374.jpg)
  

  ![day6lab6e](https://user-images.githubusercontent.com/118953917/208401453-67d6b045-9212-47b3-a8d2-65e6c5303748.jpg)
  
Another way to run the TCL script is by sourcing the gvim file using tcl scripting
> sh gvim myscript.tcl


![day6lab6f](https://user-images.githubusercontent.com/118953917/208401489-fb572ed7-8c29-445a-a6fa-82f513660a3d.jpg)
</details>

  
  
## Day-7

### Topic: Basic SDC constraints

<details>
  <summary>Introduction to STA</summary>
 

### Introduction to Static Timing Analysis (STA)

**Advanced Synthesis and STA using Design Compiler**

**STA Basics**

**Maximum and Minimum Delay Constraints**

![day7lab1a](https://user-images.githubusercontent.com/118953917/208686000-7da7df59-66a1-4852-acc1-82e3861dcb40.jpg)

**Why delay?**

By using water bucket analogy

Scenario 1: $\textcolor{red}{\text{Different}}$ amount of water inflow with the $\textcolor{red}{\text{same}}$ size of bucket.

Notes: Example figure is taken from instructor's video

![day7lab1b](https://user-images.githubusercontent.com/118953917/208686086-048909a3-e0e7-4cbb-8b19-9bc6e7ad78a1.jpg)
  
Scenario 1: $\textcolor{red}{\text{Same}}$ amount of water inflow with $\textcolor{red}{\text{different}}$ size of bucket.

Notes: Example figure is taken from instructor's video

  ![day7lab1c](https://user-images.githubusercontent.com/118953917/208686124-9c07015e-83ea-4a0b-a1b3-562532e1b507.jpg)
  
**Is delay of a cell constant?**
* Delay of a cell will be a function of input Transition which is the water inflow. 
* Delay of a cell will be a function of output load which is the size of the bucket.
  
  ![day7lab1d](https://user-images.githubusercontent.com/118953917/208686187-fbb5da82-515c-4658-b124-29a47fd8fec1.jpg)

**Timing arcs**
* Combinational cell -> Delay information from every input pin to every output pin which it can control.
  
  ![day7lab1e](https://user-images.githubusercontent.com/118953917/208686221-a37ade29-097b-44a7-b3df-158ac8a6b66b.jpg)

* Sequential cell -> can be DFF/D-latch
  
  -> Delay from clock to Q for D-flip flop
  
  -> Delay from clock to Q, delay from D to Q for D latch
  
  -> Setup and hold time 
  
![day7lab1f](https://user-images.githubusercontent.com/118953917/208686254-dcc45d95-460d-48bd-8b88-e4e39df82387.jpg)
  
 </details> 

<details>
  <summary>Constraints</summary>
 

### What are constraints?
  
**Timing paths**
  
![day7lab2a](https://user-images.githubusercontent.com/118953917/208686303-80ff2d78-65b0-4d05-b50d-565adfd34e57.jpg)

  
**Constraining the design**
  
Why constraints?
  
![day7lab2b](https://user-images.githubusercontent.com/118953917/208686332-9eaaf8bc-e010-4dc6-a0fa-26399c4ca734.jpg)

  
**Timing paths**
  
* Start point
  
  -> Input ports
  
  -> Clk pins of register
  
* End point
  
  -> Output ports
  
  -> D pins of DFF/D-latch
  
* Always the timing paths start at one of the start points and ends at one of the end points.
  
  -> Clk to D (reg-to-reg timing path)
  
  -> Clk to output (IO timing path)
  
  -> Input to D (IO timing path)
  
  -> Input to output (IO timing path that ideally shouldn't be present)
  
![day7lab2c](https://user-images.githubusercontent.com/118953917/208686404-63146af9-cffe-4acf-85db-a03ef948f9dc.jpg)

  
* Reg-to-reg: constrained by clock -> Tclk >= Tcq + Tcombi + Tsetup
  
* Reg-to-output: constrained by output external delay, output load and clock period 
  
* Input-to-reg: constrained by input external delay, input transition and clock period 
  
* Collectively the reg-to-output and input-to-reg are called IO paths and the delay modelling referred as IO delay modelling -> using standard interface specifications and budgeting based in interactions with other modules
  
</details> 

<details>
  <summary>IO Constraints</summary>
 

### Input transfer output load
  
Is IO modelling sufficient? 
  
![day7lab3a](https://user-images.githubusercontent.com/118953917/208686438-a656e8f2-9a32-4f31-975d-731993703bee.jpg)

  
Are IO delay and input transition modelling sufficient for IO path?
  
Note: IO path should be constrained for both maximum delay (setup) and minimum delay (hold)
  
![day7lab3b](https://user-images.githubusercontent.com/118953917/208686468-072ed17d-5645-448d-a3e8-ebc4af5fbf04.jpg)
</details> 

<details>
  <summary>Lab 1: Timing dot libs</summary>
 

### Lab 1: Timing .lib
  
>> Open .lib file
  
> gvim DC_WORKSHOP/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  
> :syn off
  
  ![day7lab4a](https://user-images.githubusercontent.com/118953917/208875467-f5c0a760-1893-4665-b37e-30d11b7ac78a.jpg)
  
Understanding in default max transition
  
![day7lab4b](https://user-images.githubusercontent.com/118953917/208875522-6492b38c-dc0f-447a-b503-734373bf5d01.jpg)  
  
Understanding in delay model: table look up
  
![day7lab4c](https://user-images.githubusercontent.com/118953917/208875583-9ee8d137-daa6-4305-a6c7-05415a7823e2.jpg)

>> To split gvim side by side
  
> :vsp 
  
![day7lab4d](https://user-images.githubusercontent.com/118953917/208875621-0885c41f-82fe-4850-b49c-b4583fdc94e7.jpg)
  
Internal power delay
  
Note: LHS is and2_2 while RHS is and2_0
  
![day7lab4e](https://user-images.githubusercontent.com/118953917/208875652-d5050b54-ea64-411f-b2af-654412a4271e.jpg)
  
Timing delay
  
![day7lab4f](https://user-images.githubusercontent.com/118953917/208875681-a322de6b-1e7a-4d90-8adf-b8555d78d7d2.jpg)
  
Timing sense and timing type in timing arcs
  
![day7lab4g](https://user-images.githubusercontent.com/118953917/208875709-de6c0d32-61f7-44c4-b0b9-977d62781ea6.jpg)
  
</details> 

<details>
  <summary>Lab 2: Exploring dot libs part 1</summary>
 

### Lab 2: Exploring .lib part 1

Details of pins 
  
![day7lab5a](https://user-images.githubusercontent.com/118953917/208875755-9b9ed68c-cc8e-473b-9b4c-84c87dbae8d9.jpg)

Rising/falling edge of the pins
  
![day7lab5b](https://user-images.githubusercontent.com/118953917/208875786-c5f849db-1204-40e1-93d0-c346f9f901b1.jpg)

Setup time of rising/falling edge of the clock pin

![day7lab5c](https://user-images.githubusercontent.com/118953917/208875819-39b2acfc-16f9-4a69-be3c-90904c99ba03.jpg)

>> Invoking dc_shell to look for DFF and D-latch name

> csh

> dc_shell

> echo $target_library

> get_lib_cells */* -filter "is_sequential==true"

![day7lab5d](https://user-images.githubusercontent.com/118953917/208875857-88aeb1f8-b78b-4b1d-b713-508548f3cc81.jpg)

</details> 

<details>
  <summary>Lab 3: Exploring dot libs part 2</summary>
 

### Lab 3: Exploring .lib part 2 

> list_lib
  
> get_lib_cells */*and*
  
> foreach_in_collection my_lib_cell [get_lib_cells */*and*] {
  
  set my_lib_cell_name [get_object_name $my_lib_cell]; 
  
  echo $my_lib_cell_name;  
  
  }
  
> get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/*
  
> foreach_in_collection my_pins [get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/*] {
  
  set my_pin_name [get_object_name $my_pins];
  
  set pin_dir [get_lib_attribute $my_pin_name direction];
  
  echo $my_pin_name $pin_dir;
  
  }

  
>> To check the direction of the cell
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/A direction
  

>> To check the output pin
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/A is_output
  
  
>> To check the input pin
  
>get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/A input
  
 
>> To get the functionality of the cell
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/X function
  
  
>> Try another gate
  
  
>> NAND gate with 4 inputs
  
> get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4_1/*
  

>> Repeat the same steps for forach_in_collection for nand4_1
  
  
>> AND gate with 2 inputs
  
> get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2b_1/*
  
  
>> Repeat the same steps for forach_in_collection for and2_b1
  
![day7lab6a](https://user-images.githubusercontent.com/118953917/208875892-ed546572-7921-4af7-9b62-8f7f65d7493b.jpg)
  
> sh gvim my_script.tcl
  
>> Insert the contents inside gvim, save and source the file 
  
> source my_script.tcl
  
  
>> To get the area value of the cell
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4b_2 area
  
  
>> To see the capacitance of B pin
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4b_2/B capacitance
  
  
>> To get the connection of the pin with the clock
  
> get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4b_2/B clock
  
![day7lab6b](https://user-images.githubusercontent.com/118953917/208875925-5a719a7c-910c-4d83-a988-25bbb5fcf9fe.jpg)
  
> get_lib_cells */* -filter "is_sequential == true"
  
  
>> Explore D-latch
  
  
>> To check whether each component is depending on pins/ports/cell/etc
  
> list_attribute -app
  
![day7lab6c](https://user-images.githubusercontent.com/118953917/208875968-dc77b926-70df-4884-897a-42ba7fb77df8.jpg)
  
</details> 

## Day-8

### Topic: Advanced SDC Constraints

<details>
  <summary>SDC Part1</summary>
 

### SDC Part1: Clock - Clock Tree Modelling - Uncertainty

**Advanced Synthesis and STA using Design Compiler**

**Advanced constraints, specifying constraints through SDC**

+ Timing path
  * Reg-to-reg: constrained by clock -> clock period 
  * Reg-to-output: constrained by output external delay, output load and clock period 
  * Input-to-reg: constrained by input external delay, input transition and clock period 
  
**What needs to be constrained for clocks?**

![image](https://user-images.githubusercontent.com/118953917/209547160-3b2465ee-2f28-46e5-a85e-a2682216a05b.png)

**Clock generation**

* Oscillator
* Phase-Locked Loop (PLL) 
* External clock source
* All of the above clock sources have inherent variations in the clock period due to stochastic effects

![image](https://user-images.githubusercontent.com/118953917/209547202-64208f1f-39be-4fe0-8874-c95eb0153137.png)
  
**Clock distribution**
  
Jitter: Stochastic variations of clock generation
  
![image](https://user-images.githubusercontent.com/118953917/209547219-516926a5-bc50-4791-a161-144b45220748.png)
  
**Clock skew**
  
* Clock Tree built during CTS -> Practical Clock Tree
  
* Logic optimization happens in synthesis -> Ideal Clock Tree
  
* Timing Clean path in synthesis may fail after STA
  
![image](https://user-images.githubusercontent.com/118953917/209547244-c618379a-2dab-4259-8188-878a6828ea09.png)
  
**Clock modelling**
  
* Period
* Source latency: time taken by the clock source to generate clock
* Clock Network Latency: time taken by clock distribution network
* Clock skew: clock path delay mismatches which causes difference in the arrival of the clock
  + CTS will balance the clocks, but still the skew cannot be reduced to 0
* Jitter: stochastic variations in the arrival of clock edge
  + Duty cycle jitter
  + Period jitter 
* Collectively clock skew and jitter are called Clock Uncertainty
  
![image](https://user-images.githubusercontent.com/118953917/209547266-2ba5968a-ceb8-4478-b6c4-13be3a956085.png)
  </details>
<details>
  <summary>SDC Part2</summary>
 

### SDC Part1: IO Delays
  
**Advanced Synthesis and STA using Design Compiler**

**Advanced constraints, specifying constraints through Synopsys Design Constraints (SDC)**

**How to constraint the design in DC?**
  
* DC takes constraints in the form of SDC 
  
![image](https://user-images.githubusercontent.com/118953917/209547347-511c0ac1-87e4-4b06-a646-8b9fe164651d.png)
  
**Commands of getting ports in DC**
  
> To get the ports
```
get_ports clk;                           (All ports containing clock)
get_ports *clk*;                         (Collection of ports containing clk)
get_ports *;                             (All ports of the design)
get_ports * -filter "direction == in";     (All input ports)
get_ports * -filter "direction == out";    (All output ports)
```
  
-> get_ports -> Query the ports in the design
+ For example; 
  * port
  * pin
  * clock

*Note: all of the names are case sensitive 

**Commands of getting clocks in DC**
  
> To get the clocks
```
get_clocks *                                        (All clocks in the design)
get_clocks *clk*                                    (All clocks containg clk)
get_clocks * -filter "period>10"                    (Filtering the clocks)
get_attribute [get_clocks_ my_clk] period           (Querying period of the mentioned clock)
get_attribute [get_clocks my_clk] is_generated      (Checking whether clock mentioned is generated or not)
report_clocks my_clk                                (Reporting the details of the clock)
```

**Querying the cells in the design**
  
![image](https://user-images.githubusercontent.com/118953917/209547377-5a64bd16-da43-4e90-9a7c-0759ef6fcab7.png) 

**Clock distribution**
  
![image](https://user-images.githubusercontent.com/118953917/209547415-7c81ece4-d884-4094-b3a9-40de1493552e.png)
  
Bringing the practicalities (latency, uncertainty) of clock network
  
![image](https://user-images.githubusercontent.com/118953917/209547435-6d8c7e48-d746-4d4d-a0d3-053d269570cb.png)
  
**Clocks: Waveform**
  
![image](https://user-images.githubusercontent.com/118953917/209547461-739d2845-a057-4043-bc2f-6179ca3a8546.png)
  
**Constraining IO paths**
  
![image](https://user-images.githubusercontent.com/118953917/209547507-9b73d080-41c5-47a9-b758-07852a0b66f8.png)
  
![image](https://user-images.githubusercontent.com/118953917/209547538-bb3e046f-efba-4ef3-b092-2e883f283fc5.png)
	
**Summary**
  
* create_clock
* set_clock_latency
* set_clock_uncertainty 
  + skew + jitter -> Pre-CTS
  + only jitter -> Post-CTS
* set_input_delay
* set_input_transition
* set_output_delay
* set_load
* get_ports, get_clocks, get_cells
  
</details>
<details>
  <summary>Lab 1: Loading design</summary>
 

### Lab 1: Loading design get_cells, get_ports, get_nets
  
> gvim lab8_circuit.v
  
![image](https://user-images.githubusercontent.com/118953917/209547591-73c16358-105d-4af2-82de-e596fe948645.png)
  
> Invoke dc_shell
```
csh                                                        
dc_shell                                
echo $target_library 
echo $link_library 
read_verilog DC_WORKSHOP/verilog_files/lab8_circuit.v 
link
compile_ultra
```
![image](https://user-images.githubusercontent.com/118953917/209547614-41c9d71a-1fc7-44da-b126-e97d029e81e9.png)

> Get ports
```
get_ports
  
foreach_in_collection my_port [get_ports *] {                      (Listing the collection of ports name)
set my_port_name [get_object_name $my_port];
echo $my_port_name;
}
  
get_ports rst
get_attribute [get_ports rst] direction                           (Display reset port direction)

foreach_in_collection my_port [get_ports *] {                     (Listing the collection of port name and its direction)
set my_port_name [get_object_name $my_port];
set dir [get_attribute [get_ports $my_port_name] direction];     
echo $my_port_name $dir;
}
```

![image](https://user-images.githubusercontent.com/118953917/209547642-d79c7ea6-a7d4-4825-85ea-62a03853d159.png)

> Get cells
```
get_cells *
get_attribute [get_cells U9] is_hierarchical                        (Checking the desired cell is hierarchical/not)
get_cells * -hier -filter "is_hierarchical == false"                (Listing the false hierarchical cell)
get_cells * -hier -filter "is_hierarchical == true"                 (Listing the true hierarchical cell)
```
  
![image](https://user-images.githubusercontent.com/118953917/209547666-fe7bb361-e71b-4c7f-a480-b85ed7cf036f.png)
  
  
> Get reference name of the cells
```
get_attribute [get_cells REGA_reg] ref_name                         (Getting the reference name of the cell)
  
foreach_in_collection my_cell [get_cells * -hier] {                 (Listing cell name and its reference name)
set my_cell_name [get_object_name $my_cell];
set rname [get_attribute [get_cells $my_cell_name] ref_name];
echo $my_cell_name $rname;
} 
```

![image](https://user-images.githubusercontent.com/118953917/209547686-7edde42e-7a39-4bc7-8298-0fe6434ad306.png)

> Writing DDC 
```
write -f ddc -out lab8_circuit.ddc
csh
design_vision
read_ddc DC_WORKSHOP/verilog_files/lab8_circuit.ddc
get_nets *
all_connected N1
all_connected n5

foreach_in_collection my_pin [all_connected n5] {                   (Listing the driver of the net)
set pin_name [get_object_name $my_pin];
set dir [get_attribute [get_pins $pin_name] direction];
echo $pin_name $dir;
}
```
![image](https://user-images.githubusercontent.com/118953917/209547714-293a0e43-0d98-452a-a16d-73cc140199f5.png)
	
![image](https://user-images.githubusercontent.com/118953917/209547737-d67a4e53-41e9-4858-85bb-21d26ce72a4e.png)

Note: In digital design, net can only have one driver
  
Example: 
  
![image](https://user-images.githubusercontent.com/118953917/209547771-e4aff53d-73bb-4abc-afdb-ddb691ba76c1.png)
  
</details>
<details>
  <summary>Lab 2: Loading design</summary>
 

### Lab 2: Loading design get_pins, get_clocks, querying_clocks
  
> Get pins 
```
get_pins *

foreach_in_collection my_pin [get_pins *] {                            (Listing out the pins)
set pin_name [get_object_name $my_pin];
echo $pin_name;
}

get_attribute [get_pins REGC_reg/RESET_B] direction
get_attribute [get_pins REGC_reg/RESET_B] clock
get_attribute [get_pins REGC_reg/CLK] clock
  
foreach_in_collection my_pin [get_pins *] {
set pin_name [get_object_name $my_pin];
set dir [get_attribute [get_pins $pin_name] direction];
echo $pin_name $dir;
}
```
  
![image](https://user-images.githubusercontent.com/118953917/209547817-e39169be-520f-4d0c-b646-29c37fe1b9b6.png)
  
> Make use of regexp
>> 0 if it is not found, 1 if it is matched
```
regexp abcd efgh
regexp abcd abcd
set a in
regexp $a in
regexp $a out

foreach_in_collection my_pin [get_pins *] {                             (Listing input pin name with clock)
set pin_name [get_object_name $my_pin];                                                                                      
set dir [get_attribute [get_pins $pin_name] direction];                                                      
if { [regexp $dir in] } {                                                                                    
if { [get_attribute [get_pins $pin_name] clock] } {                                          
echo $pin_name;                                                                                              
}                                                                                                            
}                                                                                                            
}
```

![image](https://user-images.githubusercontent.com/118953917/209547853-dfec6797-ed26-4631-a9b8-65ee0dc8ac11.png)
  
> Scripting in gvim 
```
sh gvim query_clock_pin.tcl

foreach_in_collection my_pin [get_pins *] {                              (Listing input pin name with clock - The pin is meant to be a clock pin/not)
	set my_pin_name [get_object_name $my_pin];
        set dir [get_attribute [get_pins $my_pin_name] direction];                                                                                              
	if { [regexp $dir in] } {
		if { [get_attribute [get_pins $my_pin_name] clock] } {
		       echo $my_pin_name $clk_name;

		}
	}
}	
```
   
> Checking if there is any clock coming in
```
get_attribute [get_pins REGA_reg/CLK] clock
get_attribute [get_pins REGA_reg/CLK] clocks
```

> Get clock
```
get_clocks *
```
  
![image](https://user-images.githubusercontent.com/118953917/209547885-0ea80cfa-1929-4918-bf93-229334f35a54.png)
</details>
<details>
  <summary>Lab 3: Clock waveform</summary>
 

### Lab 3: Creating clock waveform

> Get the name of top module that is currently working, get ports, create clock and attribute
```
current_design										(Display current module)
get_ports *
create_clock -name MYCLK -per 10 [get_ports clk]
get_clocks *
get_attribute [get_clocks MYCLK] period
get_attribute [get_clocks MYCLK] is_generated						(If false, it is the master clock)
get_attribute [get_pins REGA_reg/CLK] clocks
report_clocks *										(Reviewing clocks report)
get_attribute [get_pins REGA_reg/CLK] clocks
get_attribute [get_ports out_clk] clocks
sh gvim query_clock_pin.tcl
	
foreach_in_collection my_pin [get_pins *] {						(Contents inside gvim)
	set my_pin_name [get_object_name $my_pin];
        set dir [get_attribute [get_pins $my_pin_name] direction];                                                                                              
	if { [regexp $dir in] } {
		if { [get_attribute [get_pins $my_pin_name] clock ] } { 
			set clk [get_attribute [get_pins $my_pin_name] clocks]; 
	# set clk_name [get_object_name [get_attribute [get_pins $my_pin_name] clocks]];
			set clk_name [get_object_name $clk];
 			echo $my_pin_name $clk_name;

		}
	}
}
	
source query_clock_pin.tcl								(Source the gvim)
```
![image](https://user-images.githubusercontent.com/118953917/209548104-723892a1-797e-4f1b-8ed3-201a1d050774.png)
	
> Creating clock and reviewing clock report
```
get_cells U13
get_attribute [get_cells U13] ref_name
get_attribute [get_cells U14] ref_name
create_clock -name BAD_CLK -per 10 [get_pins U14/Y]
get_clocks *
report_clocks *								(From the report, it's not reaching any clock pin/data path of any flop)
all_connected U14/Y
all_connected n3
```
	
![image](https://user-images.githubusercontent.com/118953917/209548139-c21c44c1-be63-4740-8572-0ec0a9217b13.png)

> Removing clock and adjusting multiple clock waveforms
```
remove_clock BAD_CLK
get_clocks *
report_clocks *
remove_clock MYCLK
create_clock -name MYCLK -per 10 [get_ports clk] -wave {5 10}				(Rising edge = 5; falling edge = 10)
report_clocks *
remove_clock MYCLK
create_clock -name MYCLK -per 10 [get_ports clk] -wave {0 2.5}				(Order is not important)
report_clocks *
remove_clock MYCLK
create_clock -name MYCLK -per 10 [get_ports clk] -wave {15 20}
report_clocks *
```

![image](https://user-images.githubusercontent.com/118953917/209548165-2c4f4c42-a82d-4536-85f6-1cccd533bdca.png)
	
</details>
<details>
  <summary>Lab 4: Clock Network Modelling</summary>
 

### Lab 4: Clock Network Modelling: Uncertainty & report_timing
  
* Clock skew -> clock network due to imbalance delay between the flops
* Clock jitter -> Random variations in clock edge, coming from the source
* Clock Tree Synthesis (CTS) -> the tool to minimize the imbalance but it cannot make it zero ("0")
* Clock_uncertaint
	+ Skew + jitter (in pre-CTS)
	+ Jitter alone since the clock network is actualy built (in post-CTS)
	
![image](https://user-images.githubusercontent.com/118953917/209548189-207a7007-d804-4f4e-9542-815b9198d5f9.png)

> Modelling the clock tree attribute
```
report_clocks *
set_clock_latency -source 1 [get_clocks MYCLK]					(Modelling the source latency)
set_clock_latency 1 [get_clocks MYCLK]						(Modelling the network latency)
set_clock_uncertainty 0.5 [get_clocks MYCLK]					(Max delay for setup time by default)
set_clock_uncertainty -hold 0.1 [get_clocks MYCLK]				(Min delay for hold time) 
```
	
![image](https://user-images.githubusercontent.com/118953917/209548207-0a3e6d53-ce51-4edd-acce-6fec2347b3c7.png)
	
> Clock timing
```
remove_clock *
get_clocks *
report_timing
report_timing -to REGC_reg/D							(Got nothing to constraint)
create_clock -name MYCLK -per 10 [get_ports clk]
report_timing -to REGC_reg/D
```
	
![image](https://user-images.githubusercontent.com/118953917/209548231-1606e86b-c8a2-4298-b382-5f6fc83e445e.png)
	
> Model clock behavior and report timing
```
set_clock_latency -source 2 [get_clocks MYCLK]
set_clock_latency 1 [get_clocks MYCLK]
set_clock_uncertainty -setup  0.5 [get_clocks MYCLK]
set_clock_uncertainty -hold  0.1 [get_clocks MYCLK]
report_timing -to REGC_reg/D
```

![image](https://user-images.githubusercontent.com/118953917/209548245-36cc6d8f-7c3b-4bec-a77c-2e7ad7f874ff.png)
	
> Hold time
```
report_timing -to REGC_reg/D -delay min
```
	
![image](https://user-images.githubusercontent.com/118953917/209548278-1f83bd69-d551-4b67-975c-1829ea55a905.png)
	
> Report of all ports
```
report_port -verbose
```
	
![image](https://user-images.githubusercontent.com/118953917/209548295-44b174ce-93c1-4c39-a497-d893337ca2d1.png)
	
	
</details>
<details>
  <summary>Lab 5: IO Delays</summary>
 

### Lab 5: IO Delays
  
![image](https://user-images.githubusercontent.com/118953917/209548311-f40b3814-2e08-4f5c-a535-26295823dae4.png)
	
> IO Constraints
```
report_timing -from IN_A
report_timing
report_timing -to OUT_Y
```
	
![image](https://user-images.githubusercontent.com/118953917/209548340-884ddc87-b125-4ec9-8727-5d9f0f801533.png)
	
> Listing all the ports
```
report_port -verbose
```
	
![image](https://user-images.githubusercontent.com/118953917/209548360-7b4f3c30-0bdf-4022-a5e3-84244a1ca94f.png)
	
> Modelling the delay
```
set_input_delay -max 5 -clock [get_clocks MYCLK] [get_ports IN_A]				(Setting input delay)
set_input_delay -max 5 -clock [get_clocks MYCLK] [get_ports IN_B]
report_port -verbose
report_timing -from IN_A
report_timing -from IN_A -trans -net -cap
report_timing -from IN_A -trans -net -cap -nosplit > a
sh gvim a
```

![image](https://user-images.githubusercontent.com/118953917/209548381-41af4143-b650-481e-b370-51f81a2bd7f0.png)
	
![image](https://user-images.githubusercontent.com/118953917/209548404-5074afa1-bcab-4430-a26f-192f48fc5525.png)
	
> Hold timing
```
report_timing -from IN_A -trans -net -cap -nosplit -delay_type min
```
	
![image](https://user-images.githubusercontent.com/118953917/209548431-74172e5c-2cdc-4219-9f26-79819165909a.png)
	
> Modelling the hold time 
```
set_input_delay -min 1 -clock [get_clocks MYCLK] [get_ports IN_A]
set_input_delay -min 1 -clock [get_clocks MYCLK] [get_ports IN_B]
report_timing -from IN_A -trans -net -cap -nosplit -delay_type min
```
	
![image](https://user-images.githubusercontent.com/118953917/209548454-4fe83460-3285-473d-a79b-c0fabcb05041.png)
	
> Setting new maximum value
```
set_input_delay -max 5 -clock [get_clocks MYCLK] [get_ports IN_A]
sh gvim a
```
	
![image](https://user-images.githubusercontent.com/118953917/209548480-9ee82772-2ebc-4000-b595-65cbacfcdfb2.png)
	
> Setting input transition
```
set_input_transition -max 0.3 [get_ports IN_A]
set_input_transition -max 0.3 [get_ports IN_B]
set_input_transition -min 0.1 [get_ports IN_B]
set_input_transition -min 0.1 [get_ports IN_A]
report_timing -from IN_A -trans  -cap -nosplit > a_trans
```
	
![image](https://user-images.githubusercontent.com/118953917/209548506-1026575b-c0eb-4a04-ba6a-c46501056e37.png)
	
> Setting output transition
```
set_output_delay -max 5 -clock [get_clocks MYCLK] [get_ports OUT_Y]
set_output_delay -min 1 -clock [get_clocks MYCLK] [get_ports OUT_Y]
report_timing -to OUT_Y
report_timing -to OUT_Y -cap -trans
```
	
![image](https://user-images.githubusercontent.com/118953917/209548527-d3feaac2-0f9f-4a68-b55a-87f58884e1d8.png)
	
> Setting for load
```
set_load -max 0.4 [get_ports OUT_Y]
report_timing -to OUT_Y -cap -trans
```
	
![image](https://user-images.githubusercontent.com/118953917/209548546-1a570a8c-af03-44ab-b060-2c19c1d0f7a0.png)
	
> Setting minimum delay
```
report_timing -to OUT_Y -cap -trans -delay min
```
	
> Setting another load for minimum delay
```
report_timing -to OUT_Y -cap -trans -delay min
```
	
![image](https://user-images.githubusercontent.com/118953917/209548567-8982e988-5709-454f-98c9-ae39b498246c.png)
	
</details>
<details>
  <summary>SDC Part3</summary>
 

### SDC Part3: Generated clock

**Notes**
![image](https://user-images.githubusercontent.com/118953917/209548593-e87f2035-ef23-4ab2-af7b-cdd647b7aa2c.png)
	
**Generated clocks**

* Generated clocks: always created with respect to master clocks (clocks at clock source i.e. PLL/oscillator or primary IO port)

```
create_generated_clock -name MY_GEN_CLK -master [get clocks MY_CLK] -source [get_ports CLK] -div 1 [get_ports OUT_CLK]
```

where;
* [get clocks MY_CLK] -source [get_ports CLK] 
	+ wrt what the generated clock is created
* -div
	+ Refers to the division value of generated clock (useful for clock dividers)
* [get_ports OUT_CLK]
	+ Generated definition point where the generated clock is created 
* Out_Y need to be constrained wrt the generated clock
	
**Constraining the design**
	
![image](https://user-images.githubusercontent.com/118953917/209548621-38adcc67-bb3e-4d40-b9ea-0dd5ffb097f3.png)

![image](https://user-images.githubusercontent.com/118953917/209548643-4bf30f41-2483-4114-9117-9341fffe2714.png)

</details>
<details>
  <summary>Lab 6: Generated clock</summary>
 

### Lab6: Generated clock

```
report_timing -to OUT_Y
```
	
![image](https://user-images.githubusercontent.com/118953917/209548658-671239fa-0b0b-422c-a707-1356d6099079.png)
	
> Creating generated clock
```
create_generated_clock -name MYGEN_CLK -master MYCLK -source [get_ports clk] -div 1 [get_ports out_clk]
report_clocks
get_attribute [get_clocks MYGEN_CLK] is_generated								(True if it is generated clk)
get_attribute [get_clocks MYCLK] is_generated									(False if it is generated clk - master clk)
```
	
> Modelling MYGEN_CLK
```
set_clock_latency -max 1 [get_clocks MYGEN_CLK]
set_output_delay -max 5 [get_ports OUT_Y] -clock [get_clocks MYGEN_CLK]
set_output_delay -min 1 [get_ports OUT_Y] -clock [get_clocks MYGEN_CLK]
report_timing -to OUT_Y
```
	
![image](https://user-images.githubusercontent.com/118953917/209548669-bc6ad376-aadc-4dd6-ac1e-ecd9b3046796.png)
	
> Modifying lab8_circuit.v
```
sh gvim DC_WORKSHOP/verilog_files/lab8_circuit.v
:vsp lab8_circuit_modified.v 
```
	
![image](https://user-images.githubusercontent.com/118953917/209548680-add03dc2-c565-47a5-8e03-d43640f10a2f.png)
	
> Resetting the design
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/lab8_circuit_modified.v
sh gvim DC_WORKSHOP/verilog_files/lab8_cons.tcl
link
source DC_WORKSHOP/verilog_files/lab8_cons.tcl
report_clocks
get_generated_clocks
```
	
![image](https://user-images.githubusercontent.com/118953917/209548705-eed00ea4-2abd-42cc-8711-e9a5d1207837.png)
	
> Reporting the ports
```
report_port -verbose
```

The design is completely constrained

![image](https://user-images.githubusercontent.com/118953917/209548729-afb555d7-e69d-49a7-97d7-5e6617abf752.png)	
	
</details>
<details>
  <summary>SDC Part4</summary>
 

### SDC Part4: vclk, max_latency, rise_fall IO Delays

**Input delay**
	
* Positive delay 
	+ data comes after clk edge
	+ for max is tightening
* Negative delay 
	+ data comes before clk edge
	+ for max is relaxing
	
* min delay 
	+ Positive is tightening the path
	+ Negative is relaxing the path
	
```
set_input_delay –max 3 –clock myclk [get_ports IN_A]
```
	
* create_clock_name myclk –per 10 [get_ports clk ]
* To get available time -> available time = [clock period – uncertainty – input delay] 
* Positive for max is tightening
	
```
set_input_delay –max -3 –clock myclk [get_ports IN_A]
```
	
* Negative i.e. -3 is the delay where before the rise edge, the data was stable, however, the clock got more delayed compared to the data
* i.e. 10 -[-3] = 13 ns
* Negative delay for max is relaxing 
	
```
set_input_delay –min 1  –clock myclk [get_ports IN_A]
```
	
* Positive delay –> the data comes after clock edge
* 1 ns is the hold time and it helps to meet the hold time
* Positive delay becomes relax
	
```
set_input_delay –min -1 –clock myclk [get_ports IN_A]
```
	
* Negative i.e. -1 is delay where the data comes after clock edge
* Note that we need to avoid the hold failures, hence, we need to delay the data
* Negative for min delay is tightening 
	
![image](https://user-images.githubusercontent.com/118953917/209548761-fcc143e7-1433-487f-9197-56b1a2b09142.png)
	
**Output delay**
	
```
set_output_delay –max 3 -clock myclk [get_ports IN_A]
```
	
* set clock period to 10 ns 
* To get avalaibale time -> available time = clock period – external delay 

```
set_output_delay –max -3 -clock myclk [get_ports IN_A]
```
	
```
set_output_delay –min 1 -clock myclk [get_ports IN_A]
```
	
* Relaxing the hold time
* Independent of the clock period 
	
```
set_output_delay –min -1 -clock myclk [get_ports IN_A]
```
	
* Tightening the hold time
* Independent of the clock period
* -min delay -> clock relatively getting pushed wrt the data
	
**IO constraints re-visited**
	
![image](https://user-images.githubusercontent.com/118953917/209548788-ac62ef3b-3461-4252-9b67-92097a7d0d20.png)
![image](https://user-images.githubusercontent.com/118953917/209548805-7d50e9ff-d06c-4887-b2e5-b46b8264bcf2.png)
![image](https://user-images.githubusercontent.com/118953917/209548924-2146da70-dea6-4930-9fcb-7272f39cb89b.png)
![image](https://user-images.githubusercontent.com/118953917/209548952-5ebe1835-cb2f-486b-b877-b3d5fd4f061b.png)
![image](https://user-images.githubusercontent.com/118953917/209548981-c09d0a9e-38d1-4a19-bd72-bbad8fee77f6.png)
	
</details>
<details>
  <summary>Lab 7: Set_Max_delay</summary>
 

### Lab 7: Set_Max_delay

![image](https://user-images.githubusercontent.com/118953917/209549018-a529d492-b5a2-49ef-8650-19939e5d3c99.png)
	
> Resetting the design to lab14_circuit.v
```
reset_design
sh gvim DC_WORKSHOP/verilog_files/lab14_circuit.v
read_verilog DC_WORKSHOP/verilog_files/lab14_circuit.v
source DC_WORKSHOP/verilog_files/lab8_cons.tcl 
report_timing								(Report timing in terms of gtech cells)
```
	
![image](https://user-images.githubusercontent.com/118953917/209549039-8787ac5c-ef25-40cf-88e4-eb038238b0e6.png)
	
> Linking the design
```
link
compile_ultra
report_timing
```
	
![image](https://user-images.githubusercontent.com/118953917/209549055-e0f23d8c-93e5-4df4-a799-4b91f2c5962c.png)
	
> Checking the path whether it is constrained/not
```
get_ports *
report_timing -to OUT_Z
report_timing -from IN_C
```
	
![image](https://user-images.githubusercontent.com/118953917/209549141-08dc3ff6-ceee-4a44-9c6a-2084c9fa69d5.png)
	
> Another helpful commands to try on
```
all_inputs							(Listing all inputs)
all_outputs							(Listing all outputs)
all_clocks 							(Listing all clocks)
all_registers 							(Listing all registers)
all_registers -clock MYCLK 					(Listing registers clocked by MYCLK)
all_fanout -from IN_A 						(Listing all fanouts of desired input)
all_fanout -flat -endpoints_only -from IN_A
all_fanin -to REGA_reg/D
all_fanin -flat -startpoints_only -to REGA_reg/D
```
	
Note: ENDPOINTS of a timing path => D/output pin

> Constraining path to Z
Note that no path to OUT_Z yet
```
set_max_delay 0.1 -from [all_inputs] -to [get_port OUT_Z]
report_timing -to OUT_Z -sig 4
```
	
Path is not constraint properly, DC do not optimized to meet the path
	
![image](https://user-images.githubusercontent.com/118953917/209549166-1979fbc3-9ef8-4b1a-b949-a0dd05be00e7.png)
	
> Optimizing the delay
	
```
compile_ultra
report_timing -to OUT_Z -sig 4
```
	
The tool is picking up other cells
	
![image](https://user-images.githubusercontent.com/118953917/209549204-d26fe307-a6b3-4c1e-a159-7064fcc4d7f5.png)
	
> Invoking design_vision
```
write -f ddc -out DC_WORKSHOP/verilog_files/lab14.ddc
reset_design
read_ddc DC_WORKSHOP/verilog_files/lab14.ddc
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/209549228-c4c2e809-0499-4bb6-9545-8fc7825e0858.png)
	
</details>
<details>
  <summary>Lab 8: VCLK</summary>
 

### Lab 8: VCLK

**Virtual clock**
* Other ways to constraint path from IN_C or IN_D to Z
* Input delay and output delay with respect to virtual clock
	
**While using VCLK**
* First method: set_max_delay
* Second method: use virtual clock where a clock is created without a definition point
	
> Using VCLK
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/lab14_circuit.v
link
source DC_WORKSHOP/verilog_files/lab8_cons.tcl
compile_ultra
report_clocks
report_timing -to OUT_Z
```
	
![image](https://user-images.githubusercontent.com/118953917/209549269-37b2fb49-8308-41b9-801b-fc73199f82f8.png)	
```
create_clock -name MYVCLK -per 10
report_clocks
```
	
The highlighted one is virtual clock since it has no source
	
![image](https://user-images.githubusercontent.com/118953917/209549295-c3d2a9ed-3a6e-408b-9340-815a008168f3.png)
	
> Annotating IO Delays
```
set_input_delay -max 5 [get_ports IN_C] -clock [get_clocks MYVCLK]
set_input_delay -max 5 [get_ports IN_D] -clock [get_clocks MYVCLK]
set_output_delay -max 4.9 [get_ports OUT_Z] -clock [get_clocks MYVCLK]
report_timing
```
	
![image](https://user-images.githubusercontent.com/118953917/209549331-a1547370-569c-42d1-8be8-abc0ffc368ab.png)
	
> Optimizing 
```
compile_ultra
report_timing -to OUT_Z -sig 4
report_port -verbose
```

![image](https://user-images.githubusercontent.com/118953917/209549363-fa392726-ada0-455d-8aef-100f65a3c50a.png)
	
</details>

## Day-9

### Topic: Optimizations

<details>
  <summary>Optimizations Combinational Opt</summary>
 

### Optimizations Combinational Opt

**Advanced synthesis and STA using Design Compiler**
	
**Logic optimizations**
	
**What are the optimization goals?**
* Cost function based optimizations
	+ Optimization till the cost is met
	+ Over optimization of one goal will harm other goals 
	+ Goals for synthesis: ensure to meet timing, area, and power (Those are 3 metrics of netlist which will be contradictory)
	
**Combinational Logic Optimisation**
* To squeeze the logic to get the most optimised design in terms of Area and Power saving
* Constant propagation technique used: Direct optimisation
* Boolean logic optimisation technique: K-map and Quine McKluskey

![image](https://user-images.githubusercontent.com/118953917/210128758-35553b5a-2243-4037-9d86-f8b2faea5bb7.png)

![image](https://user-images.githubusercontent.com/118953917/210128764-1951205b-1981-4de9-bb02-9a5b572b848c.png)

![image](https://user-images.githubusercontent.com/118953917/210128770-64515713-e924-4f06-b958-3f109930e33c.png)

![image](https://user-images.githubusercontent.com/118953917/210128777-5bae9223-396a-4970-8517-c759a5a57a44.png)

![image](https://user-images.githubusercontent.com/118953917/210128795-953d1979-6e07-414a-a21f-33524fcf9b87.png)
	
</details>
	
<details>
  <summary>Sequential Logic Optimizations</summary>
 

### Sequential Logic Optimizations
	
* Basic
	+ Sequential constant propagation
	+ Retiming
	+ Unused flop removal
	+ Clock gating
	
* Advanced 
	+ State optimisation
	+ Sequential logic cloning (Floor plan aware synthesis)
	
**Sequential constant**
	
![image](https://user-images.githubusercontent.com/118953917/210128815-1bca84f4-4a26-427d-81d4-764828eaf89a.png)

![image](https://user-images.githubusercontent.com/118953917/210128821-759b7612-292b-494e-a093-e2915692edde.png)

![image](https://user-images.githubusercontent.com/118953917/210128828-515c10f8-a263-4d55-a6b8-b2f40fd4f8db.png)

![image](https://user-images.githubusercontent.com/118953917/210128832-16e6a103-a4d4-4193-8100-574cb746be72.png)

![image](https://user-images.githubusercontent.com/118953917/210128855-b14d51c7-5f77-4554-a0e0-b55ddd245ed6.png)


**Controlling sequential optimizations in DC**
```
compile_seqmap_propagate_constants 
compile_delete_unloaded_sequential_cells
compile_register_replication						(For cloning the registers)
```
</details>
	
<details>
  <summary>Lab 1 part 1</summary>
 

### Lab 1: Combinational Optimizations part 1

> Setup environment for dc_shell
```
/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop
csh
dc_shell
```
	
> To view the scripting of all opt_checks
```
sh gvim DC_WORKSHOP/verilog_files/opt_check*.v -o
```

![image](https://user-images.githubusercontent.com/118953917/210128871-3ea71ff9-a112-4733-a0a8-4649b0f7bab1.png)

![image](https://user-images.githubusercontent.com/118953917/210128876-23527a11-f377-4f4e-9ee8-d2ab6cee034e.png)

![image](https://user-images.githubusercontent.com/118953917/210128882-6894dc44-8234-47cc-a999-88c5d83ee1d1.png)

![image](https://user-images.githubusercontent.com/118953917/210128889-ed74e739-e06a-493c-9d5a-bfb7b3f43fbe.png)

![image](https://user-images.githubusercontent.com/118953917/210128896-339c6be9-0b3f-4124-8a07-d43ffe0ff5be.png)

> opt_check
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/opt_check.v
report_timing
link 
compile
report_timing
get_cells *
report_timing -to y2
report_timing -to y1
write -f ddc -out DC_WORKSHOP/verilog_files/opt_check.ddc
```
	
```
design_vision
read_ddc DC_WORKSHOP/verilog_files/opt_check.ddc
```

![image](https://user-images.githubusercontent.com/118953917/210128910-d17033bf-5c43-41d0-874d-77557f1cb14b.png)

![image](https://user-images.githubusercontent.com/118953917/210128922-b3b5c561-2dcc-414b-a0c7-fa18d16fe87d.png)
	
> opt_check2
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/opt_check2.v
link 
compile
write -f ddc -out DC_WORKSHOP/verilog_files/opt_check2.ddc
	
read_ddc DC_WORKSHOP/verilog_files/opt_check2.ddc				(In design_vision)
```
	
![image](https://user-images.githubusercontent.com/118953917/210128939-b1e06619-f654-4358-a949-bcd49469be18.png)
	
> opt_check3
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/opt_check3.v
link
compile
write -f ddc -out DC_WORKSHOP/verilog_files/opt_check3.ddc
	
read_ddc DC_WORKSHOP/verilog_files/opt_check3.ddc
```
	
![image](https://user-images.githubusercontent.com/118953917/210128945-398a1927-f7c0-4677-aea4-78e96e7760ff.png)
	
> opt_check4
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/opt_check4.v
link
compile
write -f ddc -out DC_WORKSHOP/verilog_files/opt_check4.ddc
	
read_ddc DC_WORKSHOP/verilog_files/opt_check4.ddc
```
	
![image](https://user-images.githubusercontent.com/118953917/210128956-87cafbcf-13ed-43d3-9644-50e9c5dff9bc.png)
	
```
report_timing -to y
set_max_delay .06 -from [all_inputs] -to [get_ports y]
report_timing
report_timing -sig 4
compile_ultra
report_timing
get_lib_cells */sky130_fd_sc_hd__xnor2*
size_cell U3 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__xnor2_4
report_timing
compile_ultra
```
	
![image](https://user-images.githubusercontent.com/118953917/210128969-28586244-5dd1-4662-b4e0-471da87b2636.png)

</details>
	
<details>
  <summary>Lab 1 part 2</summary>
 

### Lab 1: Combinational Optimizations part 2
```
sh gvim DC_WORKSHOP/verilog_files/resource_sharing_mult_check.v
read_verilog DC_WORKSHOP/verilog_files/resource_sharing_mult_check.v
link
compile_ultra
write -f ddc -out DC_WORKSHOP/verilog_files/resource_sharing_mult_check.ddc
	
reset_design
read_ddc DC_WORKSHOP/verilog_files/resource_sharing_mult_check.ddc
```
	
![image](https://user-images.githubusercontent.com/118953917/210128975-b4d48749-8ce0-44f9-adc1-eaacab5a7fdc.png)

> In design_vision
```
report_area
report_timing
set_max_delay -from [all_inputs] -to [all_outputs] 2.5
report_timing
compile_ultra
report_timing
```	
	
![image](https://user-images.githubusercontent.com/118953917/210128981-40dd8c6c-02b4-4893-b8c6-cf875a5c90ab.png)
	
![image](https://user-images.githubusercontent.com/118953917/210128989-699fd768-98fe-4319-9d27-4f7828cf332a.png)
	
	
```
report_area
set_max_delay -from sel -to [all_outputs] 0.1
report_timing
compile_ultra
report_area
report_timing
report_timing -sig 4
```
	
![image](https://user-images.githubusercontent.com/118953917/210128995-dd719518-7b99-4628-a23c-34dda6237bb9.png)
	
![image](https://user-images.githubusercontent.com/118953917/210128998-5509f3be-875a-484c-8de8-3a9e3c39c2aa.png)
	
```
set_max_area 800
compile_ultra
report_timing
report_area
```
	
![image](https://user-images.githubusercontent.com/118953917/210129008-eddc3233-961e-4cf0-876c-28fc10dcc449.png)
	
![image](https://user-images.githubusercontent.com/118953917/210129015-309304f1-5046-4cee-875d-d108c5dda74f.png)
	
</details>
	
<details>
  <summary>Lab 2</summary>
 

### Lab 2: Sequential Optimizations

```
sh gvim DC_WORKSHOP/verilog_files/dff_cons* -o
```

![image](https://user-images.githubusercontent.com/118953917/210129023-fe573204-17ea-44df-8bd3-5d282c6248cc.png)

![image](https://user-images.githubusercontent.com/118953917/210129031-1ee147c2-b401-4a76-88e7-9e66ae5d41d7.png)

![image](https://user-images.githubusercontent.com/118953917/210129040-a0ccfd74-8332-47f3-bd99-fc71311983dc.png)

![image](https://user-images.githubusercontent.com/118953917/210129045-06351669-d469-4fe0-a912-2386327cfee1.png)

![image](https://user-images.githubusercontent.com/118953917/210129051-bad7474a-e2f7-481e-bf68-7bde38fc2644.png)

![image](https://user-images.githubusercontent.com/118953917/210129054-8a75683b-c0d0-4f2b-8152-049c37eb12c7.png)

	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/dff_const1.v
link
compile
get_cells

foreach_in_collection my_cell [get_cells *] {
set cell_name [get_object_name $my_cell];
echo $cell_name; 
}
	
foreach_in_collection my_cell [get_cells *] {
set cell_name [get_object_name $my_cell];
set rn [get_attribute [get_cells $cell_name] ref_name];  
echo $cell_name $rn; 
}
```
	
![image](https://user-images.githubusercontent.com/118953917/210129056-fc0596f3-4410-49fd-9cb1-e9cecb5f0843.png)
	
```
design_vision
read_verilog DC_WORKSHOP/verilog_files/dff_const1.v
link
compile
```

![image](https://user-images.githubusercontent.com/118953917/210129067-a967fa54-9528-4b2a-8f3b-77b2b4ff7d30.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/dff_const2.v
link
compile
```
	
![image](https://user-images.githubusercontent.com/118953917/210129072-180059aa-3718-4d01-b7a1-df96e859c96c.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/dff_const3.v
link
compile
```
	
![image](https://user-images.githubusercontent.com/118953917/210129088-aaf3f023-1ed4-485d-b9a1-4c23eabe6a06.png)
	
```
reset_design 
read_verilog DC_WORKSHOP/verilog_files/dff_const2.v
set compile_seqmap_propagate_constants false
link
compile
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129098-a09c0313-2c77-451d-b9c7-ca99ead9e6cb.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/dff_const4.v
link
set compile_seqmap_propagate_constants true
compile_ultra
start_gui
```
![image](https://user-images.githubusercontent.com/118953917/210129122-5e28bc24-7a91-4731-bcdd-b77b07e70ec6.png)	
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/dff_const5.v
link
compile
```
	
![image](https://user-images.githubusercontent.com/118953917/210129118-2595f2f6-254e-4b28-a59e-de91cb89104a.png)
	
</details>
	
<details>
  <summary>Special Optimizations</summary>
 

### Special Optimizations

**Register retiming**
	
**Why flops were added?**
* To reduce the number of delay 
	+ From the figure, each flop has 47 ns slack. So, the combinational logic is divided to some partitions between the flops resulting those slacks of the critical path to be decreased as well as making the freaquency increases.
	+ This is what we called Register Retiming
	
![image](https://user-images.githubusercontent.com/118953917/210129133-2c7c49be-7238-4275-8fcb-b0e75d12f81d.png)
	
**Boundary Optimization**
	
**How to control boundary optimization?**
```
set_boundary_optimization <design><true|false>
set_boundary_optimization module_sub false
```
	
![image](https://user-images.githubusercontent.com/118953917/210129139-17283ab1-ac0b-4a49-8444-c204ce7c5178.png)
	
**Multi-cycle path**
	
![image](https://user-images.githubusercontent.com/118953917/210129152-c56fe10f-01b2-4632-89b1-16f84fdad647.png)
	
**False path**
	
> Paths that are not valid for STA
```
set false_path -from <> -to <>
set false_path -through <>
```

![image](https://user-images.githubusercontent.com/118953917/210129162-9270bdb6-f3ab-4a02-a3f3-6e4224b00cc0.png)
	
**External load vs internal load**
	
![image](https://user-images.githubusercontent.com/118953917/210129172-98810ca9-7ba1-4ba3-bdec-71c06e0ab1e9.png)
	
</details>
	
<details>
  <summary>How Paths are timed MCP?</summary>
 

### How Paths are timed Multi-Path Cycle?
	
**How DC/STA tool checks timing?**
	
**Single cycle path**
	
![image](https://user-images.githubusercontent.com/118953917/210129180-1d16a1d7-6062-4f6a-a048-0c5910aa2d84.png)
	
**Half cycle path**
	
![image](https://user-images.githubusercontent.com/118953917/210129190-e88b82dc-4918-4be9-a5e8-071a250d808a.png)
	
**Multi cycle path**
	
![image](https://user-images.githubusercontent.com/118953917/210129203-cfb5b40c-d864-4328-99fa-c7fa30157661.png)
	
</details>
	
<details>
  <summary>Lab 3</summary>
 

### Lab 3: Boundary Optimization
	
```
sh gvim DC_WORKSHOP/verilog_files/check_boundary.v
```
	
![image](https://user-images.githubusercontent.com/118953917/210129207-36caf3a2-3403-47ea-a4d6-d315fd9c31c7.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
link
compile_ultra
write -f ddc -out boundary.ddc
get_cells
```
	
```
design_vision
read_ddc DC_WORKSHOP/verilog_files/boundary.ddc
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129215-8dac93db-be0e-42aa-968c-97f725fe388b.png)

> In design_vision
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
link
get_cells							(If command in dc_shell, the tool cannot find the matching objects because the boundary optimization has happened, that's why the hierarchy got dissoved)
set_boundary_optimization u_im false
compile_ultra
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129224-d3fc3603-2128-4a3e-a2cc-5c4569fe6da4.png)
	
</details>
	
<details>
  <summary>Lab 4</summary>
 

### Lab 4: Register Retiming

> In design_vision
```
reset_design
sh gvim DC_WORKSHOP/verilog_files/check_reg_retime.v
```
	
![image](https://user-images.githubusercontent.com/118953917/210129235-3bf86683-725f-4489-8f62-8c0f3bb22265.png)
	
```
read_verilog DC_WORKSHOP/verilog_files/check_reg_retime.v
link
compile
start_gui
```

![image](https://user-images.githubusercontent.com/118953917/210129248-c6cbeef4-dd0c-4b9c-982a-dbf72ffd6918.png)
	
```
report_timing
sh gvim DC_WORKSHOP/verilog_files/reg_retime_cons.tcl			(Setting the constraints)
source DC_WORKSHOP/verilog_files/reg_retime_cons.tcl
report_clocks
report_timing
compile_ultra -retime
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129252-5c47dbc5-919d-4f9c-82f7-d6e6a00f3071.png)
	
![image](https://user-images.githubusercontent.com/118953917/210129264-003c2885-7411-4205-806d-c2b48f2310dd.png)
	
```
report_timing
compile_ultra
report_timing -from [all_inputs]
report_timing -from [all_inputs] -trans -cap -nosplit -sig 4
```
	
![image](https://user-images.githubusercontent.com/118953917/210129279-a1702c7a-c93d-4161-9d6c-e31511294e55.png)
	
</details>
	
<details>
  <summary>Lab 5</summary>
 

### Lab 5: Isolating Output Ports
	
![image](https://user-images.githubusercontent.com/118953917/210129288-4ca80cf2-e625-473c-bc20-cc796da8c3b0.png)
	
```
sh gvim DC_WORKSHOP/verilog_files/check_boundary.v
```
	
![image](https://user-images.githubusercontent.com/118953917/210129293-21564a49-bcb3-4ca5-9af0-0de446102049.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
link
compile_ultra
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129298-f60dfe27-c494-43da-a705-33332670f6a8.png)
	
```
set_isolate_ports -type buffer [all_outputs]
compile_ultra
start_gui
```
	
![image](https://user-images.githubusercontent.com/118953917/210129305-8efa8dbf-2af4-42e1-a7ab-d447b9bbdfc8.png)
	
```
reset_design
read_verilog DC_WORKSHOP/verilog_files/check_boundary.v
link
compile_ultra
create_clock -per 5 -name myclk [get_ports clk]
set_input_delay -max 2 [all_inputs] -clock myclk
set_output_delay -max 2 [all_outputs] -clock myclk
set_load -max 0.3 [all_outputs]
report_timing -nosplit -inp -cap -trans -sig 4
report_timing -to val_out_reg[0]/D -inp -trans -nosplit -cap -sig 4		(Viewing report timing before isolating portr -> reg to reg path)
```
	
![image](https://user-images.githubusercontent.com/118953917/210129351-1f7bf903-61fd-462f-91ec-e2481d770d7b.png)
	
> Isolating ports of both paths
```
set_isolate_ports -type buffer [all_outputs]
compile_ultra
report_timing -nosplit -inp -cap -trans -sig 4
report_timing -from val_out_reg[0]/CLK -to val_out_reg[0]/D -nosplit -inp -cap -trans -sig 4
```
	
![image](https://user-images.githubusercontent.com/118953917/210129373-869bdbe0-4d4b-4d44-bfa6-914b07dc0e96.png)
	
</details>
	
<details>
  <summary>Lab 6</summary>
 

### Lab 6: Multi Cycle Path
	
```
sh gvim DC_WORKSHOP/verilog_files/mcp_check.v
```
	
![image](https://user-images.githubusercontent.com/118953917/210129392-455daaa8-f642-46d4-8202-aeb99d83b725.png)
	
```
read_verilog DC_WORKSHOP/verilog_files/mcp_check.v
link
compile_ultra
sh gvim DC_WORKSHOP/verilog_files/mcp_check_cons.tcl
source DC_WORKSHOP/verilog_files/mcp_check_cons.tcl
report_timing
compile_ultra
report_timing
set_multicycle_path -setup 2 -to prod_reg[*]/D -from [all_inputs] 	(Must put all_inputs -> valid to prod_reg is a single cycle path. If [all_inputs] didn't there, it will mcp the valid to prod_reg path too. This is a CRIMINAL MISTAKE!)
report_timing -to prod_reg[*]/D -from valid_reg/CLK
report_clock *
```

> Applying MCP
```
report_timing -to prod_reg[*]/D -from [all_inputs]
```

![image](https://user-images.githubusercontent.com/118953917/210129406-797ff33c-38c9-474f-ba42-c519c423e453.png)
	
![image](https://user-images.githubusercontent.com/118953917/210129420-225d1ba6-4c80-430f-9e7f-f9c7a04fd62b.png)
	
> Hold time
```
report_timing -delay min
```
	
> Applying MCP for hold time
```
set_multicycle_path -hold 1 -from [all_inputs] -to prod_reg[*]/D
report_timing -delay min -to prod_reg[*]/D -from [all_inputs]
```
	
> Isolating ports in report timing
```
report_timing -nosplit -inp -cap -trans -sig 4
```

![image](https://user-images.githubusercontent.com/118953917/210129437-59b0d647-2391-4ba3-9928-5a834b26e3fc.png)
	
</details>

## Day-10

### Topic: Quality Checks - Quality of Results (QOR)

<details>
  <summary>Report timing</summary>
 

### Lecture Report timing

**Generating timing reports**
```
report_timing -from DDF_A/clk
report_timing -from DDF_A/clk -to DDF_A/d
report_timing -fall_from DDF_A/clk
report_timing -rise_from DDF_b/clk
report_timing -delay_type min -to DDF_C/d
report_timing -delay_type min -through INV/a
report_timing -delay_type max -through AND/b
report_timing -rise_from DDF_b/clk -delay_type max -nets -cap -trans -sig 4             (delay_type max -> default if the delay type was not specified)
```
  
**Quick look at propagation delay**
  
![image](https://user-images.githubusercontent.com/118953917/210180887-59412998-fb3b-490c-b549-62d996c229d4.png)
  
**Timing path: Further details**
  
![image](https://user-images.githubusercontent.com/118953917/210180898-b0bbe5ce-d730-4b8e-a965-157ba0943587.png)

![image](https://user-images.githubusercontent.com/118953917/210180920-0559790f-4448-430b-b6cc-31954668c8bb.png)
  
**Max path and Nworst**
  
![image](https://user-images.githubusercontent.com/118953917/210180931-0821ae7a-ad8d-493b-b7fc-331908e270da.png)
</details>
  
<details>
  <summary>Lab 1</summary>
 

### Lab 1: Report timing
  
```
sh gvim DC_WORKSHOP/verilog_files/lab8_circuit_modified.v
:vsp DC_WORKSHOP/verilog_files/lab8_cons_modified.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/210180948-ec646819-27fc-46ca-b85f-b26c00d359ee.png)

> Setup check
```
read_verilog DC_WORKSHOP/verilog_files/lab8_circuit_modified.v
link
source DC_WORKSHOP/verilog_files/lab8_cons_modified.tcl
report_timing -sig 4 -nosplit -trans -cap -input_pins -from IN_A > DC_WORKSHOP/verilog_files/t1.rpt
sh gvim DC_WORKSHOP/verilog_files/t1.rpt
```
  
![image](https://user-images.githubusercontent.com/118953917/210180954-dbcf8f10-85e0-44d7-a5ac-ee346fcdc80e.png)

> To check for the worst delay
```
report_timing -rise_from IN_A -sig 4 -transition_time -capacitance -input_pins > DC_WORKSHOP/verilog_files/t2.rpt
sh gvim DC_WORKSHOP/verilog_files/t2.rpt
:vsp DC_WORKSHOP/verilog_files/t1.rpt   
```
  
![image](https://user-images.githubusercontent.com/118953917/210180960-fd1bebc3-7d18-45a4-bd16-02c09da712e9.png)
  
```
report_timing -rise_from IN_A -sig 4 -transition_time -capacitance -input_pins -to REGA_reg/D > DC_WORKSHOP/verilog_files/t3.rpt
sh gvim DC_WORKSHOP/verilog_files/t3.rpt
:vsp DC_WORKSHOP/verilog_files/t1.rpt  
```
  
![image](https://user-images.githubusercontent.com/118953917/210180965-03bd4553-ac03-4d80-ac76-cd5f8f0d9d1b.png)
  
> Hold check
```
report_timing -delay min -from  IN_A
```
  
![image](https://user-images.githubusercontent.com/118953917/210180973-6788f71b-80af-43eb-897c-a3d013ac8a59.png)
  
> Report timing through U15/Y
```
report_timing -through U15/Y
report_timing -delay min -through U15/Y
```
  
![image](https://user-images.githubusercontent.com/118953917/210180986-1940ea45-413b-4825-a663-4144f291ed58.png)
  
</details>
  
<details>
  <summary>Lab 2</summary>
 

### Lab 2: Lab Check_timing, Check_design, Set_max_capacitance, HFN
  
```
read_verilog DC_WORKSHOP/verilog_files/lab8_circuit_modified.v
link
check_design
compile_ultra
check_timing                (Checking the design is properly constrained or not)
report_constraints          (Default constraints loaded in the tool memory)
source DC_WORKSHOP/verilog_files/lab8_cons_modified.tcl
check_timing
report_timing
```
  
![image](https://user-images.githubusercontent.com/118953917/210180998-26b50d00-6da9-4587-8495-576fd5a4e85d.png)
  
```
report_constraints
```
  
![image](https://user-images.githubusercontent.com/118953917/210181012-0e482d68-6c20-4cfa-9aeb-8c2bc680a649.png)
  
```
reset_design
sh gvim DC_WORKSHOP/verilog_files/mux_generate.v
:vsp DC_WORKSHOP/verilog_files/mux_generate_128_1.v  
```
  
![image](https://user-images.githubusercontent.com/118953917/210181027-5c7dc379-7e44-4094-b7a7-4fe7ec7b231e.png)
  
```
sh gvim DC_WORKSHOP/verilog_files/mux_generate.v 
:vsp DC_WORKSHOP/verilog_files/mux_generate_128_1.v
read_verilog DC_WORKSHOP/verilog_files/mux_generate_128_1.v 
link
compile_ultra
write -f verilog -out DC_WORKSHOP/verilog_files/mux_generate_128_1_net.v
sh gvim DC_WORKSHOP/verilog_files/mux_generate_128_1_net.v
```

![image](https://user-images.githubusercontent.com/118953917/210181039-b981304d-e119-4610-b567-e1905ed39c88.png)
  
```
get_cells * -hier -filter "is_sequential == true"           (No output since there is no sequential cells)
get_cells * -hier -filter "is_sequential == false"
report_timing -net -cap -sig 4
check_timing
```
 
> Setting the constraints
```
set_max_delay -from [all_inputs] -to [all_outputs] 3.5
report_timing
```
  
![image](https://user-images.githubusercontent.com/118953917/210181047-56a6044a-b398-4679-a326-c54a48945a59.png)
  
> Setting max capacitance
```
set_max_capacitance 0.025 [current_design]
report_constraint -all_violators
compile_ultra
check_timing 
report_constraints
report_timing
report_timing -net -cap -sig 4
```
  
![image](https://user-images.githubusercontent.com/118953917/210181057-4063c805-44b6-46f0-adcd-94246d161e37.png)
  
> New design
```
sh gvim DC_WORKSHOP/verilog_files/en_128.v
reset_design 
read_verilog DC_WORKSHOP/verilog_files/en_128.v
link
compile_ultra
report_timing -from en -inp -nets -cap
set_max_capacitance 0.03 [current_design]                       (Breaking/buffering HFN)
report_constraints
compile_ultra 
report_timing -from en -inp -nets -cap -sig 4
write -f ddc -out  DC_WORKSHOP/verilog_files/en_128.ddc
```
  
![image](https://user-images.githubusercontent.com/118953917/210181089-08fab177-2e64-47cc-b9dd-5b0570634894.png)
  
> Invoking design vision
```
design_vision
read_ddc DC_WORKSHOP/verilog_files/en_128.ddc
start_gui
```
  
![image](https://user-images.githubusercontent.com/118953917/210181102-35c48b12-2ca4-4f07-a0a7-d0284a9f5356.png)
  
> Setting the max transition 
```
report_timing -from en -nets -cap -sig 4 -trans
set_max_transition 0.150 [current_design]
report_constraints
report_constraint -all_violators
```
  
![image](https://user-images.githubusercontent.com/118953917/210181113-dd759149-57d8-4a77-939b-fbaa83c7bdc1.png)
  
```
compile_ultra
report_constraint -all_violators
report_timing -inp -nets -cap -trans -sig 4 -nosplit
report_timing -inp -nets -cap -trans -sig 4 -nosplit -from en -to y[116]
```
  
![image](https://user-images.githubusercontent.com/118953917/210181117-66f60290-dc2f-4cc0-a0df-509477d1d701.png)
  
**Summary**

* check_design 
  + To ensure the quality of the design is proper, to check if the design is proper/not, or if there are any missing things in the design.
* check_timing 
  + To ensure all the proper constraints are in place.
* report_constraints 
  + To check what are the constraints we are checking. If there is any violation, it will report it.
* set_max_capacitance & set_max_transition 
  + To check if there is any high fanout net (HFN) or broken or is the design is buffered properly, so that there are no transition issues.
  
**Summarizing**
  
**Important things should be there in synthesis script -> synth.tcl**

* Constraints
  + clock, genclk (if any)
  + vclk (if any)
  + Practicalities of the clock -> uncertainty including skew + jitter for pre CTS latency and jitter only for post CTS & latency
  + Input delay
  + Output delay
  + Input trans/set_driving _cell
  + Output load
  + set_max_area
  + set_max_capacitance
  + set_max_transition

* Synthesis Knobs
  + Boundary Optimization
  + Retiming 
  + Constant propagation 
  + Unused flop removal 
  + Isolate ports 

  
Note: All of those things must be needed in synthesis or script.tcl

  
**After sourcing all those contents, the program needs to:**

* read_verilog
* read_db
* check_design
* source constraints
* check_timing
* compile_ultra
* report_constraint (for all_violations)
* report_area
</details>
  
<details>
  <summary>Timing Model</summary>
 

### Timing Model: ETM and QTM
  
**QTM and ETM in VLSI**
  
**Introduction**
In design, once a block has met its timing constraints at gate level, the detailed internal timing of the block is not needed for chip-level timing analysis. For that, we can create/write a timing model for the block.
  
*Source: http://www.vlsi-expert.com/2011/02/etm-extracted-timing-models-basics.html#:~:text=Extracted%20Timing%20Models%20(ETM)%20in,QTM)%20for%20top%2Ddown%20design 
  
**What is timing models?**
  
* It is used to perform STA on a chip using Primetime since every leaf cell must have a timing model.
* For STA purposes, a leaf cell can be a simple macro cell i.e. NAND, NOR, or flip flop, or a complex block i.e. RAM/microprocessor.
* Hierarchical STA flow allows us to partition different blocks using timing models which should completely model the full input/output timing characteristics without requiring a complete netlist of the block and not modelling every path in the block.
* Hierarchical STA reduces runtime and memory usage as compared to flat STA. The actual runtime savings depending on the design complexity.
  
  
**Types of timing models**
* Extracted Timing Model (ETM)
* Quick Timing Model (QTM)
  
*Source: http://mantravlsi.blogspot.com/2014/06/timing-models-etm-qtm-ilm.html 

  
**Extracted Timing Model (ETM)**

* Block-based model (.lib)
* Contents of the block are hidden
* Original netlist is replaced by model containing timing arcs for the block interfaces
* NLDM lookup tables are extracted for each timing arcs
* These arcs whose delay a function of input transition and output load. This makes ETM usable with different input transition times and different output loads.
* Multiple modes per model
* Single PVT per model
* Used for implementation (not sign-off) of IP models. The contents are protected since the model contains abstracted timing information, without any netlist information
  
**ETM model illustration**

*Source: http://www.vlsi-expert.com/2011/02/etm-extracted-timing-models-basics.html#:~:text=Extracted%20Timing%20Models%20(ETM)%20in,QTM)%20for%20top%2Ddown%20design 
  
![image](https://user-images.githubusercontent.com/118953917/210180743-50a8facd-28c1-4bdf-ab26-7122d454c532.png)

**Quick Timing Model (QTM)**
In the early stages of the design cycle, if a block does not have a netlist yet, we can use a QTM to decsribe its initial timing. Later in the cycle, we can replace each QTM with a netlist block to obtain more accurate timing.
  
*Source: http://mantravlsi.blogspot.com/2014/06/timing-models-etm-qtm-ilm.html 
  
* QTM is generated by the command create_qtm_model, followed by save_qtm_model
  
*Source: http://tech.tdzire.com/what-are-etms-qtms-and-ilms/
</details>

## Day-11

### Topic: Introduction to the BabySoC

<details>
  <summary>SoC</summary>
 

### Introduction to BabySoC

**What is System on Chip (SoC)?**

* SoC is a single-die chip that has some different IP cores on it. These IPs could vary from microprocessors which are completely digital to 5G Broadband modems which are completely analog. 
* The structural design of SoC usually includes a central processing unit, memory, ports for inputs and outputs, secondary storage devices, and peripheral interfaces i.e. timers and etc.

**Why SoC is used?**

* Depending upon the requirement, it can also consists of a digital/analog signal processing system or a floating-point unit.
* SoC with equivalent functionality will have increased performance and reduced power consumption as well as a smaller semiconductor die area.

**Typical structure of MediaTek Dimensity 9000 Processor**

* This processor is made using TSMC’s 4nm semiconductor chip fabrication process, and it is said to be more power-efficient compared to Samsung’s 4nm process which is used to make the Exynos 2200 and the Qualcomm Snapdragon 8 Gen 1. 
* The precessor has a 1+3+4 CPU core configuration with one ARM Cortex-X2 CPU core clocked at 3.05GHz, three ARM Cortex-A710 CPU cores clocked at 2.85GHz, and four ARM Cortex-A510 CPU cores clocked at 1.8GHz.

*Source: https://onsitego.com/blog/mediatek-dimensity-9000-smartphones-list/#:~:text=The%20MediaTek%20Dimensity%209000%20processor%20is%20made%20using%20TSMC's%204nm,3%2B4%20CPU%20core%20configuration.*

![image](https://user-images.githubusercontent.com/118953917/210308234-d3128bbf-0ed6-4ceb-b4e4-895c0737b607.png)

**Types of SoC**

* SoCs built around a microcontroller (board).
* SoCs built around a microprocessor (chip), where it is often found in cell phones.
* Specialized application-specific integrated circuit SoCs designed for specific applications that do not fit into the above two categories.

**SoC Structure**

* SoC consists of hardware functional units, including microprocessors that run software code, as well as communication subsystems to connect, control, direct and interface between these functional modules. 
* **Functional components**: processor cores, memory, interfaces, digital signal processor (DSP), others.
* Intermodule communication**: bus-based communication, network on a chip.

**SoC design flow**

![image](https://user-images.githubusercontent.com/118953917/210308326-272eefdc-d3bd-4238-8e1e-d7bb9acadefc.png)

</details>

<details>
  <summary>BabySoc</summary>
 

### Introduction to BabySoc

* BabySoc is a small yet powerful RISCV-based SoC. 
* The main purpose of designing such a small SoC is to test three open-source IP cores together for the first time and calibrate the analog part of it. 
* BabySoC contains one RVMYTH microprocessor, an 8x-PLL to generate a stable clock, and a 10-bit DAC to communicate with other analog devices.

*Source: https://github.com/manili/VSDBabySoC#introduction-to-the-vsdbabysoc*

![image](https://user-images.githubusercontent.com/118953917/210308374-b36bf404-f021-4415-a0fc-2ac8b37852f7.png)

* SoC is an IC that integrates multiple components of a system onto a single chip.
* MPSoC addresses performance requirements. 

*Source: https://www.ecb.torontomu.ca/~courses/coe838/lectures/Intro-SoC.pdf*

![image](https://user-images.githubusercontent.com/118953917/210308411-01184a7b-44da-48d3-95c9-40e4ca249e67.png)

**Baby SoC components**

* RVMYTH: RVMYTH core is a simple RISCV-based CPU, introduced in a workshop by RedwoodEDA and VSD.
* Phase-locked loop (PLL): a control system that generates an output signal whose phase is related to the phase of an input signal. PLLs are widely used for synchronization purposes, including clock generation and distribution.
* Digital-to-analog converter (DAC): a system that converts a digital signal into an analog signal. DACs are widely used in modern communication systems enabling the generation of digitally-defined transmission signals.

*Source: https://github.com/manili/VSDBabySoC#problem-statement*

**Phase-locked loop (PLL)**

* PLL is a closed loop feedback circuit comprises of four main blocks.
* PLL mainly consists of four components: 
  + Charge pump (CP)
  + Phase Frequency Detector (PFD)
  + Voltage Controlled Oscillator (VCO)
  + Loop Filter
  + Frequency Divider (FD)
* These blocks are connected to form a closed loop feedback network so as to synchronize the output with the input in both phase and frequency. 
* This loop continues to run until PLL locked condition is achieved.
* As technology scales down, PLL with wide tuning range, low jitter, and PLL operating at high frequencies are preferred.

*Source: https://github.com/bharath19-gs/avsdpll28nm/#PLL-introduction*

![image](https://user-images.githubusercontent.com/118953917/210308453-089b2d25-3e34-4570-b945-cc8794c3c25c.png)

**Digital-to-analog converter (DAC)**

* DAC converts a digital input signal into an analog output signal. 
* The digital signal is represented with a binary code, which is a combination of bits 0 and 1. DAC consists of a number of binary inputs and a single output. 
* There are two types of DACs:
  + Weighted Resistor DAC
  + R-2R Ladder DAC
  
*Source: https://github.com/Devipriya1921/avsddac28nm#introduction*

</details>

<details>
  <summary>BabySoC Modeling</summary>
 

### Introduction to Modelling

* BabySoC modelling is simulated using ```iverilog``` as well as ```gtkwave``` tool  to display the result.
* Some initial input signals will be fed into BabySoC module making the PLL to start generating the proper ```CLK``` for the circuit.
* The clock signal will make the ```rvmyth``` to execute instructions in its ```imem```. As a result, the register ```r17``` will be filled with some values cycle-by-cycle.
* These values are used by DAC core to provide the final output signal named ```OUT```.
* So, we got 3 main elements (IP cores) and a wrapper as an SoC and of-course there would be also a testbench module out there.

*Source: https://github.com/manili/VSDBabySoC#introduction-to-the-vsdbabysoc*

</details>

<details>
  <summary>Microchips fabrication</summary>
 

### How Microchips are made?
  
**Introduction to microchips fabrication**
  
* All chips started out with a very simple raw material which is sand.
* Complex chemical and physical processes are required to create out of the sand an pure monocrystalline silicon ingot.
* The process to manufacture chips from a wafer starts with the layout and design phase where extremely thin wafers are being cut using a special sawing technique.
* They are fabricated in a range of different diameters, the most common sizes are 150, 200 and 300 mm.
* Wafers with large diameters offer more space for chips. 
* Transistors are the smallest control units in microchips. It used to control electric voltages and currents and it is the most important components of electronic circuits.
  
*Source: https://www.infineon.com/cms/en/product/promopages/how-a-chip-is-made-video/*

**Fabrication of wafers from transistors**
  
1. Highly complex chips are made up of billions of integrated and connected transistors, enabling sophisticated circuits i.e. microcontrollers and crypto chips.
2. Firstly, the surface of the wafer is oxidized in a high-temperature furnace operating at approximately 1000°C to create a non-conductive layer.
3. Then, a photo resist material is uniformly distributed on this non-conductive layer.
4. The wafer is then exposed to light through the photomask in special exposure machines known as steppers.
5. The exposed layer of oxide is then etched off in the areas that have been developed using wet or plasma etching.
6. The photoresist is being applied again, the wafer is exposed to light through the mask, and the exposed photoresist is stripped again. 
  
**Doping process**
  
1. Impurity atoms are introduced into the exposed silicon and ion implanter is used to shoot the impurity atoms into the silicon. This changes the conductivity of the exposed silicon by fractions of a micrometer.
2. After the photoresist residue has been stripped, another oxide layer is applied. 
3. The wafer undergoes another cycle of applying photoresist, exposure through the mask and stripping.
4. Contact holes are etched to provide access to the conductive layers, enabling the contacts and interconnections to be integrated in the wafer. 
5. Photoresist and mask are applied once again. 
6. Chemical-mechanical process is used to polish away excess material in order to give the insulation layer above the interconnections the smooth finish.
7. The steps may be repeated multiple times until the IC is completed.
  
**Assembly process (Final stage of the fabrication)**
  
1. The individual chips are placed in a package and terminals are attached.
2. The result is a finished semiconductor device, which can be mounted on circuit boards using different types of terminals. 
3. Over a thousand connection contacts can be realized. 
  * The high levels of precision and quality are essential at every stage of the workflow which is from the production of silicon boules - cleanroom fabrication - quality control.
  
*Source: https://www.infineon.com/cms/en/product/promopages/how-a-chip-is-made-video/*
  
**Overall fabrication process illustration**
  
*Source: https://link.springer.com/article/10.1557/s43577-020-00001-3*
  
![image](https://user-images.githubusercontent.com/118953917/210314860-b1ad8f93-f8ad-43ab-8298-2f5a27d878cf.png)

 </details>

## Day-12

### Topic: BabySoC Modelling

<details>
  <summary>Theory</summary>
 
### Lab: Theory

**What is modelling?**

* Modelling and simulation (M&S) is the use of a physical/logical representation of a given system to generate data and help determine decisions/make predictions about the system.
* M&S is widely used in the VLSI domain.

**Purpose of modelling**

System models are specifically developed to support analysis, specification, design, verification and validation of a system, as well as to communicate certain information.

**What are we modelling? (VSDBabySoC)**

* Some initial input signals will be fed into vsdbabysoc module
* PLL will start generating the proper CLK for the circuit
* Clock signal will make the rvmyth to execute instructions and some values are generated, these values are used by DAC core to provide the final output signal named OUT
* There are 3 main elements (IP cores) and a wrapper as SoC and also a testbench module

**RVMYTH - Risc-V based MYTH**

* RISC: Reduced instruction set computer
* RISC-V (“risk-five”): a base integer ISA, which must be presented in any implementation, plus optional extensions to the base ISA
* Each base integer instruction set is characterized by the width of the integer registers and the corresponding size of the address space and by the number of integer registers. There are two primary base integer variants, RV32I and RV64I

**Waterfall flow diagram for a pipelined Risc-v processor**

*Source: https://www.vlsisystemdesign.com/risc-v-waterfall-diagram-and-hazards/*

![image](https://user-images.githubusercontent.com/118953917/210520422-1b72c586-3ba4-4fbd-bca4-3fa881778c78.png)

**Phase Locked Loop (PLL)**

* Electronic circuit with a voltage or voltage-driven oscillator that constantlyadjusts to match the frequency of an input signal
* Purposes: to generate, stabilize, modulate, demodulate etc

**Why off-chip clocks can’t be used all the time?**

* Clock will be a supply for a lot of blocks on the chip, it will have delays due to long wires (if used only one clock source) - i.e. clock jitter
* Some blocks might need 200 MHz and some might need 100 MHz -> different frequencies just on one small chip
* Concept of ppm (clock accuracy) comes in, whenever quartz is acquired, it comes with x ppm error

**PLL used on SoC**

Main components:
* Phase detector
* Loop filter
* Voltage controlled oscillator
* Frequency divider 

*Source: https://onedrive.live.com/?authkey=%21AOwVpzXkVogukuk&cid=E0E9B5EEF85B162E&id=E0E9B5EEF85B162E%2199346&parId=E0E9B5EEF85B162E%2197363&o=OneUp*

![image](https://user-images.githubusercontent.com/118953917/210522255-2b1931b5-f254-47b7-b980-2388358680ec.png)

**Digital-to-Analog Converter (DAC)**

* Converts a digital input signal into an analog output signal
* Digital signal is represented with a binary code, which is a combination of bits 0 and 1. DAC consists of a number of binary inputs and a single output
* 2 types of DAC
  + Weighted Resistor DAC
  + R-2R Ladder DAC
  
**Tips on modelling the design**

* Avoid race Conditions -> can use VCS race detection tool
* Use an optimized Testbench for debugging the design
* Creating models that simulate faster
* Follows case statement behaviour

**DVE (Normal mode)**

* DVE provides a graphical user interface (GUI) to debug the design
* Steps to open GUI with normal mode:
  + Run the design with a valid testbench
  + Compile them
  + Cross check .vcd file 
  + Invoking DVE tool
  
**DVE (Interactive mode)**

* Debugging the design in interactive mode or in post-processing mode with a valid testbench
* Steps to open GUI with interactive mode:
  + Run the design with a valid testbench
  + Get the code dump file (.vcd)
  + This should open the tool automatically and we can fully run our test bench or debug it step by step

**RVMYTH modelling**

* RISC-V CPU core has been written in Verilog and already written testbench code for the same
* Entire C program will be converted into a hex format and will be loaded into memory
* CPU will then read the contents of the memory, process it and display the output result of sum numbers from 1 to n


</details>

<details>
  <summary>Lab</summary>
 

### Lab: Modelling

> RVMYTH (RISC-V) modelling
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc
git clone https://github.com/kunalg123/rvmyth/
cd rvmyth
/p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./
csh
vcs mythcore_test.v tb_mythcore_test.v                                                    (Got 1 error -> need to refer both files and fix that)
```
  
**Error compiling**

![image](https://user-images.githubusercontent.com/118953917/210686222-acdb0f86-e0d9-4352-9bc5-f6c1ae18a32e.png)
  
**Error debugging**
  
![image](https://user-images.githubusercontent.com/118953917/210686260-b0f35375-e60e-4764-9569-e95783155564.png)

```
./simv
dve &                         (Error -> should state how many bits to display in the command)
dve -full64                   (Error fixed)
```

**Error debugging and output waveform**
  
![image](https://user-images.githubusercontent.com/118953917/210829380-5709b5fb-bfbc-45c1-815f-a132491061da.png)

> DAC modelling
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/dac
git clone https://github.com/vsdip/rvmyth_avsddac_interface.git
csh
cp -r rvmyth_avsddac_interface /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/rvmyth_avsddac_interface/iverilog/Pre-synthesis
vcs avsddac.v avsddac_tb_test.v
```

**Error** 
  
![image](https://user-images.githubusercontent.com/118953917/210829629-061ef761-6b84-4546-b762-b450005d89f1.png)
  
```
vcs -sverilog avsddac.v avsddac_tb_test.v           (To notice the system to support system verilog)
./simv
dve -full64  
```
  
**Error fixing**
  
![image](https://user-images.githubusercontent.com/118953917/210829699-97193411-e76c-4a35-93ec-146c18c27dab.png)
  
**Output waveform**
  
![image](https://user-images.githubusercontent.com/118953917/210833554-cd023f66-a179-4853-9cff-23c444ccdea3.png)
  
> PLL modelling 
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/rvmyth_avsdpll_interface/verilog
csh
vcs avsd_pll_1v8.v pll_tb.v
./simv
dve -full64 
```
  
**Scripting**
  
![image](https://user-images.githubusercontent.com/118953917/210829788-20be3b5d-6607-4669-a8a3-70e865becf26.png)
  
**Output waveform**

![image](https://user-images.githubusercontent.com/118953917/210829879-f03f9769-21ae-43b9-a307-22ed03ca1cd7.png)
  
> Simulating in interactive mode (debug mode)
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/rvmyth
csh
vcs -lca -debug_access+all -full64 mythcore_test.v tb_mythcore_test.v
./simv -gui &
```
  
**Debuging line-by-line coding**
  
![image](https://user-images.githubusercontent.com/118953917/210829938-b59a4a6b-025a-4def-a5bc-f9c8cac94da4.png)
  
**Output waveform**
  
![image](https://user-images.githubusercontent.com/118953917/210829980-683feb81-ba33-4f16-9c46-0448d6b6c0e1.png)
  
>> Interfacing blocks together
  
> risc_v and pll 
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc
git clone https://github.com/vsdip/rvmyth_avsdpll_interface
cp -r rvmyth_avsdpll_interface /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/rvmyth_avsdpll_interface/verilog
csh
vcs rvmyth_pll.v rvmyth_pll_tb.v
```
  
**Fixing errors**
  
![image](https://user-images.githubusercontent.com/118953917/210830075-142ceaae-d603-43e2-b27f-d6210a2e2280.png)
  
```
./simv
dve -full64 
```
  
**Output waveform**
  
![image](https://user-images.githubusercontent.com/118953917/210830186-d91efcb5-769a-4c19-9880-fe5cbf311dbe.png)
  
> DAC and RVMYTH
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/rvmyth_avsdpll_interface/verilog
csh
vcs rvmyth_avsddac.v rvmyth_avsddac_TB.v
```

**Error compiling**
  
![image](https://user-images.githubusercontent.com/118953917/210830252-352144b5-3113-472b-8f7d-576dcbb6a9b2.png)
  
**Error fixing**
  
![image](https://user-images.githubusercontent.com/118953917/210830312-41b01106-2b8e-457d-85a0-c2f087d29c34.png)
  
```
vcs -sverilog rvmyth_avsddac2.v rvmyth_avsddac_TB2.v
./simv
dve -full64 
```

**Output waveform**
  
![image](https://user-images.githubusercontent.com/118953917/210830355-0a3cec67-4fde-4b67-b127-6bf3f420c1a6.png)
	
> Simulating and modelling all 3 IP’s (VSDBabySoC)
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/
git clone https://github.com/manili/VSDBabySoCcd 
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/VSDBabySoC/src/module
csh
vcs -sverilog vsdbabysoc.v testbench.v
./simv 
dve -full64 
```
	
**Error compiling**
	
![image](https://user-images.githubusercontent.com/118953917/210921496-35b88f16-4ba4-4f63-9db9-dd690f781d61.png)

**Error fixing**
	
![image](https://user-images.githubusercontent.com/118953917/210921774-76e02aed-7aac-44f3-97b8-4b43ad26b317.png)

**Output waveform**
	
![image](https://user-images.githubusercontent.com/118953917/210921842-71f590f0-0b36-41b2-aed5-5d745cdf81dd.png)
  
</details>

<details>
  <summary>Task</summary>
 

### Lab: Task to do
  
**Differences of the modes in interactive mode**
  
![image](https://user-images.githubusercontent.com/118953917/210830922-aa9a5a54-68e8-43d2-8e8e-d41836431916.png)
  
> Design chosen: up counter
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/babysoc/
csh 
vcs upcntr.v tb_upcntr.v
./simv
dve -full64 
```
  
**Fixing error**
  
![image](https://user-images.githubusercontent.com/118953917/210831067-ad8d9cd5-15de-432b-bcb8-08574be2f5ba.png)
  
**Block diagram of upcounter**
	
*Source: https://www.electronics-tutorials.ws/counter/count_3.html*
  
![image](https://user-images.githubusercontent.com/118953917/210831238-90c5c31c-35fd-4f46-bdb8-5c2ebfbaae03.png)
  
**Output waveform of upcounter**

![image](https://user-images.githubusercontent.com/118953917/210831372-6e9e77e3-d9fe-4470-b080-3ed5f5159c26.png)

</details>

## Day-13

### Topic: Post-synthesis simulation

<details>
  <summary>Theory</summary>
 
### Theory

**Things to do in pre-synthesis**

Modelling and simulating IP cores in VSDBabySoC (for checking its functionality) 
  
**Refreshing on synthesizable and non-synthesizable constructs in verilog**
  
![image](https://user-images.githubusercontent.com/118953917/210950834-5d98bf62-278a-4bb3-a5c3-4d84781364d0.png)
  
**Why do pre-synthesis? Why cannot just do post-synthesis?**
  
* Pre-synthesis simulation is done according to the logic that we have designed for and written -> only functionality
* Post synthesis simulation/GLS (gate level simulation) is done after synthesis considering each gate delays into account, also reports the violations in both functionality and timing
* This will show the mismatches that are likely to get due to the wrong usage of operators and inference of latches
* i.e. using ‘X’ (simulator/synthesizer terms) as ‘Unknown’/‘Don’t care’
  
**Gate Level Simulation (GLS)**
  
* 'gate level' refers to netlist view of a circuit, usually produced by logic synthesis
* RTL simulation is pre-synthesis while GLS is post-synthesis
* Netlist view is a complete connection list consisting of gates and IP models with full functional and timing behavior
* RTL simulation is zero delay environment and events, generally occurs on the active clock edge. Whereas GLS can be zero delay too, but it is more often used in unit delay or full timing mode
  
*Note: Gate level simulation is used to boost the confidence regarding implementation of a design and can help verify dynamic circuit behaviour, which cannot be verified accurately by static methods. It is a significant step in the verification process.*
  
**Tools used to synthesize the netlist**
  
* Using synopsys’s DC shell (Design Compiler)
* DC RTL synthesis solution enables users to meet today's design challenges with concurrent optimization of timing, area, power and test
  
**Why post-synthesis simulation is needed?**
  
* To ensure each and every gate delays are taken into account
* Pre-synthesis in VCS and DVE that has done from the previous labs would be compared 
* To observe the output generated
* Note that post-simulation output should be matched with pre-simulation output

</details>

<details>
  <summary>Lab: Convert .lib to .db using lc_shell</summary>
 
### Converting .lib file to .db file

>> Picking one file 
  
**avsddac.lib**

> Change directory to the desired path
```
cd /nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training
```

> Entering cheetah environment and invoking lc_shell
```
set block = ddrphy
setenv block ddrphy
#source /nfs/site/disks/zsc11_mip_xmphy_0002/proj_root_ulc/setup/setup_pv.csh $block
/p/hdk/bin/cth_psetup -proj ip/2209sp3 -cfg IP78P3H180O12_22WW47 -cfg_ov /nfs/site/disks/ipg_da_00001/da/cth_overrides/sde_2209sp3_converged.cth -ward $PWD -verbose -x '$SETUP_R2G -force'
  
lc_shell
```

> Read and write .lib files
```
cd /nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/sky130RTLDesignAndSynthesisWorkshop/lib
read_lib avsddac_ori.lib                                                                                  (Error reading .lib file -> need to do modification)
```

**avsddac.lib error debugging**
  
![image](https://user-images.githubusercontent.com/118953917/211332488-46a6a719-600d-46bb-b5a8-9d38105b4c57.png)

```
cd /nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/sky130RTLDesignAndSynthesisWorkshop/lib    (Modify the .lib file)
read_lib avsddac.lib        
write_lib avsddac -format db -output avsddac.db
exit                                                                                                                (Exit lc_shell)     
tkdiff avsddac_ori.lib avsddac.lib                                                                                  (Looking the differences for before and after modification) 
```
  
**Modification of avsddac.lib**
  
![image](https://user-images.githubusercontent.com/118953917/211332631-8b55d664-693d-469f-bec2-dd93b687507e.png)
  
> Moving converted .db file from cheetah environment (santa clara zsc11) to png site 
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files                 (Penang site)
rsync -rv rsync.zsc11.intel.com:/nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/sky130RTLDesignAndSynthesisWorkshop/lib/avsddac.db .    ("." stands for current directory)
```

**avsdpll.lib**
  
```
/nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/VSDBabySoC/src/lib
lc_shell
read_lib avsdpll.lib          
```
  
**avsdpll.lib error debugging**
  
![image](https://user-images.githubusercontent.com/118953917/211332719-f4e6fa28-f94e-4307-812d-e1daae9472c9.png)
  
**Modification of avsdpll.lib**
  
![image](https://user-images.githubusercontent.com/118953917/211332887-2b569f6f-b19a-4c8a-900f-e1e593be1ce7.png)
  
```
read_lib avsdpll.lib 
write_lib avsdpll -format db -output avsdpll.db
exit    
tkdiff avsdpll_ori.lib avsdpll.lib 
```
  
> Move the converted .db files to the training path (png site)
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files                 (Penang site)
rsync -rv rsync.zsc11.intel.com:/nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/VSDBabySoC/src/lib/avsdpll.db .  
```
</details>

<details>
  <summary>Lab: Synthesis</summary>
 
### Synthesizing the code
  
**using avsddac.db**
  
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/sky130RTLDesignAndSynthesisWorkshop
/p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./
csh
dc_shell
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/dac/rvmyth_avsddac_interface/iverilog/Pre-synthesis

sh gvim .synopsys_dc.setup
set target_library {/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db}
set link_library {* nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db}
```
  
**rvmyth_avsddac.v**
  
```
read_verilog rvmyth_avsddac.v
```

**rvmyth_avsddac.v Error debugging**
  
![image](https://user-images.githubusercontent.com/118953917/211706699-6cf5e5b5-fdf0-4afc-96c1-46c63a2bfeba.png)
  
**Modification of rvmyth_avsddac.v**
  
![image](https://user-images.githubusercontent.com/118953917/211706748-ff43e106-22da-4235-9131-28da491d21c1.png)
  
```
echo $target_library
echo $link_library
read_file {mod_rvmyth_avsddac.v mod_avsddac.v mod_mythcore_test.v clk_gate.v} -autoread -format verilog -top rvmyth_avsddac 
compile
write -f verilog -out mod_rvmyth_avsddac_net.v
```

![image](https://user-images.githubusercontent.com/118953917/211706800-c6baa5f9-1108-4c87-a4df-759d4f9f6704.png)
  
**Netlist of rvmyth_avsddac**
  
![image](https://user-images.githubusercontent.com/118953917/211706853-85f2f560-8021-4f5e-94f8-0d337bc430a9.png)
  

> Checking the design 
```
current_design
check_design
check_timing
report_constraint
report_timing
```
  
![image](https://user-images.githubusercontent.com/118953917/211706893-82f070cd-87ad-4179-9672-f925523f76df.png)
  

**using avsdpll.db**
  
```
sh gvim .synopsys_dc.setup
set target_library {/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db}
set link_library {* nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db}
```

**avsd_pll_lv8.v**
  
```
echo $target_library
echo $link_library
read_verilog rvmyth_avsdpll.v
``` 

**avsd_pll_lv8.v Error debugging**

![image](https://user-images.githubusercontent.com/118953917/211706945-3c9a2fc7-8879-4996-b2d6-c9dff6286477.png)
  
**Modification of avsd_pll_lv8.v**
  
![image](https://user-images.githubusercontent.com/118953917/211707005-4cf034bd-75da-414e-8b76-446435867f5b.png)
  
```
echo $target_library
echo $link_library
read_file {mod_avsd_pll_1v8.v mod_mythcore_test.v clk_gate.v mod_rvmyth_pll.v } -autoread -format verilog -top rvmyth_pll_interface
compile
write -f verilog -out avsd_pll_1v8_net.v
```

![image](https://user-images.githubusercontent.com/118953917/211707052-5eea3774-75f6-4f1a-9a59-2e0e7d6d1c33.png)
  
**Netlist of avsd_pll_lv8.v**
  
![image](https://user-images.githubusercontent.com/118953917/211707102-80af24c0-0e64-4ad3-b929-781e3ccb2e43.png)
  
  
  
### VSDBabySoC
  
```
sh gvim .synopsys_dc.setup
set target_library {/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db}
set link_library {* nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/sky130_fd_sc_hd__tt_025C_1v80.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db}
```
  
```
echo $target_library
echo $link_library
read_file {mod_mythcore_test.v mod_avsd_pll_1v8.v mod_avsddac.v clk_gate.v mod_vsdbabysoc.v} -autoread -format verilog -top vsdbabysoc
compile
write -f verilog -out vsdbabysoc_net1.v
``` 
  
![image](https://user-images.githubusercontent.com/118953917/211965920-d89fad34-d839-436e-b114-35a916b7c300.png)

**Netlist of VSDBabySoC**
  
![image](https://user-images.githubusercontent.com/118953917/211966018-18e67c13-b0ba-48db-9f4c-dce2e935e507.png)
  
</details>

<details>
  <summary>Lab: Post-synthesize and comparisons</summary>
 
### Post-synthesizing simulations 
  
**rvmyth_avsddac.v**
  
```
vcs mod_rvmyth_avsddac_net.v rvmyth_avsddac_TB.v
  
```
</details> 

## Day-14

### Topic: Synopsys DC and Timing Analysis

<details>
  <summary>Theory</summary>
 
### Recap 
  
**What is synthesis?**
  
* RTL to gate level translation
* The design is converted into gates and the connections are made between the gates
* This is given out as a file called netlist
  
**What is .lib?**
  
* Collection of logical modules
* Includes basic logic gates like AND, OR, NOT, etc.
* Different flavors of the same gate
  
**Why different flavours of gate is needed?**
  
* Combinational delay in logic path determines the maximum speed of operation of digital logic circuit
* So, we need cells that work faster to make Tcombi small
  
**What to achieve in logic synthesis?**
  
Working digital logic circuit is:

* Logically correct
* Electrically correct
* Timing met
  
*Note: To give more delay to the circuit to meet setup/hold time, we need to add buffers. However, additional buffers to meet hold, will add additional area.*
  
**How to decide for the correct implementation of the design?**
  
By using constraints
  + Constraints are the guide to the synthesizer to pick the correct library cells which is most appropriate for the design
  + The illustrations are picked based on the needs
  
**What is CTS?**
  
* Clock Tree Synthesis: a technique for distributing the clock equally among all sequential parts of VLSI design
* Purpose: to reduce skew and delay. CTS provide the placement data as well as the clock tree limitations as input.
  
*Source: https://www.google.com/search?q=cts+in+vlsi&rlz=1C1GCEA_enMY1023MY1023&oq=cts+in+vlsi&aqs=chrome..69i57j0i512j0i22i30l8.2308j0j7&sourceid=chrome&ie=UTF-8*
  
**PVT stands for?**
  
* Process, Voltage, Temperature
  
**Corners of PVT**
  
* Integrated circuits are designed in such a way that they can function in a wide variety of temperatures and voltages, rather than a single temperature and voltage
* In order to make our chip to work after fabrication in all possible conditions, we simulate it at different corners of process, voltage, and temperature
* These conditions are called corners. All these three parameters directly affect the cell delay

**Understanding PVT**
  
* **Process** -> there are millions of transistors on a single chip as we are going to lower nodes and all the transistors in a chip cannot have the same properties. Process variation is the deviation in parameters of the transistor during the fabrication
* **Voltage** -> as we are going to lower nodes, the supply voltage for a chip is also going to less. If the chip is operating at 1.2V, there are chances that at certain instances of time this voltage may vary
* **Temperature** -> when a chip is operating, the temperature can vary throughout the chip. This is due to the power dissipation in the MOS-transistors
  
**PVT Graphs**
  
*Source: https://onedrive.live.com/?authkey=%21APiDwU9SDyOxl5w&cid=E0E9B5EEF85B162E&id=E0E9B5EEF85B162E%2199590&parId=E0E9B5EEF85B162E%2197363&o=OneUp*
  
![image](https://user-images.githubusercontent.com/118953917/211721237-90fa20cc-d0ce-4e88-bf63-46a673c4e1ed.png)

  
</details> 

<details>
  <summary>Task and labs</summary>
 
### Task
  
**Steps to read PVT corners of each timing libs provided**
 
### Converting .lib to .db using lc_shell
  
```
cd /nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training
git clone https://github.com/Geetima2021/vsdpcvrd.git
/nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/vsdpcvrd/resources/timing_libs
lc_shell
read_lib sky130_fd_sc_hd__ff_100C_1v65.lib > 100C_1v65.rpt                         (Error reading lib file -> remove the line in lib with those errors)
```
  
**Error debugging -> grepping errors from .rpt file**
  
![image](https://user-images.githubusercontent.com/118953917/211825198-f8a621b1-d89e-49c7-9ddb-ca2610a95d4b.png)

**Modification of .lib file**
  
![image](https://user-images.githubusercontent.com/118953917/211825404-41ac67e1-fd19-48be-8488-3c676300ca5b.png)

```
read_lib sky130_fd_sc_hd__ff_100C_1v65.lib
write_lib sky130_fd_sc_hd__ff_100C_1v65 -format db -output sky130_fd_sc_hd__ff_100C_1v65.db
```
  
![image](https://user-images.githubusercontent.com/118953917/211831483-dcf4b51a-3a58-4ada-a452-7ad59b264736.png)

> Moving converted .db file from cheetah environment (santa clara zsc11) to png site 
```
/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d14/timing_libs                (Penang site)
rsync -rv rsync.zsc11.intel.com:/nfs/site/disks/zsc11_mip_xmphy_0021/users/nazahah/partition/training/vsdpcvrd/resources/timing_libs/sky130_fd_sc_hd__ff_100C_1v65.db .    ("." stands for current directory)
```
  
### Synthesizing and optimizing
  
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d14/timing_libs
sh gvim cons.sdc
```
  
**Setting the constraints**
  
![image](https://user-images.githubusercontent.com/118953917/212027191-97e051b3-1d26-431d-be55-d5b558625ae0.png)
  
```
sh gvim .synopsys_dc.setup
 
set target_library {/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d14/timing_libs/sky130_fd_sc_hd__ff_100C_1v65.db}
set link_library {* /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsdpll.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/db_files/avsddac.db /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d14/timing_libs/sky130_fd_sc_hd__ff_100C_1v65.db} 
```
  
![image](https://user-images.githubusercontent.com/118953917/212027266-f27dc504-4949-4892-aa64-c916e2982384.png)
  
```
dc_shell
echo $target_library
echo $link_library
read_file {mod_mythcore_test.v mod_avsd_pll_1v8.v mod_avsddac.v clk_gate.v mod_vsdbabysoc.v} -autoread -format verilog -top vsdbabysoc
link
read_sdc cons.sdc
compile_ultra
report_qor
```

![image](https://user-images.githubusercontent.com/118953917/212027341-33ed43df-6a54-4e8c-b802-3b9fe5eefb12.png)
  
*Note: Change the synopsis setup and repeat the same steps for all PVT corners files*
*Don't forget to source new edited .synopsys_dc.setup*
  
**Short discussions regarding PVT corners**
  
* WNS (Worst Negative Slack) -> slack for the timing path with worst timing failure 
  + If WNS is positive, the path has passed. Else, it failed. 
  + Applicable to setup time
  
* WHS (Worst Hole Slack) -> slack for hold path with worst timing failure
  
* TNS (Total Negative Slack) -> sum of the total negative path slacks, or the sum of all WNS
  + If TNS = 0, the design meets timing. Else, if it is positive, there is negative slack in the design (hence the design fails). 
  + TNS cannot be negative
  
* THS (Total Hold Slack) ->  sum of the total negative hold slack paths, or the sum of all WHS
  + If THS = 0, the design passed. Else, if it is positive, the design failed.
  
**Summary of all PVT corners provided**
  
![image](https://user-images.githubusercontent.com/118953917/212031365-7279d9cc-b689-42d5-9dcb-c22d24204deb.png)

</details>

## Day-15

### Topic: Inception of EDA and PDK

<details>
  <summary>What is a package?</summary>
 
### Introduction to QFN-48 Package, chip, pads, core, die and IPs
  
**What is package?**
  
It is the material that contains semiconductor device attached with a die using wire bonding. Package is a container that holds die and was connected to outside (external device) by using wire bonding. Example of package - Quadruple in-line package (QIP) and Dual in-line package (DIP).
  
**Example of a real package in industry**

![image](https://user-images.githubusercontent.com/118953917/212086264-1703bc90-452c-41f9-8c76-f9f7bff3aef0.png)
  
**Example of typical ports in an Arduino**
  
![image](https://user-images.githubusercontent.com/118953917/212086463-019c1922-2dae-4ca4-8c55-0e57a5b24c28.png)
  
**Example of the package inside Arduino**
  
* Package: QFN-48
* Quadflat no leads
* Comes in a square size where both length and width are 7mm
* The chip will be placed at the centra; of the package
* Wire bond will be interconnecting the chip with the ports and pins
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212086529-6dee0954-fca5-4189-9e9e-056381851004.png)
  
**Elements inside a package**
  
* Pad: surface mount of pins connected and it is used to connect inside (core) to outside (I/O), good at ESD protection to prevent charge coming from outside that would damage the core inside
* Core: consists of all the main logic gate (NMOS/PMOS) and cell block such as macro cell and foundry IP's
* Die: the actual silicon chip (IC) that would normally be inside a package/chip
* Foundry IPs: cell with more specific functionality and the design was patent/owned by a company, as well as having a higher value compared to macros and cannot be found online
* Macros: protocol to transfer data using simple functionality and can be found online

</details>
    
<details>
  <summary>Introduction to RISC-V</summary>
 
### Introduction to RISC-V
  
**RISC-V Instruction Set Architecture (ISA)**
  
**Process of converting RISC-V architecture to layout**
  
* The C codes will be compiled in RIS-V assembly language program
* The assembly language will be converted to machine language which is binary language containing logic 0 and logic 1 that is understood by the computer/hardware
The converted binary language will be sketched in a layout by the computer program and we will get the required output
* However, there is another interface that should be presented between architecture and layout of RISC-V which is **Hardware Description Language (HDL)** where it used RTL implementing the specifications of RISC-V
  
*Source: https://www.vlsisystemdesign.com/*

*Credit to: Kunal Gosh*
  
![image](https://user-images.githubusercontent.com/118953917/212091056-24dde7f6-fc24-46cd-9510-09f3237cf2c8.png)

</details>
    
<details>
  <summary>How to talk to computers?</summary>
 
### Communication of Software and Hardware
  
* The tool will undergo synthesis process which is converting software’s instructions in HLL to machine language in binary format
  
**Flow of the the synthesis process**
* Software (HLL) -> System software (assembly language) -> Hardware (machine language)
* Basically, the application software would enter the clock of the system software and the system software would convert the application program into the binary language
* One of the major operation in system software is Operating System (OS) would take the particular applications and convert it into respective assembly language program and binary program, so that the program will be understood by the hardware
* The converted binary language/machine language will fed into the hardware and it will generate the output
  
**Major layer/components of system software**
 
* Operating System (OS)
  + Handle IO operations
  + Allocate memory
  + Low level system functions

* Compiler
  + Converting the programming language into the respective intructions 
  + The syntax of the instruction is depending upon what kind of the hardware is, i.e. if the hardware belongs to RISc-V format, the syntax would have the syntax of RISc-V file format instructions

* Assembler
  + Take particular instructions and convert it into the respective binary number which is machine language program
  + Consisting of logic 1 and logic 0 where the computer/hardware understands the language

**Process flow and its example**
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212218492-1e0bc3d1-bbe5-4574-a8dc-4bd8517e652d.png)

![image](https://user-images.githubusercontent.com/118953917/212219102-4e6d41fc-2de0-41fd-b04c-b02675886d0e.png)

</details>
    
<details>
  <summary>SoC design and OpenLANE</summary>
 
### Introduction to all components of open-source digital ASIC design
  
* Designing ASIC flow in an automated way requires several elements:
  
  + Hardware Description Language (HDL) which Register Transfer Level (RTL) model of the function we want to implement including RTL's IP
  + Tool used for automation i.e. EDA tools
  + Process Design Kit (PDK) data
  
**Open source digital ASIC design**
  
*Source: the image has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212222308-d4607e49-a968-45c1-b69c-54b25f369950.png)
  
**Getting to know PDK**
  
* PDK: the interface between the fabrications and the designers
* PDK -> stands for Process Design Kit

* Collection of files used to model a fabrication process for EDA tools used to design an IC
  + Process Design Rules: DRC, LVS, PEX
  + Device models
  + Digital Standard Cell Libraries
  + I/O libraries
  
**List of EDA tools available**
  
* HDL simulation
* Floor planning
* Detail placement
* HDL design entry
* IR drop analysis
* DRC
* Logic equivalence checking
* Fill insertion
* LVS
* DFM
* RC extraction
* DFT
* Power planning
* STA
* Global placement
* Logic synthesis
* RTL synthesis
* Global routing
* Detailed routing
* Static code analysis
* CTS
  
</details>
    
<details>
  <summary>Simplified RTL2GDS flow</summary>
 
### Simplified RTL to GDS flow
  
**ASIC Design Flow**

* Flow objective: RTL to GDSII
  + Also called Automated PnR and/or Physical Implementation
  
**Simplified RTL to GDSII flow**
  
* Major implementations of ASIC flow:
  + Synthesis 
  + Floor/power planning
  + Placement 
  + Clock tree Synthesis
  + Routing
  + Sign-off
  
![image](https://user-images.githubusercontent.com/118953917/212224976-4eef3690-43ec-4240-a466-7065c5eb7865.png)

**Synthesis**
  
* The process of converting RTL to a circuit out of components from the standard cell library (SCL)
* The result of the circuit is described in HDL and usually refered to as gate level netlist, also it is functional equivalent to RTL

* "Standard Cells" have regular layout and each cell has different views/models:
  + Electrical, HDL, SPICE
  + Layout (Abstract and detailed)

*Source: http://vlsitechnology.org/*
  
![image](https://user-images.githubusercontent.com/118953917/212226980-4c5645c4-1086-4456-b1a0-9acc4f9fd039.png)

**Floor and Power Planning**
  
* Chip Floor Planning: partition the chip die between different system building blocks and place the IO pads
  
*Source: the image has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212227502-cc0232d6-b93b-439d-85e4-f17d608ca454.png)
  
* Macro Floor Planning: dimensions, pin locations, rows and definition
* Power Planning: the power is provided  to the every macros, standard cells, and all other cells are present in the design. Typically, the power distribution network using upper metal layers since they are thicker than lower metal layers
  
*Source: the image has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212228282-a5655967-278a-4123-a2a3-8ac4059a86fc.png)

**Placement**
  
* The process of placing the cells on the floor plan rows, aligned with the sites. Also, the process of finding a suitable physical location for each cell in the block.
* Macros would place the gate level netlist cells on the rows and the cells should be placed very close to each other to reduce an interconnect delays and enable successful routing 
* Usually done in two steps: 
  + Global: a very first stage of the placement where cells are placed inside the core area for the first time looking at the timing and congestion, it aims at generating a rough placement solution that may violate some placement constraints while maintaining a global view of the whole netlist
  + Detailed: the position obtained from global placements are minimally altered 
  
*Source: the image has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212229348-d78afab6-bb60-452a-a4b5-91c171ae389b.png)

![image](https://user-images.githubusercontent.com/118953917/212229384-2435bef0-9e0d-44e5-be2a-484b8cc5fe5e.png)
  
**Clock tree synthesis (CTS)**
  
* The process of routing the clock by creating the clock before entering major routing process 
  
* Create clock distribution network
  + To deliver the clock to all sequential elements i.e. Flip Flop
  + With minimum skew (zero is hard to achieve) 
  + Achieve a good shape
  + Usually in a Tree (H, X, ...)
  
*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212230550-fbdd1ced-de40-4b0f-bfd5-2d6d5a7ac1f2.png)

**Routing**
  
* The process of implementing the interconnect using the available metal layers
* Metal is tracks from a routing grid
* As the routing grid is huge, it used divide and conquere approach:
  + Global Routing: generating routing guides
  + Detailed Routing: using routing guides to implement the actual wiring

*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212230891-49472921-52c4-4e88-a8a6-63a5ef42cedd.png)

**Sign-off**
  
* Final layout which undergoes verifications 
* Physical verifications
  + Design Rule Checking (DRC) -> ensuring the final layout obeys all the design rules
  + Layout vs Schematic (LVS) -> ensuring the final layout matches the gate level netlist of the design
* Timing verification
  + Static Timing Analysis (STA) -> ensuring all the timing constraints are met and the circuit will run at designated clock frequencies
  
</details>
    
<details>
  <summary>Introduction to OpenLANE and Strive chipsets</summary>
 
### Introduction to OpenLANE and Strive chipsets

**Open Source ASIC Flow**
  
* The problem is tougher when using open source EDA
  + Tools qualification
  + Tools calibration
  + Missing tools 
  
**What is OpenLANE?**
  
* Started as an Open-Surce Flow for a True Open Source Tape-Out Experiment
* striVe is a family of open everything SoCs i.e. Open PDK, Open EDA, Open RTL

*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212237000-a7dd821a-7868-4ada-8a6a-9e6eef95de73.png)

![image](https://user-images.githubusercontent.com/118953917/212237209-e8c58106-c544-4606-bd26-da2d61eae4e1.png)

**OpenLANE ASIC Flow**
  
* Main goal: to produce a clean GDSII with no human intervention (no-human-in-the-loop)

* Clean means: 
  + No LVS violations
  + No DRC violations
  + No timing violations 
  
* Tuned for SkyWater 130 nm Open PDK, also supports XFAB180 and GF130G 
  
* Containerized 
  + Functional out of the box
  + Instructions to build and run natively will follow 
  
* Can be used to harden Macros and Chips
  
* Two modes of operation:
  + Autonomous
  + Interactive 
  
* Design Space Exploration feature
  + Finding the best set of flow configurations 
  
* Comes with large number of design examples
  + 43 designs with their best configurations
  
</details>
    
<details>
  <summary> Detailed ASIC design flow</summary>
 
### Introduction to OpenLANE:  Detailed ASIC design flow
  
**OpenLANE ASIC Flow (Detailed design flow)**
  
* The steps flow is much more detailed than the one that has been presented before
  
* The flow started from RTL design and ended with final layout in GDSII format by using the function of PDK
  
* OpenLANE is based on several open source project i.e. OpenROAD, KLayout, Yosys, QFlow, ABC, Magic VLSI Layout Tool, Fault, and etc.

*Source: the image has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212254333-481efbdf-884b-47b5-bc1d-be4712e886bc.png)
  
* The step starts with RTL synthesis where RTL is fed into Yosys with the design constraints. Yosys will translate the RTL into logic circuits and be optimized
  
* The optimized circuit will be mapped into cells from the cell library using abc where abc has to be guided during the optimization. OpenLANE comes with several abc scripts 
  
**Synthesis exploration**
  
* Synthesis exploration utility is used to generate report that shows the design delay and area 
* From the exploration, we can pick the best strategy to proceed with
* Also, synthesis exploration utility can be used to sweep the design configurations and generate reports
* The report is observed and ensuring the number of violations generated after generating the final layout 
* The best configurations can be picked from the design
  
*Source: the example has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212255397-97292c9c-e1ea-4fb7-8f5a-b7f292cfffc5.png)

**OpenLANE Regression Testing**
  
* The design exploration utility is also used for regression testing (CI)
* Running OpenLANE in several +-70 designs and compare the results to the best known ones
  
*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212256602-e0f693b0-514f-4442-b98f-d2f23273d6e8.png)

**DFT**
  
* After synthesis, DFT is ready to be testing before fabrication (optional step) using open source project which is Fault

* Performing several steps including:
  + Scan Insertion 
  + Automatic Test Pattern Generation (ATPG)
  + Test Patterns Compaction 
  + Fault Coverage
  + Fault Simulation
  
*Source: the example has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212257599-bd8ef164-1a26-46cb-8698-a5700975d5c3.png)

**Physical implementation**
  
* Also called automated PnR (Place and Route)
  
* Using OpenRoad open source to perform the implementation
  
* Involves several steps including
  + Floor/Power Planning
  + End Decoupling Capacitors and Tap cells insertion
  + Placement: Global and Detailed
  + Post placement optimization
  + Clock Tree Synthesis (CTS)
  + Routing: Global and Detailed

**Logic Equivalent Check (LEC)**
  
* Everytime the netlist is modified, verifications must be performed
  + CTS modifies the netlist
  + Post Placement optimization modifies the netlist
  
* LEC is used to formally confirm that the function did not change after modifying the netlist
  
* Open source application used: Yosys
  
**Dealing with Antenna Rules Violations**
  
* A special step during physical implementation is called Antenna Diodes Insertion
  
* This step is required for antenna worst violations
  
* When a metal wire segment is fabricated and it is long enough, it can act as antenna
  + Reactive ion etching causes charge to accumulate on the wire
  + Transistor gates can be damaged during fabrication 
  
* Solutions
  + Bridging attaches a higher layer intermediary (Requires router awareness)
  + Add antenna diode cell to leak away charges (Antenna diodes are provided by SCL)
  
*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212262857-87f12d22-c825-4e27-9181-7e26057f17af.png)

* With OpenLANE, we took preventive approach by:
  + Adding a fake antenna diode next to every cell input after placement
  + Run the antenna checker (Magic) on the routed layout
  + If the checker reports violations on the cell input pin, replace the fake diode cell by a real one
  
*Source: the example has been taken from instructor's video*

![image](https://user-images.githubusercontent.com/118953917/212266874-48585c47-61ec-479f-b5ec-3e89ca62004f.png)

**Static Timing Analysis (STA)**
  
* RC Extraction: DEF2SPEF
* STA: OpenSTA (using OpenROAD) 
* Involving timing reports to check violations in timing paths 
  
**Physical verification DRC & LVS**
  
* Magic is used for Design Rule Checking and SPICE Extraction from Layout
* Magic and Netgen are used for LVS where extracted SPICE by Magic vs verilog netlist are used 

</details>
    
<details>
  <summary> Lab 1: Getting familiar to open source EDA tools</summary>
 
### Lab 1: OpenLANE Directory structure in detail
  
* OpenLANE is not a tool but a flow that is comprises to many EDA tools i.e. Yosys, etc.
* Objective of using OpenLANE: to convert RTL scripting to GDSII scripting
  
```
cd work/tools/
ls -ltr
cd openlane_working_dir/
ls -ltr
cd pdks
ls -ltr
cd sky130A/
ls -ltr
cd libs.ref/                (Specifically to the technology/process)
ls -ltr
cd ..
cd libs.tech/               (Specifically to the tools)
ls -ltr
cd ..
cd libs.ref/
ls -ltr
cd lib/                     (Getting to know PVT corners)
ls -ltr
cd ..
cd lef/
ls -ltr
```
  
![image](https://user-images.githubusercontent.com/118953917/212288000-296246a4-0f2b-4aa6-80b8-c191ec6717ce.png)

</details>
    
<details>
  <summary> Lab 2: Design Preparation Step</summary>
 
### Lab 2: Design Preparation Step

*Source: https://github.com/nickson-jose/openlane_build_script*
  
> Invoking openlane
```
cd work/tools/openlane_working_dir/openlane
make mount
pwd
ls -ltr
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
```
  
![image](https://user-images.githubusercontent.com/118953917/212351992-e9d2f493-0dbb-4546-80de-90d6fe2ea405.png)
  
> In terminal
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a
vim config.tcl
vim sky130A_sky130_fd_sc_hd_config.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/212340670-bda528ca-97db-4dc3-9fa1-196f9388d432.png)

</details>
    
<details>
  <summary> Lab 3: Reviewing Files</summary>
 
### Lab 3: Review files after design prep and run synthesis
  
> In terminal
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a
ls
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/tmp
ls -ltr
vim merged.lef
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09
vim config.tcl
vim cmds.log
```
  
![image](https://user-images.githubusercontent.com/118953917/212351814-5235de8b-e06e-4bd4-ab74-e5bde99d900f.png)
  
> In openlane
```
run_synthesis
```
  
![image](https://user-images.githubusercontent.com/118953917/212352881-d5807bd7-621d-4c50-a4a1-7e5a3f93b538.png)

</details>
    
<details>
  <summary> Lab 4: OpenLANE Project Git Link Description</summary>
 
### Lab 4: OpenLANE Project Git Link Description
  
*Visit and browse through the link https://github.com/efabless/OpenLane to know more about OpenLANE*
  
</details>
    
<details>
  <summary> Lab 5: Characterizing synthesis results</summary>
 
### Lab 5: Steps to characterize synthesis results
  
From the previous lab session, after synthesizing and get the results;
  
Flop ratio = 10.84%
  
Flop ratio of the design is calculated as below:
  
![image](https://user-images.githubusercontent.com/118953917/212362794-40f9b972-08c0-48ec-8a8b-15bd53a4ba2b.png)

> In terminal
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
vim picorv32a.synthesis.v
cd /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/reports/synthesis
vim 1-yosys_4.stat.rpt
vim 2-opensta.rpt
```
  
![image](https://user-images.githubusercontent.com/118953917/212367232-4077a988-4c4c-46dc-a6a5-0ec6da2503b1.png)

</details>

## Day-16

### Topic: Understand importance of good floorplan vs bad floor plan and introduction to library cells

### Chip Floor planning considerations
<details>
  <summary>Lecture 1: Utilization factor and aspect ratio</summary>
 
### Utilization factor and aspect ratio
  
**Defining width and height of the core and die**
  
1. Begin with a simple netlist as an example
* Consider a netlist with 2 flops and 2 gates with below connections 
*Note: a netlist describes the connectivity of an electronic design*

![image](https://user-images.githubusercontent.com/118953917/212586111-49b04c72-3ef0-4de2-92af-77182d19a591.png)

2. Convert the components/symbols into physical dimension
  
![image](https://user-images.githubusercontent.com/118953917/212587431-c7aa9bb0-1bfc-45f2-9a92-2c2533601a7a.png)
  
3. Find out the dimesion of the core and die
*Note: Only focus on the dimensions of the standard cells and flops, not the wires*
  
Let say, the dimension of standard cell is 1 unit by 1 unit. Hence, the area is 1 sq. unit as shown
  
![image](https://user-images.githubusercontent.com/118953917/212588313-edb52e12-b691-4c08-bb16-c5842866558e.png)

Assume the same for flip flop
  
![image](https://user-images.githubusercontent.com/118953917/212589262-5800a3b2-a07e-45f4-a6f3-cef4246d1822.png)

4. Calculate the area occupied by the above netlist on a Silicon wafer by:
  * Remove the wires and place all the physical dimensions into a single grid
  
![image](https://user-images.githubusercontent.com/118953917/212590234-3532ee54-547a-4407-909a-027e916d4f81.png)
  
**Recap: What is core and die section of a chip?**
  
* Core: the section of the chip where the fundamental logic of the design is placed
* Die: consists of core (encapsulate the core), it is a small semiconductor material specimen on which the fundamental circuit is fabricated
  
*Source: the illustration has been taken from instructor's video*
  
![image](https://user-images.githubusercontent.com/118953917/212591511-3af66b9e-e24a-4fed-9ef9-9192b0693289.png)
  
* How to arrive on its dimensions?
5. Place all the logic cells inside the core
  * The logical cells occupies the complete area of the core with 100% utilization
  * If there is some areas left out, it will not be 100% utilization, it may be some other number
  
  
![image](https://user-images.githubusercontent.com/118953917/212591281-a945f01a-0a28-42ef-92c6-68f47e442ef7.png)
  
* Since utilization factor = 1, equivalent to 100% utilization, and if there is some extra logic needs to be added, that is not allowed because there is no space left
* This 100% utilization is usually as an ideal scenario, but in practical scenario, we only utilized up until 50% to 60% utilization
* Whenever the aspect ratio = 1, it signifies that the chip is in square-shaped, else if aspect ratio is the other number except 1, it signifies that the chip is in rectangular-shaped

![image](https://user-images.githubusercontent.com/118953917/212791884-9a22ef2f-b4a5-4c4d-b1c3-3e88cc81c307.png)
  
* Let say the dimentions of the die and core is wider;
  
* As we can see from the example below, the core is 50% utilized by the logic and another remaining space/area can be used for any additional cells 
* Defining the utilization factor and aspect ratio are significant especially when we're doing floor planning
  
![image](https://user-images.githubusercontent.com/118953917/212794558-13c1047d-392d-4edd-a79e-36f832cbb1c2.png)
  
</details>

<details>
  <summary>Lecture 2: Concept of pre-placed cells</summary>
 
### Concept of pre-placed cells
  
**Continue on defining width and height of the core and die**
  
* Let say the core and die is bigger with the same height and width;
  
* Referring to the example below, the core has been utilized with 25% of the combinational logic and it has another 75% space/area which can be used for any additional cells
* Also, the free space can be used for more additional layers of routing
* Since aspect ratio = 1, it signifies the square-shaped
  
![image](https://user-images.githubusercontent.com/118953917/212796719-e8d0b937-3c9d-4a2e-a61e-3f7619ee81ed.png)
  
**Defining the location of the pre-placed cells**
  
![image](https://user-images.githubusercontent.com/118953917/212799249-0a383654-bdd4-4f3c-aa17-863867a8e727.png)

**What are the pre-placed cells?**
  
* Combinational logic basically does some functionalities i.e. memory, mux, any complex clock divider or etc.
* Combinational logic does a huge task and produced some huge output circuits
* Therefore, we need to extract it out and divide that huge output circuits into multiple blocks and then separate them out into different blocks 
* Referring to the separated blocks below, block 1 and block 2 will be implemented separately 
  
![image](https://user-images.githubusercontent.com/118953917/212802067-76e7d27c-f106-4305-84ab-f6afa1276c23.png)

* Block 1 contains the input of the pins while block 2 contains the output of the pins
* We then need to extend those IO pins of the two blocks and detached those blocks with the black boxes
* Those two blocks will then be invisible for the side that is looking from the top/main netlist
* Since those sections of the boxes are now invisible to the top netlist that we're implemented, we will now separate the black boxes as two different IP's or modules
* The advantages of separating those blocks are it is more convenient to use them for multiple times when needed with different users where they will be implemented separately based upon their functionalities. Also, those blocks can be reused separately for each block for multiple times when needed.
  
![image](https://user-images.githubusercontent.com/118953917/213130615-55d6489f-e256-4c62-8a24-4d77c20eb3c5.png)
  
* Similarly, there are any other IP's that are available, i.e.;
  + Memory
  + Clock-gating cell
  + Comparator
  + Mux
* All of them can be implemented once and can be instantiated multiple times onto a netlist
* However, this is no need to be implemented for multiple times because this is a part of top-level netlist where they perform some functions, where they receive some inputs signals, they deliver some output signals, but the functionality of the particular cells will be implemented only once
* This is what we called as pre-placed cells since the cells are being just placed once in a chip where we have to define the locations/arrangements of the particular cells and it has to be done before the routing
* The placement and arrangements of the cells on top-level chip will be fixed and they will not being moved even by automated tools
* Since they are being placed before the routing, they are called pre-placed cells 
  
* The arrangement of these IP’s in a chip is referred as Floorplanning
* These IP’s/blocks have user-defined locations, and hence are placed in chip  before automated placement-and-routing and are called as pre-placed cells.
* Automated placement and routing tools places the remaining logical cells in the design onto chip

</details>
  
<details>
  <summary>Lecture 3: De-coupling capacitors</summary>
 
### De-coupling capacitors
  
**Defining on pre-placed cells**
  
* For example, consider there are three pre-placed cell blocks including block A, block B, and block C where we implemented memories for once and they will be reused for multiple times in the circuit
* Most of the blocks are communicating with input pins. Hence, the blocks will be usually being placed near the input side depending on the scenario/design background
* Once the location has been set to place the blocks, the location can't be moved. Therefore, the location needs to be very well defined

![image](https://user-images.githubusercontent.com/118953917/212816258-75cdada2-e5d4-4f22-9b46-43e7e60aca6f.png)
  
**Surrounding the pre-placed cells with Decoupling Capacitors**
  
* Consider the amount of the switching current required for a complex circuit something like below
  
* Referring to the diagram below;
  
1.	Consider capacitance to be zero for the discussion. Rdd, Rss, Ldd and Lss are  well defined values.
2.	During switching  operation, the circuit demands switching current i.e. peak current (Ipeak).
3.	Now, due to the presence of Rdd and Ldd, there will be a voltage drop across them and the voltage at Node 'A' would be Vdd' instead of Vdd.
4.	If Vdd' goes below the noise margin, due to Rdd and Ldd, the logic '1' at the output of circuit won't be detected as logic '1' at the input of the circuit following this circuit.
  
*Source: https://www.vlsisystemdesign.com/*

![image](https://user-images.githubusercontent.com/118953917/212812045-c46db167-d66c-4a81-8d90-73e4f1246306.png)

**Noise margin summary**
  
* Anything that lies between Vol and Vll will be considered as logic 0 
* Any voltage that lies between Vll and Vih will be considered as undefined region 
* Undefined region -> the logic can either moved from logic 1 to logic 0 or from the interception point of (b) to logic 0. Undefined region is a danger case 
* Whenever the voltage lies between Vih and Voh, it will always being treated as 1V or logic 1
* Therefore, we have to ensure that the voltage didn't enter in undefined region since it cannot be identified whether the voltage might be in logic 1 or not
* That is the problem when we are having a large physical distance from the main power supply to the circuit
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212813997-d1f1a5c0-dc8e-4356-b175-c692c4ec5c4c.png)

  
* To solve this issue, we have to add decopuling capacitors 
* Consider the decoupling capacitor is a huge capacitor which is completely be filled with the charge and the equivalent voltage across the decoupling capacitor is similar to what we have in the power supply
* Add the decoupling capacitor in parallel with the circuit
* Decoupling capacitor would decouples the circuit from the main supply 
* Everytime the circuit switches, it draws current from Cd. Whereas, the RL network is used to replenish the charge into Cd
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212817283-9d6cda09-9700-4ed4-a70c-6b0527215c25.png)
  
* Overview of pre-placed cells on a top-level netlist across the decoupling capacitors and the blocks
  
![image](https://user-images.githubusercontent.com/118953917/212817436-6134ebd8-14bc-4e5f-970b-bcce194cc73a.png)

</details>

<details>
<summary>Lecture 4: Power planning</summary>

### Power planning
  
* From previous example, let's take the circuit and converted into a black box and denoted it as a macro/block
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212826749-fba0ba9b-69fb-4669-a7d7-2bb77b0f8a49.png)

* Let say there are 4 different macros/blocks containing driver, load, and etc that are usually available in a complete chip with different functionalities
* The voltage source was supplied for 4 blocks. Hence, the supply from the source will be not stable where it is impossible to put all the decoupling capacitors.
* Let's assume the orange line was 16 bit bus
* Logic 1 indicates that the capacitor is being charged to Vdd while logic 0 will be discharged to the Ground
* This 16 bit bus is connected with the inverter, so the output will be inverted from the input. Logic 1 will be discharged and while logic 0 will be charged.
* All the capacitors that were charged to volts will be discharged to 0 volt through single Ground tap point. This will cause a bounce in Ground tap point.
* If this bounce exceeds the noise margin level, it will reaches undefined state, where during that stage, the voltage might be changed from logic 1 to logic 0 and it is unpredictable 
* All capacitors which were '0' volt will have to charge to 'V' volts through single Vdd tap point. This will cause lowering of voltage at Vdd tap point
* The level of Ground Bounce and Voltage Droop will be increased due to the multiple process of tap points happened at the same time. 
* If this voltage droop is within the noise margin level, it will be enough but if it exceeded undefined region in the noise margin level, we will in danger zone

*Source: https://www.vlsisystemdesign.com/*

![image](https://user-images.githubusercontent.com/118953917/212834088-97e65ccf-00db-4b79-8b59-68e105fb198e.png)


* To fix this issue, we need to use multiple power supply (i.e. multiple  Vdd and Vss) instead of using 1 power supply only
* Multiple power supply will be sourced to the nearest block and it will prevent the block from being missed to get the power supply
* Therefore, all the logics will take the nearest power supply
* The driver and the load also can be brought closed to each other in 'L' sense

*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212835786-e010e5f5-4576-407f-a43e-b08ed5e6aea3.png)
  
</details>

<details>
<summary>Lecture 5: Pin placement and logical cell placement blockage</summary>

### Pin placement and logical cell placement blockage

* Let's take several designs as examples that need to be implemented
* Along with the circuit, there are some pre-placed blocks as well that is being connected to the input circuit and being clocked out 
* There are 4 designs in total with different connections to be looking through in this section
* By merging all of the four designs, it will be a complete design 

![image](https://user-images.githubusercontent.com/118953917/212839899-2651497a-b8bf-4d8d-9f5d-c45188a2f13d.png)

**Pin placement of the complete design**
  
* For the design plan, the input port is set to be on the LHS while the output port is set to be on the RHS
* Input ports and output ports are placed randomly since it is depending on our the design planning
* The pins are placed depending on the blocks
* No cells/flip flops can be placed on the block a, block b and block c area
* Clock ports which are CLK1, CLK2 and Clkout are bigger in size as compared to data ports since the clock is the ports that are driving all the cells and sending the signals to all flip flops
* Bigger the size, least the resistance. Therefore, clock ports need to be bigger in size to avoid resistance during signal transmission since clock plays an important role in sending the signals
  
*Source: https://www.vlsisystemdesign.com/*
  
![image](https://user-images.githubusercontent.com/118953917/212844989-78948f55-f883-4eb1-bd09-7e6a4fc9cf35.png)

</details>

<details>
<summary>Lab 1: Steps to run floorplan using OpenLANE</summary>

### Steps to run floorplan using OpenLANE
  
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
  
![image](https://user-images.githubusercontent.com/118953917/212850404-c5806032-162e-46fd-afbf-ac313433a657.png)

```
vim floorplan.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/212851351-44319a52-c656-4d87-931a-aa8079ccdf0a.png)

```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a
vim config.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/212937440-c3afd92a-87d8-4ffb-8144-d98212cb3f76.png)
  
> In OpenLANE terminal
```
run_floorplan
```
  
![image](https://user-images.githubusercontent.com/118953917/212854551-c8c84876-318a-496b-947f-6c28f2d0de0a.png)

</details>

<details>
<summary>Lab 2: Review floorplan files and steps to view floorplan</summary>

### Review floorplan files and steps to view floorplan
  
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/logs/floorplan
vim 4-ioPlacer.log
```
  
![image](https://user-images.githubusercontent.com/118953917/212937620-16ef4520-7e0c-48b9-b428-ef5b3ddc7dff.png)
  
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/
vim config.tcl
```

![image](https://user-images.githubusercontent.com/118953917/212937722-d220fefa-48ec-4f46-bc95-954d11ae697b.png)
  
```
cd ../Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/floorplan
vim picorv32a.floorplan.def
```

![image](https://user-images.githubusercontent.com/118953917/212937842-402075ea-8ab9-4028-b6dd-f76e3c6e4e80.png)

</details>

<details>
<summary>Lab 3: Review floorplan layout in Magic</summary>

### Review floorplan layout in Magic
  
```
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
  
![image](https://user-images.githubusercontent.com/118953917/213065626-ef4a7930-e0ba-45e2-a747-005fcb1677f4.png)
  
![image](https://user-images.githubusercontent.com/118953917/213065684-9726f790-fd91-44d4-b1b3-96d2167c6e5c.png)
  
</details>

### Library Binding and Placement
<details>
  <summary>Lecture 1: Netlist binding and initial place design</summary>
 
### Netlist binding and initial place design

* Usually, the combinational logic gate will have its standard shape like AND gate, inverter and etc.
* But, in reality, the combinational logic gate will be converted to the box. The physical gate will be changed to the physical dimension.
* Therefore, all the gates will be removed and changed as in the figure
* Library: the place where we can find all the boxes and it has timing information of the delay of each gate
* Library also can be separated into sub library i.e. the first library consisting of the shape and size while the second library only consists of delay information.
* Library offers several options of library in same cell depending on its timing conditions and its available spaces in the floorplan. The bigger the cell size, the lesser the resistance 
* Hence, we have different flavours of library and we can pick up the desired library based upon the requirements
  
![image](https://user-images.githubusercontent.com/118953917/212942911-f3f8c138-8b65-4be0-917d-d591f6e443ca.png)

* The physical view of logic gates will be placed into the floorplan 
* We need to bind the netlist of the physical cells where the cells will have a real view of a box with a specific width and height
* These boxes will be available in the library, which will be having the width and height of the cells, as well as other details such as delay or required information, as well as the flavor of the cells.
* The arrangements in the floorplan is decided by taking into considerations of the connections of the physical cells i.e. where is the nearest locations between inputs and outputs and etc.
* During placement stage, we must ensure that the area used for the black boxes and decap cells do not have any cells inserted that can cause overlapping. The placement needs to be timing conscious as well to not make the routing long.
  
![image](https://user-images.githubusercontent.com/118953917/212945356-a4f1298a-b3d0-4b57-94b0-5bd0ef70acd1.png)

</details>

<details>
  <summary>Lecture 2:  Optimize placement using estimated wire-length and capacitance</summary>
 
###  Optimize placement using estimated wire-length and capacitance
  
**Optimizing placement**
  
* Optimizing is done by some estimations, let's take Din2 to FF1 in the figure as example. 
* As we can see, the route across Din2 to FF1 would make the data slew (long distance) where higher capacitance makes the amount needed to charge the capacitance becomes high, resulting in worst slew (transition).
* Before routing, we estimate the wire length and capacitance where based on that, the repeaters are inserted.
* In this case, the buffer is added (to lower the capacitance) and will act as repeaters that recondition the signals and making new signals or replicate the signal woth no distortion. However, more repeaters would results in loosing some data. 

![image](https://user-images.githubusercontent.com/118953917/213071175-5785104a-479a-4e24-955f-14a7c9a89c61.png)

</details>

<details>
  <summary>Lecture 3:  Final placement optimization</summary>
 
###  Final placement optimization

* Buffers are added due to its signal transmission length. For example, the length between FF1 and Din4 is to high, so we need the repeaters to recondition the signal and send it to FF1.
* From FF1 to 1, the length is good enough but since we will going across the other FF and buffer, therefore we need to make it on separated layer. 
* From 1 to 2 is a huge gap. Hence, we consider to put the buffer.
* The more the gate and FF closed to each other, the lower delay.
* Moreover, we need to do timing setup checking to see whether our placement acceptable/not as well as identifying the specifications have been met/not.

![image](https://user-images.githubusercontent.com/118953917/213074569-4be5098a-798d-438d-b07a-de873c8d3c1c.png)

</details>

<details>
  <summary>Lecture 4:  Need for libraries and characterization</summary>
 
###  Libraries characterization and modelling

**Part 1: Concepts and theory - NLDM, CCS timing, power and noise characterization**
  
Steps in mcharacterizing and modelling 
  
![image](https://user-images.githubusercontent.com/118953917/213076122-994fd13f-0d90-4e4c-9913-cbaa9ea1e5df.png)

* Common thing across all stages "GATES or Cells"
* Those things in the library must be categorized as library and making sure that the tools will understand what are the gates/cells are 
* To make the tool understands, we have to design, chategorize and model each gate/cell in such a way that the tool understand using EDA tool
  
![image](https://user-images.githubusercontent.com/118953917/213076726-0596bace-b53c-449b-a4b7-20c8dc8a2fac.png)

  
</details>

<details>
  <summary>Lab 1:  Congestion aware placement using RePlAce</summary>
 
###  Congestion aware placement using RePlAce

* Global placement: assigns general locations to movable objects. It used to reduce wire length
* Detailed placement: refines object locations to legal cell sites and enforces non-overlapping constraints 
* The detailed locations enable more accurate estimations of the circuit delay for the purpose of timing optimization
* Legalization is an essential step where the overlaps between gates/macros must be removed

> In openLANE
```
run_placement
```
  
* Half Parameter Wire Length (HPWL) is applied to reduce wire length
  
![image](https://user-images.githubusercontent.com/118953917/213079569-86f77657-1e09-4c97-ba7d-c29b88533f67.png)
  
> In terminal
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/placement
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
  
![image](https://user-images.githubusercontent.com/118953917/213080197-b9144a7c-4ab5-4c3e-bc8c-76165896c4b5.png)

</details>

### Cell design and characterization flows
<details>
  <summary>Lecture 1:  Inputs for cell design flow</summary>
 
###  Inputs for cell design flow
  
* Combinational logics are referred as standard cells and those standard cells will be designed, characterized and modelled in a library
* Library is the place where we keep all the standard cells or any other collaterals
  
![image](https://user-images.githubusercontent.com/118953917/213081403-f3240e5f-44bb-4861-beb6-e1d8dde3e15f.png)

* A library got different functionalities with different sizes and flavours 
* It also contains standard cells with different threshold voltage
  
![image](https://user-images.githubusercontent.com/118953917/213081939-12bcef17-4c98-437d-ba93-dd44d7202990.png)

**Cell design flow**
  
![image](https://user-images.githubusercontent.com/118953917/213101525-135764db-db69-42f9-ab02-a49d2d282666.png)
  
![image](https://user-images.githubusercontent.com/118953917/213084248-7061eaf8-bf49-41e9-bd60-ac8d2601e6e8.png)

</details>

<details>
  <summary>Lecture 2:  Circuit design step</summary>
 
###  Circuit design step

**Cont. Inputs for cell design flow**
  
* Low the drive strength makes it very difficult to drive the huge/long wire
* Drive strength would decides the cell rate while the cell height decides the separation among the power and ground grid
* Library developer will design different flavour of cells based on the supply voltage that is being provided by the top-level as well as taking care of its noise margin 
  
![image](https://user-images.githubusercontent.com/118953917/213095296-0c4638b8-aeeb-43f5-9936-c784db2f222a.png)
  
**Circuit design step**

![image](https://user-images.githubusercontent.com/118953917/213097102-e5c1145c-7fbe-4851-8b07-25170cf06a0b.png)

</details>

<details>
  <summary>Lecture 3:  Layout design step</summary>
 
###  Layout design step

* After getting pmos and nmos network graphy diagram, we need to obtain Euler's path where it is a path that is being traced only once
* Once Euler's path has been obtained, we need to draw a stick diagram of it 
* The drawn stick diagram is then needs to be converted into a proper layout based upon the rules mentioned in pdks and design characterization in previous stages
* The completed layout design will then be inserted into the tool (i.e. magic open source tool) 
* The next step of the design flow is to extract the parasitic (resistance & capacitance of the element) of the layout and characterize them in terms of timing 
* The output of the design would be in terms of GDSII, LEF, and extracted spice netlist
* The final step is we need to characterize the design to get the timing noise, power .libs and its function
  
![image](https://user-images.githubusercontent.com/118953917/213101299-d937018e-178f-4bfc-92b3-de199c3baf55.png)

</details>

<details>
  <summary>Lecture 4:  Typical characterization flow</summary>
 
###  Typical characterization flow

**Steps in characterizing the design**
  
1. Review model file
2. Review extracted SPICE netlist 
3. Define the behavior of the buffers
4. Review sub-circuit of inverters
5. Attach necessary power sources
6. Apply the stimulus
7. Provide necessary output capacitance
8. Provide necessary command (using trans/dc simulations)

* All the steps will be set as one configuration file to a characterization software called GUNA and it will generate the desired timing, noise, power .libs and function 
  
![image](https://user-images.githubusercontent.com/118953917/213107389-c4a98043-adda-44d7-ad9a-7798396dee3c.png)

</details>

### General timing characterization parameters
<details>
  <summary>Lecture 1: Timing threshold definitions</summary>
 
### Timing characterization
	
![image](https://user-images.githubusercontent.com/118953917/213112154-13441ad3-95ca-48d0-b8f2-90150fa96b32.png)
  
* Slew low rise: defines the lowest state (0V) of the power supply which is closer to zero. Typical value is about 20% from bottom power supply. But this is not enough to calculate the slew, we need the slew high rise threshold as well.
* Slew high rise: typical value is about 20% from the top of power supply. To calculate the amount of slew, take the timing difference among those 2 variables
  
![image](https://user-images.githubusercontent.com/118953917/213134921-021a6cf2-dec0-4a7e-867d-31cecbf1ef48.png)

* Similar definition applies for the falling waveform
* We also have thresholds for the delays 
* In rise threshold: refers to the best defined point to calculate the delay.
* Out rise threshold: at 50% mark, if we want to calculate the delay of the cell, we need to take the time period between the 2 points.
* Similarly, for the fall waveform, the definition applies the same as rise waveform but in the form of fall waveform
  
![image](https://user-images.githubusercontent.com/118953917/213123100-b828d238-5216-456a-abf5-34570b8a32c7.png)

</details>

<details>
  <summary>Lecture 2: Propagation delay and transition time</summary>
 
### Propagation delay and transition time

**Propagation delay**
  
* The propagation delay should be a positive value, it should not be a negative value 
* Therefore, the threshold point need to be set properly 
  
![image](https://user-images.githubusercontent.com/118953917/213126123-23f1bc34-6798-4721-b3e6-5dcddcbc998b.png)

* Another example if by chance the threshold point moves, and the output comes before the input, the delay will become a negative value, which should not be seen, and would be a result of poor choice of threshold point.
* Referring to the example below, the wire delay seems to be high for the input, resulting in huge slew (red line). This might be because the two inverters are being placed far apart from each other
* Eventhough the threshold points have been selected properly, it still gives a negative delay, so the design of the circuit is also very important
  
![image](https://user-images.githubusercontent.com/118953917/213128155-72855135-df84-49a6-8c34-26c26604ef8d.png)

**Transition time**
  
![image](https://user-images.githubusercontent.com/118953917/213130139-157ef571-d597-47bd-abae-66ff4739a7dc.png)

  </details>

## Day-17

### Topic: Design and characterise one library cell using Layout tool and spice simulator

### Labs for CMOS inverter ngspice simulations
<details>
  <summary>Lab 1:  IO placer revision</summary>
 
### Continue previous lab session (Day 16)
  
> In terminal
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
vim floorplan.tcl
```
> In openLANE
```
set ::env(FP_IO_MODE) 2
run_floorplan
```
  
![image](https://user-images.githubusercontent.com/118953917/213461720-580d1387-3c86-4491-ab15-2eb11e06c7a3.png)
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/floorplan
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
  
![image](https://user-images.githubusercontent.com/118953917/213464391-330846dc-721c-4027-97c9-3e3632d4b345.png)

</details>

<details>
  <summary>Theory 1:  SPICE deck creation for CMOS inverter</summary>
 
### SPICE deck creation for CMOS inverter
  
**What is SPICE deck?**
  
* Component connectivity
* Defining component values
* Identifying the nodes
* Naming the nodes
  
![image](https://user-images.githubusercontent.com/118953917/213471549-629a7714-ffd7-4440-b422-43a05f5b131a.png)
  
**Writing SPICE deck**
  
![image](https://user-images.githubusercontent.com/118953917/213471621-710c2e2b-e994-43b0-a095-4547f54bfc17.png)

</details>

<details>
  <summary>Theory 2:  SPICE simulation lab for CMOS inverter</summary>
 
### SPICE simulation lab for CMOS inverter
  
![image](https://user-images.githubusercontent.com/118953917/213475389-6c5d85a3-e150-4348-9bd8-9a51b57c3208.png)

![image](https://user-images.githubusercontent.com/118953917/213478263-a4d6c4eb-8289-426e-a046-653c4c728d08.png)
  
![image](https://user-images.githubusercontent.com/118953917/213477736-bb9326c4-96f7-403d-be5c-df0412e91974.png)

**Overview of the model file**
  
![image](https://user-images.githubusercontent.com/118953917/213483508-dfe6602e-9d46-4b16-964b-2d06064a9b6e.png)

**Steps in executing the circuit**
  
1. Change directory to the desired path, source the circuit, and execute the circuit
2. Set the plot and choose plot that is currently presenting in the design (dc1)
3. Display the vectors 
4. Plot the graph and observe the waveform (out vs in)

![image](https://user-images.githubusercontent.com/118953917/213486523-2280c11c-2426-4e06-ac90-303f6b833351.png)

**Output waveform obtained**
  
* Voltage transfer characteristic
* The waveform is kind of shifted towards the left 
  
![image](https://user-images.githubusercontent.com/118953917/213487543-8db2eebc-b3a9-4e46-bd25-683595dcbc7b.png)

**Shifting the value of nmos width and ratio of pmos transistor**
  
* The width of pmos has increased for about 2.5 times
  
![image](https://user-images.githubusercontent.com/118953917/213490254-cf4ee7d1-996f-466c-abe6-0feab9f451f1.png)

**Generated output waveform**
  
* The output is now has been centred
  
![image](https://user-images.githubusercontent.com/118953917/213490384-71909e03-0399-45d7-833e-10d79eb7f7e1.png)

</details>

<details>
  <summary>Theory 3:  Switching Threshold Vm</summary>
 
### Switching Threshold Vm
  
**Comparison of the output waveforms with switching voltages**
  
**Static behaviour evaluation**
  
* CMOS is a robust design, where the shape of both waveforms are the same eventhough they have different sizes
* Referring to the output waveform shown below, the graph on the RHS is not shifted when the voltage shifting is applied due to the pmos width which is larger than the design on the LHS where the widths of nmos and pmos are the same
* This happened is because the cmos circuit constructed is more robust
* One of the parameters that defines the cmos inverter robustness is the switching threshold, Vm, which is the voltage when Vin = Vout
  
![image](https://user-images.githubusercontent.com/118953917/213602461-40136fc9-f951-45a8-8164-9107a541aeaa.png)

* At interception, pmos and nmos are in saturation region (power ON)
* There is high possibility of having leakage current (power to ground)
* When the vin = vout, gate voltage = drain voltage, so the vgs will be very little compared to the threshold voltage
* At the point where vgs = vds, the currens idsn and idsp will be the same, but it's just flowing in the opposite directions

![image](https://user-images.githubusercontent.com/118953917/213603451-2c206e94-81c4-43c9-a4f7-e5a759c4b7c5.png)

</details>

<details>
  <summary>Theory 4:  Static and dynamic simulation of CMOS inverter</summary>
 
### Static and dynamic simulation of CMOS inverter
  
* Dynamic simulations usually being used to analyse the rise and fall delay as well as verifying how it varies with the switching threshold
* To construct a dynamic simulation, pulse wave is inserted as an input and the simulation command will be a transient analysis
  
![image](https://user-images.githubusercontent.com/118953917/213609513-3b328a27-183d-4aaa-afec-2b2d73905252.png)

**Setting the pulse wave and transient analysis**
  
![image](https://user-images.githubusercontent.com/118953917/213609592-d3faea15-b0cf-4317-890f-e1a7a6088700.png)

* The rise delay calculation is based on the 50% point, the difference in time between when the falling input crosses 50% and the point where rising output crosses 50%
* Vice versa for the fall delay calculation
  
![image](https://user-images.githubusercontent.com/118953917/213609830-9eeebf73-6172-4e3c-9fcd-487897930636.png)

![image](https://user-images.githubusercontent.com/118953917/213609852-06ebcda9-f143-4e29-a6bb-63a537b15e19.png)

![image](https://user-images.githubusercontent.com/118953917/213609871-28bd45bc-ba18-497b-afdc-6da319163b01.png)

</details>

<details>
  <summary>Lab 2:  Lab steps to git clone vsdstdcelldesign</summary>
 
### Lab steps to git clone vsdstdcelldesign

```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
cd vsdstdcelldesign/
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir$ cd pdks/sky130A/libs.tech/magic/
cp sky130A.tech /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
magic -T sky130A.tech sky130_inv.mag
```
  
![image](https://user-images.githubusercontent.com/118953917/213611879-6ee86bc8-385a-47aa-9dd3-c964043f2bcc.png)

</details>

### Inception of Layout & CMOS fabrication process
<details>
  <summary>Theory 1:  Create Active regions</summary>
 
### Create Active regions
  
**16-mask CMOS process**
  
1. Selecting a substrate
2. Creating active region for transistors
3. N-well and P-well formation
4. Formation of gate
5. Lightly doped drain (LDD) formation
6. Source and drain formation
7. Local interconnect formation
8. Higher level metal formation
  
**Selecting a substrate**
  
* Doping: the process of adding impurities to intrinsic semiconductors to alter their properties
* Common type of substrate is P-type substrate and it is always be used in smartphone, and etc.
* The doping level is used to fabricate nmos and pmos as well as it will be maintaining low 
  
![image](https://user-images.githubusercontent.com/118953917/213614279-acf4cd99-123b-45de-9b82-55ee21ebe551.png)

**Creating active region for transistors**
  
* Creating active region of transistors by creating pockets
  
1. Create isolation between each pocket in insulator (by growing the silicon dioxide)
2. Add in/deposit a layer of silicon nitrate onto a silicon dioxide
3. Define the region to create the pocket by depositing a layer of photoresist (film to do the process that will define all the regions)
4. Photoresist process will create a mask in fabrication and masking process will take place, where photoresist process will protect the layout from the chemical reaction if UV light is disposed
5. The exposed region which is not getting protected from the photoresist will be washed out 
  
![image](https://user-images.githubusercontent.com/118953917/213616666-7260dcbe-2125-4fde-9e3a-cb17adb0a3d2.png)

6. Mask is then removed and if there is chemical reaction or any kind of deposition/etching process, only the exposed region will be affected
7. Silicon nitrate will be etched, only the area of underneath the protection layer will be protected while the remaining area will be etched off 

![image](https://user-images.githubusercontent.com/118953917/213619651-496b1f88-1ee2-4bd9-982c-325342d002e0.png)
  
8. Photoresist will be removed since the silicon nitrate will act as a protection layer to grow the oxides of the other area
9. Place the cell into a completely oxidation furnace (containing a very high temperature) to grow the oxides of the other layers 
* From the figure, the protection layer protects the underneath region to grow while it helps the exposed region to grow in the oxidation furnace
10. The exposed region has grown while the protected layer remain the same
  * Grown process is called LOCOS (Local Oxidation of Silicon)
  * Grown area is called as Bird's beak
  
![image](https://user-images.githubusercontent.com/118953917/213619681-a1b89a85-85c9-4b06-b48a-c307d3346fc5.png)
  
11. Etched out/remove the Silicon nitrate using phosphoric acid
  * This is how we get the isolation region and the ways in protecting those two different transistors from communicating to each other 
  
![image](https://user-images.githubusercontent.com/118953917/213619715-bfedb329-5afb-4527-a0c0-092872825bb4.png)

</details>

<details>
  <summary>Theory 2:  Formation of N-well and P-well</summary>
 
### Formation of N-well and P-well
  
**N-well and P-well formation steps**
  
* N-well will be used for pmos application while P-well will be used for nmos application
* We need to protect one area while fabricating the other area
  
1. Deposit a layer of photoresist and define which layer should we protect
  * Use Mask2 to protect the desired area while we fabricating the other area
  
![image](https://user-images.githubusercontent.com/118953917/213631953-0a866e31-c03b-4a0d-bc9c-ceb91742ef31.png)
  
**Overview of Mask 2 (Top view)**
  
![image](https://user-images.githubusercontent.com/118953917/213631914-97ed5958-4bc0-4393-8a21-a5a53b76d286.png)

2. The photoresist will be exposed by the UV light, in which only the exposed area will be reacted by the UV light while the protected area would remain the same and did not react to the UV light
3. The exposed area will then be washed out from the substrate
  
![image](https://user-images.githubusercontent.com/118953917/213633496-b1bfc5ca-1ea7-443d-a8b8-33cd3e4bf1cd.png)

4. The mask is then be removed and create a p-well by adding Boron (p-type material) and it will be diffused in the substrate through the oxide layer
  * This process is using ion implantation process with a very high energy of around 200keV
  * High energy is needed, so that Boron can pass through the substrate
  * This will produce P-well 
  
![image](https://user-images.githubusercontent.com/118953917/213635240-c5ae2dde-75ba-42c0-add6-ea60e8b7ea73.png)

* The formation of N-well will undergoing the same process as P-well, but N-well uses Phosphorus (n-type material) to implant/diffuse inside the substrate with around 400keV
* Energy used in Phosphorus is quite high since Phosphorus is heavier than Boron
* After all the steps are done, N-well and P-well have been formed

![image](https://user-images.githubusercontent.com/118953917/213637152-6a4cb8fc-217f-4b0f-8234-5e5d442c3775.png)

5. Once the complete N-well and P-well have been formed, we need to diffuse the well so that it will occupies at least the half of the substrate area. Therefore, we have a clear room available for the pmos and nmos fabrication.
6. Place the complete substrate with N-well and P-well into a high temperature furnace (Driving furnace) for about 100°C for 4-6 hours
  * That will form a drive in/diffuse Boron and Phosphorus into the substrate, forming a clear well
  * N-well creates pmos transistor while P-well creates nmos transistor
  
* Explaination above refers to the ways on creating the pockets as mentioned in the previous session
  
![image](https://user-images.githubusercontent.com/118953917/213650065-57864b9b-ac52-4849-bc9c-83bc6da3f789.png)

</details>

<details>
  <summary>Theory 3:  Formation of gate terminal</summary>
 
### Formation of gate terminal
  
* Formation of gate terminal is quite important since it will control the threshold voltage as well as turning on voltage for transistors

**Quick refreshing on Circuit design and SPICE simulation**
  
* Fabrication is closely related to threshold voltage in which threshold voltage would decides the internal voltage of the gate, as well as deciding the functions of the gate
  
![image](https://user-images.githubusercontent.com/118953917/213654491-7b5181cb-ffd6-47d8-ab71-d1c5ba2d75d4.png)

**Formation of gate terminal steps**
  
1. Control and maintain the doping concentrations of the substrate by adding Mask4 
2. The rest of the process is still the same as discussed before. Hence, it will be repeated steps for the rest of the process.
  * Doping process using Boron with low energy required which is only around 60eV where it is not high enough since we only need the surface 
  * Similar process needs to be done fro pmos too
  
![image](https://user-images.githubusercontent.com/118953917/213704270-986aa838-8a7c-4d58-929d-ba8efa764a1d.png)

3. Add Mask5 on P-well and repeat the same steps for pmos. We also need to control the threshold voltage of pmos and undergo the rest of the process for pmos
4. Arsenic/Phosphorus can be used in diffusing into the substrate with maintaining the low energy 
  
![image](https://user-images.githubusercontent.com/118953917/213706127-010c6cc9-687d-4e86-bbea-1092aea41b19.png)

5. Fix the oxide since there is a lot of damages from implantation process. Fixing process can be undergo by removing the oxide using hydrofluoric (HF) acid
  * Once we fixed that, the oxide will re-grown and giving a high quality oxide to the substrate
6. Deposit a polysilicon layer using deposition technique and it will grow a thick polysilicon where the gate area is supposed to have a low resistance
7. Since the gate has a low resistance, we need to dope it with some more impurities i.e. Phosphorus & Arsenic and diffuse it on a complete polysilicon layer to have a low sheet resistance, as well as low gate resistance
8. Use Mask6 as a gate of polysilicon mask 
  
![image](https://user-images.githubusercontent.com/118953917/213713052-5491a8d7-9385-4fda-b7ff-780df015fcef.png)
  
**Top view of Mask6**
  
![image](https://user-images.githubusercontent.com/118953917/213713554-091b184e-3a83-4c7a-86e7-7db2c7af790d.png)

9. Remove Mask6 and the remaining areas of the polysilicon which is outside of the photoresist can be etched out of it
10. Polysilicon gate is now formed
  
![image](https://user-images.githubusercontent.com/118953917/213714902-42fc4015-c534-436e-a4be-dcc2b189f679.png)
  
11. Remove the photoresist and gate has been formed
  
![image](https://user-images.githubusercontent.com/118953917/213715020-4cda3c87-8341-42dd-be25-35c9b79c5db4.png)

</details>

<details>
  <summary>Theory 4:  Lightly doped drain (LDD) formation</summary>
 
### Lightly doped drain (LDD) formation
  
**Why theere are two dopping profiles?**

* Hot electron effect
  + Electric field, E=V/d
  + High energy carriers will break Si-Si bonds (more electron and hole -> cannot control doping profile well)
  + Crosses 3.2eV barrier between Si conduction band SiO2 conduction band, it will enter oxide layer and may causing a liberty issue
  
* Short channel effect
  + For short channels, drain field will penetrates channel (making the gate difficults to control the current- source and drain)
  
**Ways to generate LDD structure**
  
1. Based on the created gate from the previous session, the step started by adding Mask7 to protect the desired area and the rest steps of photolithography is remain the same 
2. However, to fabricate the nmos at P-well, we need to do the ion implantation process by doping it with Phosphorus (N-type material) 
  * N- -> lightly doped channel is formed
  
![image](https://user-images.githubusercontent.com/118953917/213725083-cd59e33f-ebce-4b90-9e1c-6fdc30af7adf.png)

3. Creating Mask8 and repeat the rest of the steps 
4. Ion implantation takes place in the next process by doping Boron 
5. Create some spaces around gate to protect further source and drain formation
  
![image](https://user-images.githubusercontent.com/118953917/213726675-d2af85ef-22c8-4712-b01f-2768556b914a.png)

6. Undergo plasma anisotropic etching 
  * The etching will create a side-wall spacers (green colour at both LHS & RHS of the gate in the figure)

![image](https://user-images.githubusercontent.com/118953917/213728268-5c93239c-ead4-42b3-83f9-68139b844841.png)

</details> 

<details>
  <summary>Theory 5:  Source and drain formation</summary>
 
### Source and drain formation

1. Add a thin layer of screen oxide to avoid channel link entering the substrate 
2. Add Mask9 and repeat the same steps of photolithography 
3. Expose the structure with Arsenic with 75keV amount of energy 
  * It will obtain N+ N- P
  
![image](https://user-images.githubusercontent.com/118953917/213731093-b1c96fd3-34dd-4301-b7bc-294b720cb732.png)

* Do the same way as pmos as well
4. Add Mask10 and do the process og photolithography 
5. Do ion implantation process using Boron with 50oeV of energy 
  * It will obtain P+ P- N
6. Place into high temperature furnace to penetrate more into N-well and P-well and the process will do the high temperature annealing
  * Source for pmos and nmos are now obtained

![image](https://user-images.githubusercontent.com/118953917/213733511-9497f7ad-9979-480b-9962-8ffaab50609c.png)

</details>

<details>
  <summary>Theory 6: Local interconnect formation</summary>
 
###  Local interconnect formation
  
* Accessible for the user to control electrical characteristics for pmos and nmos
  
1. Remove the thin screen oxide to open up for drain, source and gate region for building contact 
2. Etch the thin oxide in Hydrofluoric solution
3. Deposit Titanium/wafer surface using sputtering
  * Titanium: a metal with low resistivity
4. Create a contact between Titanium that has been deposited by heating the wafer in Nitrogen ambient
5. From the heating process, it formed a low resistance Titanium Silicon dioxide that can be used for local interconnect while Titanium nitrate is used for local communication
  
![image](https://user-images.githubusercontent.com/118953917/213915682-8bf1f3fc-5b16-475c-aaf0-26b61d8d37a8.png)

6. Add Mask11 and repeat the same lithography process 
7. Remove Mask11 and etch extra Titanium nitrate for RCA cleaning 
8. Local Titanium nitrate interconnects were used to contact locally and bring up to top
  
![image](https://user-images.githubusercontent.com/118953917/213916144-672834dc-c60d-49c1-bed3-9317ad6ddc7a.png)

</details>

<details>
  <summary>Theory 7: Higher level metal formation</summary>
 
###  Higher level metal formation
  
1. The surface topography is not suitable for metal contact since it is non-linear
2. To fix that, thick layer of silicon dioxide with doped phosphorus/boron will be deposited 
  * Phosphorus will act as a barrier protection against mobile sodium ion while boron will reduce the temperature and polish the surface and get a flat surface
3. Add Mask12 and repeat the same lithography process

![image](https://user-images.githubusercontent.com/118953917/213916572-41abc40a-3153-41e9-8774-adceee0d1bb2.png)

4. Remove the mask and etch off the silicon dioxide 
5. Remove the photoresist and deposit a thin layer of titanium nitrate
  * Why titanium nitrate? -> because it is a good layer for silicon dioxide and a good layer for bottom interconnect and top interconnect
6. Deposit a blanket tungsten layer
  * Add in another layer because it gives good contact from bottom to the top
  
![image](https://user-images.githubusercontent.com/118953917/213917335-7f889b82-7541-46bf-ae04-a03c812d0173.png)

7. Polish again 
8. Add Aluminium to allow contact hole to contact higher metal layer
9. Add Mask13 and do the same lithography process
10. Etch off the mask and plasma etch the aluminium
  
![image](https://user-images.githubusercontent.com/118953917/213917709-fb3548eb-1325-4482-8543-b02fb187d669.png)
  
11. Remove photoresist 
  
![image](https://user-images.githubusercontent.com/118953917/213917838-9ac5a89b-c5d6-4657-a631-a8405e196756.png)

12. Deposit silicon dioxide and polish again
13. Add Mask14 and repeat the same process
14. Deposit titanium nitrate that acts as barrier
15. Deposit tungsten to make the contacts 
  
![image](https://user-images.githubusercontent.com/118953917/213918111-fcf303f1-7c39-43c2-bbb3-d06acc452fe0.png)

16. Add Mask15 as 3rd level interconnect using Aluminium (more thicker)
17. Give protection layer for the chip
18. Add Mask16 to contact outside of the chip
19. Complete 16-mask cmos process 
  
![image](https://user-images.githubusercontent.com/118953917/213918441-0e32ff34-85eb-4df1-9683-e01aa4d0efd7.png)
  
</details>

<details>
  <summary>Lab 1: Lab introduction to Sky130 basic layers layout and LEF using inverter</summary>
 
###  Lab introduction to Sky130 basic layers layout and LEF using inverter

![image](https://user-images.githubusercontent.com/118953917/213921975-ed37be3f-fffa-435b-a2f9-529c8c6f92d2.png)

![image](https://user-images.githubusercontent.com/118953917/213922647-2445aa12-00d4-490e-a4c7-e96bde258219.png)

![image](https://user-images.githubusercontent.com/118953917/213922670-c4ebe92b-ef71-4f11-a75b-9f3a0e6b4e86.png)

* press "s" three times to check connection

Checking the connection
  
![image](https://user-images.githubusercontent.com/118953917/213923053-a281f38b-a8b9-45c6-8283-20ebacc0db87.png)

* LEF only have metal layer, no information on logic path, only provide information on boundary/cell/length to place a cell
  + Cell LEF: an abstract view of the cell and only gives information about PR boundary, pin position and metal layer information of the cell
  
*Note: more infromation on LEF, visit https://github.com/nickson-jose/vsdstdcelldesign#introduction-to-lef*
  
</details>

<details>
  <summary>Lab 2: Lab steps to create std cell layout and extract spice netlist</summary>
 
###  Lab steps to create std cell layout and extract spice netlist
  
**Checking the error**
  
* Click DRC tab -> DRC find next error
* Read the information regarding the violations through tkcon
* To fix the violations, select the area (left click right click) and click the layer on the right
* Ensure the final design needs to be DRC clean
  
![image](https://user-images.githubusercontent.com/118953917/213925286-6cd67f3d-a251-4fba-9da1-785f3a84942f.png)

> In tkcon
```
pwd
extract all                       (To extract inverter)
ext2spice cthresh 0 rthresh 0     (To extract parasitic capacitance)
ext2spice
```

![image](https://user-images.githubusercontent.com/118953917/213925997-ec0229b0-19e2-41f2-86e2-7b7b966c4aa9.png)
  
```
vim sky130_inv.spice
```
  
![image](https://user-images.githubusercontent.com/118953917/213926022-015a6979-c65f-48ee-8326-146e02030af0.png)

</details>

### Design library cell using Magic Layout and ngspice characterization
<details>
  <summary>Lab 1:  Lab steps to create final SPICE deck using Sky130 tech</summary>
 
### Lab steps to create final SPICE deck using Sky130 tech
  
**Overview of sky130_inv.spice**
  
```
vim sky130_inv.spice
```
  
![image](https://user-images.githubusercontent.com/118953917/214469225-6ec475a4-e994-4463-ae1a-f7c7e15aae37.png)

**Size of the grid**
  
![image](https://user-images.githubusercontent.com/118953917/214473875-0df13534-2784-4194-845b-5b72987a2d63.png)
  
**Checking lib file for nmos and pmos**
  
![image](https://user-images.githubusercontent.com/118953917/214470609-3dda5fba-504a-452f-8f97-f6753594db1f.png)

**Modifying sky130_inv.spice**
  
```
vim sky130_inv.spice
```
  
* Modify the scale to reflect the value in the magic tool

![image](https://user-images.githubusercontent.com/118953917/214473341-ee03f6ae-f326-4d10-b7f2-e32d16649621.png)

</details>

<details>
  <summary>Lab 2:  Lab steps to characterize inverter using sky130 model files</summary>
 
### Lab steps to characterize inverter using sky130 model files

```
ngspice sky130_inv.spice
```
  
![image](https://user-images.githubusercontent.com/118953917/214475263-899099d1-a534-4a74-9a34-1c90bfd96ba0.png)

```
plot y vs time a
```
  
![image](https://user-images.githubusercontent.com/118953917/214477246-bceefee3-dfdc-4cdb-95b1-0d1b31f76c9d.png)

To characterize cell -> Find value of 4 parameters

* Rise transition: time taken for the output waveform to rise from 20% of max value to 80% of max value Vdd
* Fall transition: time taken for output to fall from 80% to 20%
* Cell rise/fall delay/propagation delay: the propagation delay where the output is rising/falling (50%)

**Rise transition output (take the red line)**
  
* From 20% to 80%
  
![image](https://user-images.githubusercontent.com/118953917/214482429-13890da8-34f9-40a9-bca7-fc4b1e3bb7d1.png)
  
**Fall transition input (take the blue line)**
  
![image](https://user-images.githubusercontent.com/118953917/214482452-3aa42a2d-1bff-4c94-946f-a9d8531ecd93.png)

**Cell delay (propagation delay)**
  
**Rise delay**
  
![image](https://user-images.githubusercontent.com/118953917/214484564-1097bca0-0975-434e-8657-ff44c0b2751b.png)

**Fall delay**
  
![image](https://user-images.githubusercontent.com/118953917/214484610-1604f444-4d7c-4c9f-bad3-a5eb191193cb.png)

</details>

<details>
  <summary>Lab 3:  Lab introduction to Magic tool options and DRC rules</summary>
 
### Lab introduction to Magic tool options and DRC rules

* Visit http://opencircuitdesign.com/ to explore more about open circuit design
* Browse through http://opencircuitdesign.com/magic/index.html and http://opencircuitdesign.com/magic/tutorials/tut9.html for some tutorial on Magic/Tech files/DRC

**Introduction to Magic**
  
* An interactive system for creating and modifying VLSI circuit layout
* Magic has built-in knowledge of layout rules, i.e. while editing, it can continuously checking for some rule violations
* Magic also knows about connectivity and transistors, as well as containing a built-in hierarchical circuit extractor
  
**Introduction to DRC**
  
* Verifying whether a specific design meets the constraints imposed by the process technology to be used for its manufacturing or not
* Example of DRCs:
  + Minimum width and spacing for metal
  + Minimum area
  + Different net spacing
  + Short violation
  + Less than min edge length
  
</details>

<details>
  <summary>Lab 4:  Lab introduction to Sky130 pdk's and steps to download labs</summary>
 
### Lab introduction to Sky130 pdk's and steps to download labs
  
```
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz             (To import magic layout into the tool)
tar xfz drc_tests.tgz                                                         (To extract the file)
cd tar xfz drc_tests.tgz
ls
cat .magicrc                                                                  (To find tech file)
```
  
![image](https://user-images.githubusercontent.com/118953917/214498051-f4340afb-45ab-4cd3-9319-240ba6bb4b5e.png)

**Start-up script for Magic**
  
![image](https://user-images.githubusercontent.com/118953917/214498209-fba5a2b2-d34b-4ce0-ae85-53aebdb503f6.png)

> To start magic
```
pwd             (Ensure we are in ~/Desktop/work/tools/drc_tests directory)
magic -d XR     (To get a better graphic)
```
  
![image](https://user-images.githubusercontent.com/118953917/214498854-c7b3bed9-ba52-45c9-ae0e-f2fb450c7874.png)

> Select file --> open --> met3.mag
  
![image](https://user-images.githubusercontent.com/118953917/214499548-b49046aa-73be-4d49-b724-866978304776.png)

*Note: select any object, press ";" to auto switch to another terminal*
  
> In tkcon
```
drc why             (To check the violations on selected object)
```
  
![image](https://user-images.githubusercontent.com/118953917/214501193-a6c4752c-5730-48d9-8acf-b09ebb90ef18.png)

</details>

<details>
  <summary>Lab 5:  Lab introduction to Magic and steps to load Sky130 tech-rules</summary>
 
### Lab introduction to Magic and steps to load Sky130 tech-rules

* Visit https://skywater-pdk.readthedocs.io/en/main/ and https://github.com/google/skywater-pdk for SkyWater Open Source PDK documentation
* Browse through https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html#denmos for details on periphery rules

![image](https://user-images.githubusercontent.com/118953917/214503187-7aa9be1b-643b-42d4-879a-d37728791b64.png)

*Note: select any area, click scroller of the mouse, and select m3contact using scroller*
  
> In tkcon
```
cif see VIA2      (To create VIA within m3contact)
what
feed clear        (To clear and undo)
snap int
```

![image](https://user-images.githubusercontent.com/118953917/214507834-889807e7-39be-4341-b3ca-bec8a5e2a54f.png)

![image](https://user-images.githubusercontent.com/118953917/214507872-9f97f68a-9e78-4439-ac3b-1e25d0763521.png)

</details>

<details>
  <summary>Lab 6:  Lab exercise to fix poly.9 error in Sky130 tech-file</summary>
 
### Lab exercise to fix poly.9 error in Sky130 tech-file
  
> In tkcon
```
load poly
```
  
![image](https://user-images.githubusercontent.com/118953917/214509581-30186a61-139e-4f74-bc3d-6c0bcba8af43.png)
  
![image](https://user-images.githubusercontent.com/118953917/214510207-9a3bf47f-aa09-4a21-b77d-30b6208cb590.png)

```
cd ~/Desktop/work/tools/drc_tests
vim sky130A.tech
```
  
![image](https://user-images.githubusercontent.com/118953917/214511507-ef0ca711-a538-4a32-9f40-3904905fe40d.png)

**Modifying sky130A.tech**
  
* Adding in allpolynonfet
  
![image](https://user-images.githubusercontent.com/118953917/214514790-6d5515c9-d81c-487b-87eb-f815cb05d4fb.png)

> In tkcon
```
tech load sky130A.tech              (To reload tech file)
drc check                           (To do drc checking)
drc why                             
```
  
* The spacing for poly has been resolved
* However, further action for diffusion and tap need to take into consideration
  
![image](https://user-images.githubusercontent.com/118953917/214516083-dfdc79e0-1829-4875-8293-52f73835b5d4.png)

</details>

<details>
  <summary>Lab 7:   Lab exercise to implement poly resistor spacing to diff and tap</summary>
 
###  Lab exercise to implement poly resistor spacing to diff and tap
  
* Copy the resistor to two since there are several types of diffusion and tap

*Note: green --> ndiffusion ; brown --> pdiffusion*
  
![image](https://user-images.githubusercontent.com/118953917/214576976-cfa1bea4-4e73-415e-bfa5-b7afa335be7e.png)

**Modifying the tech file**
  
```
vim sky130A.tech
```
  
![image](https://user-images.githubusercontent.com/118953917/214579764-c47980a5-65b6-478c-b835-c0ec78e4f2e5.png)
  
  
</details>

<details>
  <summary>Lab 8: Lab challenge exercise to describe DRC error as geometrical construct</summary>
 
###  Lab challenge exercise to describe DRC error as geometrical construct
  
```
vim sky130A.tech
```
  
![image](https://user-images.githubusercontent.com/118953917/214581933-eabbf7ce-abf3-4013-a01a-d5edc5891073.png)

> In tkcon
```
load nwell.mag
```
  
* Look through nwell.6
* Deep nwell yellow stripes and nwell green dot pattern
* The point of the rule is the edge of the dnwell needs to be covered with overlap all the way around by a ring of regular n-well 
* The outside distance rule could be implemented by a simple surround of drc rule, but the inside distance cannot be captured with a simple edge type rule
  
![image](https://user-images.githubusercontent.com/118953917/214584329-1bf76471-dd0e-4abd-a8a4-f3e4615aacfd.png)
  
![image](https://user-images.githubusercontent.com/118953917/214585491-1222bf99-67b1-4c2e-9c3b-b78e09e5910c.png)

> In tkcon
```
cif ostyle drc              (Can only see layers for the cif layer style that is selected for the output)
cif see dnwell_shrink       (To see the selected area)
cif see nwell_missing       (Shows the area which gets flagged with the error)
```

![image](https://user-images.githubusercontent.com/118953917/214587247-f24d5af5-ce00-4948-aa1a-43c1a42f69ec.png)

</details>

<details>
  <summary>Lab 9: Lab challenge to find missing or incorrect rules and fix them</summary>
 
###  Lab challenge to find missing or incorrect rules and fix them
  
![image](https://user-images.githubusercontent.com/118953917/214597510-69ce0860-40a8-4a0d-9d7d-0d8c38a3b23e.png)
  
**Modifying tech file**
  
```
vim sky130A.tech
```
  
![image](https://user-images.githubusercontent.com/118953917/214593633-ebb38d26-013a-4caa-b1ee-5f56afdc75a9.png)

> In tkcon
```
tech load sky130A.tech             
drc check                          
drc style drc(full)
drc check
```
  
* still have error so copy the nwell and place the nsubstratencontact (blue x box) and the error goes away
  
![image](https://user-images.githubusercontent.com/118953917/214597158-bbf44c32-8789-464a-8594-080637b58950.png)
  
</details>

## Day-18

### Topic: Pre-layout timing analysis and importance of good clock tree

### Timing modelling using delay tables
<details>
  <summary>Lab 1:  Lab steps to convert grid info to track info</summary>
 
### Lab steps to convert grid info to track info
  
**Library Exchange Format (LEF)**
  
* A specification in which representing the physical layout of an integrated circuit in an ASCII format
* It includes design rules and abstract information about the standard cells
* LEF only has basic information required at that level to serve the purpose of the concerned CAD tool
* Containing information on input, output, power and group port, does not consists logic path information
  
* Objective: extract LEF file from .mag file and then plug the file into the picorv32a flow (previous is standard cell library)
* Main guidelines:
  + The input and output ports must lie on the intersection of the vertical and horizontal tracks
  + The width of standard cell should be on the track pitch, and the height should be on the track vertical pitch
  
```
~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd
vim tracks.info
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
magic -T sky130A.tech sky130_inv.mag
```
  
* Track information (using during routing stage) routes can go over the track/layer (metal traces)
  
![image](https://user-images.githubusercontent.com/118953917/214740911-da449828-590d-499e-8e84-5dbe2c0ac156.png)
  
* Set the grid based on the tracks.info (grid) converted the track into grid
  
![image](https://user-images.githubusercontent.com/118953917/214740963-2d493469-4489-4ba8-9ef9-7ee97563f49b.png)

* Ports are on the intersection of the horizontal and vertical tracks. It ensures that the routes can reach the ports from x and y direction.
* Verified that both input and output ports have fulfilled the guideline where input and output ports lies at the intersection of horizontal and vertical tracks

*Note: press "g" to enable grid (zoom in to see the grid)*
  
![image](https://user-images.githubusercontent.com/118953917/214741494-d1a5f5e6-5295-45ff-ba2e-ad8eac2fe210.png)

</details>

<details>
  <summary>Lab 2:  Lab steps to convert magic layout to std cell LEF</summary>
 
### Lab steps to convert magic layout to std cell LEF
  
* We need to only define layers, not ports in layout
* Ports definitions are required when we want to extract LEF file
  + Ports will be defined as pins of a macro
  
**How to define ports?**

* Select port --> edit --> Text --> fill those required information 
  
*Note: For A; and Y in locali while for VPWR and VGND in metal1*

![image](https://user-images.githubusercontent.com/118953917/214749913-cb884945-e9a5-4c44-b10c-8cb3983560ed.png)
  
* Then, define classes of ports 
  
![image](https://user-images.githubusercontent.com/118953917/214756209-3b67c804-59ed-42a8-83f3-eb585339b834.png)
  
* Extract the LEF file 
  
> In tkcon 
```
save sky130A_vsdinv.mag
```
  
> Checking the saved file
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
ls
```
  
![image](https://user-images.githubusercontent.com/118953917/214787867-9cf85de0-99f3-4db2-89fd-eec1c064ed29.png)
  
```
magic -T sky130A.tech sky130_vsdinv.mag
```

> In tkcon
```
lef write
```
  
![image](https://user-images.githubusercontent.com/118953917/214751397-07e1287d-a91d-49b5-b624-25878e3759c0.png)

```
vim sky130_vsdinv.lef
```
  
![image](https://user-images.githubusercontent.com/118953917/214756411-087a7a3c-a8f0-4f55-86f4-9453d1feb89f.png)

</details>

<details>
  <summary>Lab 3:  Introduction to timing libs and steps to include new cell in synthesis</summary>
 
### Introduction to timing libs and steps to include new cell in synthesis
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
cp sky130A_vsdinv.lef /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/libs
cp sky130_fd_sc_hd__* /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/
vim config.tcl
```
  
**Modifying config.tcl file**
  
![image](https://user-images.githubusercontent.com/118953917/214758920-88489361-6f99-4a0f-8e41-ffa089a16269.png)

```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
make mount
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 13-01_14-09 -overwrite      (Check run date at ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
run_synthesis
```
  
Successfully invoke openlane and doing synthesis
  
![image](https://user-images.githubusercontent.com/118953917/214760516-fc95cafa-9f17-4f92-8803-9819361bf9a0.png)

</details>

<details>
  <summary>Theory 1:  Introduction to delay tables</summary>
 
### Introduction to delay tables

* With the use of gates for clock nets, such as shown in the below figure, which is the method known as clock gating, we can ensure no dynamic switching and short circuit power consumed by the clock tree, during the time the clock gets gated.

![image](https://user-images.githubusercontent.com/118953917/214761577-5e776c52-2f13-4e4d-ba3a-b35145638a68.png)

* We need to look into the timing characteristics of the buffer, in the case where we want to swap out the buffer for a gate. 
* For each level of buffering, we should have an identical buffer being used, and each node should be driving the same node. 
* Keep in mind that the load at the output will be varying, and since the load of one buffer is varying, the input transition of the following buffer will also vary. 
* This means that we will have a variety of delays.
  
![image](https://user-images.githubusercontent.com/118953917/214762059-d8079e4f-ab52-48e5-9250-98041e883c2d.png)
  
* The delay table is characterized based on varying the input transition and output load of a cell, against the delay of that cell. 
* Each cell will have its own delay table for different sizes and threshold tables.

![image](https://user-images.githubusercontent.com/118953917/214762237-10ec6a51-a825-4ebf-baf4-52bb7ff85339.png)

</details>

<details>
  <summary>Theory 2:  Delay table usage</summary>
 
### Delay table usage
  
* Each type of cell will be having its own individual delay table, as the internal pmos and nmos width/length ratio gets varied, the resistance changes, then RC constant gets varied as well, meaning the delay of each cell gets varied. 
* The values of delay which are not available in the table are extrapolated based on the given data.
  
![image](https://user-images.githubusercontent.com/118953917/214764494-ef258ff7-6660-4281-85ff-5f8a2652140d.png)

* Similarly, the ways on how we have a delay table, we will also have a characterization table for input transition.
* The latency at the endpoints will be the sum of the delays of each individual cell in that path. 
* The total skew value between two endpoints will be non-zero if the output load driven for a cell is varied, meaning different delay numbers are seen between endpoints, this is why it is preferred to have the nodes at each level driving the same load. 
* Another case in which we can retain the skew to be zero in the presence of varied load, is by using a different buffer size at the same level that can achieve the same level of delay as the other buffer in same level based on its delay table.
* These are factors which should be looked into in the early stages of the clock tree design stage. 
* Now we must look into power aware CTS, where we have to consider endpoints which are only active under certain conditions. 
* In this case, we do not need to propagate the clock into those cells during the period of inactivity.

![image](https://user-images.githubusercontent.com/118953917/214765256-2979c5c0-b2a9-41ab-b311-9e3cfb33a076.png)

</details>

<details>
  <summary>Lab 4: Lab steps to configure synthesis settings to fix slack and include vsdinv</summary>
 
### Lab steps to configure synthesis settings to fix slack and include vsdinv
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
  
* SYNTH_STRATEGY: control the area and timing
* SYNTH_BUFFERING: control if we want to buffer high fanout net 
* SYNTH_SIZING: control in cell sizing instead of buffering
* SYNTH_DRIVING_CELL: ensure more drive strength cell to drive input
  
![image](https://user-images.githubusercontent.com/118953917/214776677-df33d5a9-66c2-4778-ab7e-b3ea83a6fad6.png)

> In openlane terminal
```
echo $::env(SYNTH_STRATEGY)
set ::env(SYNTH_STRATEGY) "DELAY 0"
echo $::env(SYNTH_STRATEGY)
echo $::env(SYNTH_BUFFERING)
echo $::env(SYNTH_SIZING)
set ::env(SYNTH_SIZING) 1
echo $::env(SYNTH_SIZING)
echo $::env(SYNTH_DRIVING_CELL)
```
  
*Note: refer https://github.com/AngeloJacobo/OpenLANE-Sky130-Physical-Design-Workshop#lab-part-3-day-4---fix-negative-slack for the details*
  
* With SYNTH_STRATEGY of Delay 0, the tool will focus more on optimizing/minimizing the delay, index can be 0 to 3 where 3 is the most optimized for timing (sacrificing more area). 
* SYNTH_BUFFERING of 1 ensures cell buffer will be used on high fanout cells to reduce delay due to high capacitance load. 
* SYNTH_SIZING of 1 will enable cell sizing where cell will be upsize or downsized as needed to meet timing. 
* SYNTH_DRIVING_CELL is the cell used to drive the input ports and is vital for cells with a lot of fan-outs since it needs higher drive strength (larger driving cell needed).
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
rm -rf picorv32a.synthesis.v
```
 
> In openlane terminal
```
run_synthesis
```
  
![image](https://user-images.githubusercontent.com/118953917/214780525-3aa279d5-169d-444a-aefa-c5ff52cad77f.png)

> In openlane 
```
run_floorplan
```

![image](https://user-images.githubusercontent.com/118953917/214782752-dc620279-42e7-4d0c-ae61-7c9572e0e6c0.png)
  
* The solution for this error is found. 
* basic_macro_placement command is failing since EXTRA_LEFS variable inside config.tcl is assumed as a macro which is not. 
* The temporary solution is to comment call on basic_macro_placement inside the OpenLane/scripts/tcl_commands/floorplan.tcl (this is okay since we are not adding any macro to the design).

* After that run_placement, another error will occur relating to remove_buffers, the solution is to comment the call to remove_buffers_from_nets in OpenLane/scripts/tcl_commands/placement.tcl. 
* After successfully running placement, runs/[date]/results/placement/picorv32.def will be created.
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/openroad
vim or_basic_mp.tcl
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands
vim floorplan.tcl
```
  
**Modification in gvim**
  
![image](https://user-images.githubusercontent.com/118953917/214784124-bd01cb53-8308-4b02-8c5e-469da27d04b5.png)

> In openlane
```
run_floorplan
run_placement
```
  
> In terminal
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/placement
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def
```

![image](https://user-images.githubusercontent.com/118953917/214790612-456f38a4-6cca-4353-a68a-c5135632a6a9.png)

</details>

### Timing analysis with ideal clocks using openSTA
<details>
  <summary>Theory 1: Setup timing analysis and introduction to flip-flop setup time</summary>
 
### Setup timing analysis and introduction to flip-flop setup time
  
* At the zero time stamp, there is one clock edge that reaches the launch flop. 
* At T time stamp, the second rising edge reaches the capture flop. Any analysis that needs to be done is between 0 and T. For the combinational circuit to work, the combinational delay needs to be less than the period, T.

![image](https://user-images.githubusercontent.com/118953917/214792086-fb20df82-8122-48da-8694-a780b6d8d977.png)

* Looking at more practical scenarios and how the flop works, there will be a delay within the internal flop circuitry, between mux 1 and mux 2. 
* These internal delays will restrict the combinational delay requirements.
* This internal delay is known as the setup time, and this setup time needs to be subtracted away from the complete clock period T. 
* Now the capture flop has enough time for it to compute the data within the flop and ensure the data is ready at Q by the time the second rise edge of clock reach.
  
![image](https://user-images.githubusercontent.com/118953917/214792585-bb290730-1517-41ed-98ff-46ef6c88df66.png)

</details>

<details>
  <summary>Theory 2: Introduction to clock jitter and uncertainty</summary>
 
### Introduction to clock jitter and uncertainty
  
**Jitter**
  
* Deviation of a clock edge from its ideal location
* Typically caused by clock generator circuitry, noise, power supply variations, interference from nearby circuitry etc. Jitter is a contributing factor to the design margin specified for timing closure
  
* The next practical scenario to take into consideration is jitter. 
* The clock is expected to reach the clock pin at exactly 0s or at Ts, but in real scenarios, the clock signal may not be able to reach at the exact moment, as the clock source generation may have its own built-in variation. 
* This is known as jitter, the temporary variation of the clock period. 
* The combinational delay will become more stringent as a result. Thus we change our combinational delay to factor in the uncertainty factor from the jitter.
  
![image](https://user-images.githubusercontent.com/118953917/214793401-a1382eea-22d8-4374-ae33-0bd2d36d76c2.png)

* The combinational delay of a path will look as shown above.
* The next challenge comes in performing timing analysis with multiple ideal clocks.
  
![image](https://user-images.githubusercontent.com/118953917/214900663-256785e1-7607-443d-9d9d-6715a6de46b4.png) 
	
</details>

<details>
  <summary>Lab 1: Lab steps to configure OpenSTA for post-synth timing analysis</summary>
 
### Lab steps to configure OpenSTA for post-synth timing analysis
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
vim pre_sta.conf                                          (For pre-layout timing analysis)
```
  
![image](https://user-images.githubusercontent.com/118953917/214798003-4d475ac5-16ca-4bfc-8f62-73e4642a4a27.png)

```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
vim my_base.sdc
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/libs
vim sky130_fd_sc_hd__typical.lib
```
  
![image](https://user-images.githubusercontent.com/118953917/214800764-3a700389-9330-4ac7-b43e-6dab567eaa91.png)
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
```

![image](https://user-images.githubusercontent.com/118953917/214802161-4bcb8008-5413-47af-b401-ec2ac29a9b8e.png)

</details>

<details>
  <summary>Lab 2: Lab steps to optimize synthesis to reduce setup violations</summary>
 
### Lab steps to optimize synthesis to reduce setup violations
  
![image](https://user-images.githubusercontent.com/118953917/214803801-892a4879-34ea-4753-ab7e-c76dc102c622.png)

```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
  
![image](https://user-images.githubusercontent.com/118953917/214804887-e1a8a2e7-fd97-4bdf-acd2-dd09fbd2f31b.png)
  
> In openlane
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
echo $::env(SYNTH_MAX_FANOUT)
set ::env(SYNTH_MAX_FANOUT) 4
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
rm -rf picorv32a.synthesis.v
```

> In openlane
```
run_synthesis
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
report_net -connections _18242_                           
replace_cell _41952_ sky130_fd_sc_hd__dfxtp_4             (Pick the highest fanout, cap, slew and replace the worst violations of the cell by increasing drive strength --> upsize cell from 2 to 4)
report_checks -fields {net cap dlew input pins} -digits 4
report_tns
report_wns
```

![image](https://user-images.githubusercontent.com/118953917/214859399-c9b6b58f-0584-4c04-a174-ae59bcab8cbc.png)
  
![image](https://user-images.githubusercontent.com/118953917/214857863-aac7b3eb-65c4-4582-8cd7-65b96a2b1c46.png)

</details>

<details>
  <summary>Lab 3: Lab steps to do basic timing ECO</summary>
 
### Lab steps to do basic timing ECO
  
```
report_checks -from _41952_ -through _41879_
```

![image](https://user-images.githubusercontent.com/118953917/214876198-94a45f68-c0ba-49cd-b69f-397ed034a604.png)
  
</details>

### Clock tree synthesis TritonCTS and signal integrity
<details>
  <summary>Theory 1:  Clock tree routing and buffering using H-Tree algorithm</summary>
 
### Clock tree routing and buffering using H-Tree algorithm
  
* Clock tree synthesis is done to propagate the clock signals to all the clock pins in the design.
* However, a good clock tree needs to be designed to take into account the skew between the clock pins due to long routing.
* Through the use of H-tree, which is a smarter implementation for a clock tree design, that is designed based on the distances between the clock pins in the design between the clock port. 
* This is to give a skew value as close to 0 as possible by having the clock signals reach all the cells at the same time.
  
![image](https://user-images.githubusercontent.com/118953917/214889414-ef867688-41ee-4fce-b9ba-53c150a740f6.png)

* The next step is to perform clock tree buffering. 
* The wires for the clock routes each will have resistances and huge number of capacitances, and with the long routing, there will be signal integrity issues.
* Thus, to maintain the signal integrity, we need buffering on these nets.
  
![image](https://user-images.githubusercontent.com/118953917/214899578-e074127a-75d3-4f4f-80c1-89001cd57860.png)
	
</details>

<details>
  <summary>Theory 2:  Crosstalk and clock net shielding</summary>
 
### Crosstalk and clock net shielding
  
* Another topic to understand before moving to using real clocks is clock net shielding. 
* Clock nets are the critical nets in the design, we build the clock tree to ensure there is a minimum skew. 
* However, if there is any cross talk that happens and affect the clock signals, that will affect the design very badly. 
* By shielding, we are protecting the clock nets from the outside world, avoiding glitches and delta delays from occurring. 
* If a glitch occurs on the clock net, incorrect data in the memory will cause inaccurate functionality for the design. 
* The shield can be connected to ground or to Vdd, as long as there is no switching activity occurring. 
* Critical data nets are also necessary to be shielded.
  
![image](https://user-images.githubusercontent.com/118953917/214894595-17db203b-7643-4333-800c-578284702548.png)  
  
</details>

<details>
  <summary>Lab 1: Lab steps to run CTS using TritonCTS</summary>
 
### Lab steps to run CTS using TritonCTS
  
> In sta terminal
```
write_verilog ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis.v
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
ls -lrt picorv32a.synthesis.v
date
```
  
![image](https://user-images.githubusercontent.com/118953917/214867050-6e2e1327-2021-4170-a662-2d7de1940ef4.png)

> In openlane
```
run_floorplan
run_placement
run_cts
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
  
![image](https://user-images.githubusercontent.com/118953917/214873411-922a5676-c00a-4d34-98d2-395b3118ee7f.png)
  
</details>

<details>
  <summary>Lab 2: Lab steps to verify CTS runs</summary>
 
### Lab steps to verify CTS runs
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands
vim cts.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/214878521-602486db-c598-459f-8784-92ccae05609c.png)

* Each stage has its own .tcl file, except synthesis since it is not in openroad

```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/openroad
vim or_cts.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/214880364-358aa10a-deb0-4f48-b44b-e8aebf74942b.png)

> In openlane
```
echo $::env(LIB_TYPICAL)
echo $::env(CURRENT_DEF)
echo $::env(CTS_MAX_CAP)
echo $::env(CTS_CLK_BUFFER_LIST)
echo $::env(CTS_ROOT_BUFFER)
```
  
![image](https://user-images.githubusercontent.com/118953917/214886956-73377f5a-213e-403a-a3e5-6ef4934996c4.png)
  
</details>

### Timing analysis with real clocks using openSTA
<details>
  <summary>Theory 1: Setup timing analysis using real clocks</summary>
 
### Setup timing analysis using real clocks
  
* After buffer has been added in, more clock network delay has been introduced and it will combining all the delays.
* With real clocks, we will need to have buffers inserted into the clock path to ensure the clock signal integrity. 
* Because of the buffer introduction, the clock edge will reach the clock pin with consideration to the delays of the buffers inserted. 
* The clock network delay will also need to take into consideration the delays from the buffers inserted. 
* The window will become shifted as a result of the delays from the buffers inserted. 
* The skew for this design will now be the difference between the deltas, and the equation for setup timing analysis will also changed based on the image shown. 
* If the data arrival time is higher than the data required time, then we will have negative slack on the path, meaning we have violations.
  
![image](https://user-images.githubusercontent.com/118953917/214993881-dec5a151-4e8b-4212-b8ba-64f1a8eca181.png)

* For hold timing analysis, where the capture edge is on the o clock rise edge, the combinational delay should be greater than the hold time of the flop.
* Hold time refers to the second mux delay, which is the time required for the data to be sent after the clock edge within the flop. 
* So the data needs to be arrived after the hold time, so the new data can be captured into the flop, after existing data is launched out.
  
![image](https://user-images.githubusercontent.com/118953917/214994634-1d64f057-197d-45f4-b7b0-65494f8cb69d.png)

</details>

<details>
  <summary>Theory 2: Hold timing analysis using real clocks</summary>
 
### Hold timing analysis using real clocks
  
* Introducing more real factors into our design for hold analysis will yield the below equation for hold timing. 
* Jitter for the launch clock and capture flop will not need to be taken into consideration as the design is on the 0 clock edge, and the arrival difference for the capture and launch flop will be the same.
* So, the uncertainty should be kept low for the hold analysis. 
* The slack formula will be --> data arrival time – data required time
* If data required time is higher, we will have negative slack, meaning the timing path for hold will be violated.
  
![image](https://user-images.githubusercontent.com/118953917/214995292-07ac14b8-171d-4058-9440-ff23b2804206.png)

* For the timing path setup for real clocks, we need to take into considerations the deltas that were mentioned earlier.
* For delta1, will be launch clock network delay, while delta2, will be capture clock network delay. 
* The equations for setup time and hold time are shown below.
  
![image](https://user-images.githubusercontent.com/118953917/214995599-ba697707-5ed4-463a-8ba0-0deecc7594b3.png)

</details>

<details>
  <summary>Lab 1: Lab steps to analyze timing with real clocks using OpenSTA</summary>
 
### Lab steps to analyze timing with real clocks using OpenSTA
  
*Note: Refer https://github.com/AngeloJacobo/OpenLANE-Sky130-Physical-Design-Workshop#timing-analysis-with-real-clocks*
  
> In openlane
```
openroad                                                                                                       (Invoking openroad)
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts.db
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty -max $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
set_propagated_clock [all_clocks]
read_sdc designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -format full_clock_expanded -digits 4
```

* This step is not practical, therefore it violated.
  
![image](https://user-images.githubusercontent.com/118953917/215005919-ddd073ff-17b8-4fc5-80d8-a7d2f676c794.png)

![image](https://user-images.githubusercontent.com/118953917/215007150-7985c511-e27e-4bbd-bd35-1739d6667df2.png)

</details>

<details>
  <summary>Lab 2: Lab steps to execute OpenSTA with right timing libraries and CTS assignment</summary>
 
### Lab steps to execute OpenSTA with right timing libraries and CTS assignment
  
> Continuing from previous lab
```
exit        (Exit openroad)
openroad
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
echo $::env(CTS_CLK_BUFFER_LIST)                              (To see the list of buffers)
```
  
* Both timing are already met after post CTS
* The tool picked small cell first to meet the skew and area
  + skew values are within 10% of the max clock period
  
![image](https://user-images.githubusercontent.com/118953917/215010210-b7f01f8d-f0ff-4bc6-ae4d-9bdbcdc3df86.png)

![image](https://user-images.githubusercontent.com/118953917/215010920-912b1639-6412-4db4-a7dc-8a75afbb3d9f.png)

![image](https://user-images.githubusercontent.com/118953917/215011382-00bfd9c5-05cf-4a1d-b14d-c49d2b726ce8.png)

</details>

<details>
  <summary>Lab 3: Lab steps to observe impact of bigger CTS buffers on setup and hold timing</summary>
 
### Lab steps to observe impact of bigger CTS buffers on setup and hold timing
 
> In openlane
```
exit 
echo $::env(CTS_CLK_BUFFER_LIST)
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]
echo $::env(CURRENT_DEF)
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/placement/picorv32a.placement.def
run_cts
```
  
![image](https://user-images.githubusercontent.com/118953917/215015517-cf77adc1-ce17-4311-986d-50b0b068c66b.png)
  
```
openroad
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts1.db
read_db pico_cts1.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
```

![image](https://user-images.githubusercontent.com/118953917/215015562-f0c63e6c-f266-4ec6-9b05-df091dd05c73.png)

![image](https://user-images.githubusercontent.com/118953917/215016452-7329a6e2-d21b-40d7-8c80-a7f873f1a7cb.png)

```
report_clock_skew -hold
report_clock_skew -setup
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]      (Adding back clkbuf1)
```
  
![image](https://user-images.githubusercontent.com/118953917/215017120-1d9a05f8-f29b-4019-9f4d-34cc5b271d89.png)

</details>

## Day-19

### Topic: Final steps for RTL2GDS

### Routing and design rule check (DRC)
<details>
  <summary>Theory 1: Introduction to Maze Routing using Lee's algorithm</summary>
 
### Introduction to Maze Routing using Lee's algorithm
  
**Routing stage**
  
* **Maze Routing-Lee’s Algorithm [Lee 1961]**: Algorithm to find the shortest path between two nodes in a grid

* Routing: the process of creating the physical wire connections within the design in which it helps in determining the best way of routing that can be done between two endpoints, the source, and the target, with the shortest distance as well as the least number of zig-zag turns.

* However, the algorithm needs to be aware of any blockages set that hinders any routing to be done in the particular area.
  
![image](https://user-images.githubusercontent.com/118953917/215030291-ceea2ccd-d922-4883-8370-97a39a423721.png)

**Steps in Lee's Algorithm**
  
1. Create the routing grid behind the floorplan
  
2. The two points were created which are the source and target
  * Algorithm will look for the best route to connect the two points with the help of the routing grid
  
3. The tool will label the grid ground (adjacent of horizontal and vertical grid)
  * However, it did not label the grid under the blockage and at the boundary
  
![image](https://user-images.githubusercontent.com/118953917/215032150-34401e02-d2db-4d5c-a437-3ca369b4cdec.png)

</details>

<details>
  <summary>Theory 2: Lee's Algorithm conclusion</summary>
 
### Lee's Algorithm conclusion
  
* It is preferable to choose the LHS instead of RHS of the figure below
* It is because the chosen route in the LHS figure got the best route which is less bending (L-shaped) rather than the RHS figure
* Therefore, LHS figure will proceed to do the global routing

* Performing the routing for 1 route will be fairly simple, but when we have millions of start and endpoints to route between, this method will consume a lot of time and memory
* Maze routing consumes more time and memory if the design is huge
* There are some algorithms that can help to reduce the time and memory consumption such as line-search algorithm, stanner-tree algorithm
  
![image](https://user-images.githubusercontent.com/118953917/215033857-8446f957-7d5d-4378-accf-81f824cfbdd9.png)

</details>

<details>
  <summary>Theory 3: Design Rule Check</summary>
 
### Design Rule Check
  
* Design Rule Check (DRC): the rules that should be followed whenever the routing of the design is performed.
  
* One of the rules may be the minimal wire width, where the width of the wire should be no less than a specified amount based on the limitations of the fabrication process. 
  
* Another rule that is based on the fabrication process of lithography is the wire pitch, where the centre-to-centre distance between 2 wires should be no smaller than a certain distance. 
  
* Another rule includes wire spacing rule, where distance between 2 wires should be no smaller than a certain distance. 
  
* These are many rules that the tool needs to take into account when performing the routing of the design.
  
![image](https://user-images.githubusercontent.com/118953917/215035532-aaae220b-4b3d-446c-8eed-5b697367212c.png)

* One type of DRC violation is a signal short, where two wires that are not intended to be connected becomes in contact on the same layer.
  
* This could lead to functional failure, so this needs to be taken care of.
  
* To fix this, we need to simply moving one of the wires onto a different metal layer.
  
* However, please keep in mind that there are new drc rules that need to be taken into account.

![image](https://user-images.githubusercontent.com/118953917/215036320-f0517b39-378a-4a40-9f0f-eb735c2001b4.png)

**New drc rules after fixing**
  
* **Via width** where the width of the via should be no less than a certain value. 

* **Via spacing** where the distance between 2 vias cannot be less than a specific distance. 
  
* Most of these DRC rules come from the lithographic process and the limitations that come with the technology.
  
![image](https://user-images.githubusercontent.com/118953917/215036993-58407624-384b-4965-a9b1-0519dc5a5670.png)

* Performing parasitic extraction, where the resistances and capacitances of the wires are extracted and will be used for further processes.
  
![image](https://user-images.githubusercontent.com/118953917/215037259-747e6a52-c7cd-4a01-ab20-209179aef4fe.png)

</details>

### Power Distribution Network and routing
<details>
  <summary>Lab 1: Lab steps to build power distribution network</summary>
 
### Lab steps to build power distribution network
  
> If exited from openlane
```
cd work/tools/openlane_working_dir/openlane
make mount
pwd
ls -ltr
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 13-01_14-09
```
  
*Note: If we want to retain the configurations from the last openlane job, we need to use ```prep -design -tag```. If we want to create a fresh run with new configurations but without changing the tag name, we need to use ```prep -design -tag -overwrite```.*


> In openlane
```
echo $::env(CURRENT_DEF)    (Ensure current_def is on the CTS stage)
gen_pdn                     (To generate power distribution network)
```
  
* Error encountered during “gen_pdn” in which the stage cannot perform routing as current_def has not changed to floorplan.pdn
  
![image](https://user-images.githubusercontent.com/118953917/215052338-090fb2b0-91d4-4069-aec0-4c72264fe319.png)

</details>

<details>
  <summary>Lab 2: Lab steps from power straps to std cell power</summary>
 
### Lab steps from power straps to std cell power
  
* This is just a review on PDN
  
* If the power and ground rails has a pitch of 2.72, thus the customized inverter cell will have a height of 2.72 or else the power and ground rails will not be able to power up the cell. 
* As shown below, power and ground flows from power/ground pads --> power/ground ring --> power/ground straps --> power/ground rails.
  
*Source: https://github.com/AngeloJacobo/OpenLANE-Sky130-Physical-Design-Workshop#timing-analysis-with-real-clocks*
  
![image](https://user-images.githubusercontent.com/118953917/215058376-777e3768-0d83-4b71-9d07-1594bdda4e2b.png)

</details>

<details>
  <summary>Lab 3: Basics of global and detail routing and configure TritonRoute</summary>
 
### Basics of global and detail routing and configure TritonRoute
  
```
echo $::env(CURRENT_DEF)            (Ensure the def file of pdn has been created)
echo $::env(ROUTING_STRATEGY)
run_routing
```
  
```
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```

* Assuming power distribution network has been successfully generated without being encountered by any error
  
![image](https://user-images.githubusercontent.com/118953917/215117743-5048a812-29a0-42cb-9863-a8c497402b80.png)
  
</details> 

### TritonRoute Features
<details>
  <summary>Theory 1: TritonRoute feature 1 - Honors pre-processed route guides</summary>
 
### TritonRoute feature 1 - Honors pre-processed route guides
  
* OpenLane routing stage consists of two stages:
  + **Global Routing**: Form routing guides that can route all the nets. The tool used is FastRoute.
  + **Detailed Routing**: Uses the global routing's guide to connect the pins with the least amount of wire and bends. The tool used is TritonRoute.

**Triton Route**
  
* In fast routing, a rough routing draft is created. 
  
* Fast routing is the engine which is used for global routing. 
  
* During global routing, the region is divided into grid cells, which acts as a route guide for the TritonRoute to be used for the detail routing, where an algorithm is used to find the best connectivity between the points.

* It honours the preprocessed route guides (obtained after fast routes), wherein the tool attempts as much as possible to route within route guides. 
  
* The tool assumes route guides for each net satisfies inter-guide connectivity. 
  
* Triton route works on proposed MILP (Mixed integer liner programming) based panel routing scheme with intra-layer parallel and inter-layer sequential routing framework, to finds the best way to perform the routing.
  
* Intra-layer refers to the routing within a layer, while inter-layer routing refers to routing between layers, through the uses of vias.
  
![image](https://user-images.githubusercontent.com/118953917/215102497-8e9c6337-56b7-47b4-a098-8cdd9ba1fe75.png)

</details>

<details>
  <summary>Theory 2: TritonRoute Feature 2 & 3 - Inter-guide connectivity and intra- & inter-layer routing</summary>
 
### TritonRoute Feature 2 & 3 - Inter-guide connectivity and intra- & inter-layer routing
  
* Preprocessed guides should have unit width and must be in the preferred direction of the layer. 
  
* Global route is done by fast route, and the output would be the routing guide. 
  
* The initial route guides are transformed into the preprocessed guides through splitting, merging, and bridging. 
  
* Whenever the tool detected the route guide with non-preferred direction, it divides the route guide into unit widths, and then the route with preferred direction is merged, while the non-preferred direction route is bridged to be a route on another layer, which is the preferred direction for routing. 
  
* This way, parallel routing with higher layers are avoided, as well as avoiding parallel plate capacitance.
  
![image](https://user-images.githubusercontent.com/118953917/215103703-a8f8b000-0aa2-4edc-b386-b5dd65ff421d.png)

* Each layer or panel will have its own preferred routing direction assigned to it, in which the routes should be formed. 
  
* Routing in higher layers will begin only once the routing the bottom layers have been completed.

* Two guides are connected if they are on the same metal layer with touching edges, or if they are on neighbouring metal layers with a non-zero vertically overlapped area.
  
![image](https://user-images.githubusercontent.com/118953917/215104070-3025a21a-61ca-441e-855a-0ebcda219df0.png)

* Each unconnected terminal i.e. pin of a standard cell instance, should have its pin shape overlapped by a route guide. 
  
* The purple box in the RHS figure below would be the routing guide on the metal 1 layer that would overlap with the unconnected terminal.

![image](https://user-images.githubusercontent.com/118953917/215105174-cb8ca1d4-96ae-4d19-8106-25ed5480d734.png)

</details>

<details>
  <summary>Theory 3: TritonRoute method to handle connectivity</summary>
 
### TritonRoute method to handle connectivity
  
* Inputs file needed for TritonRoute are the LEF file, DEF file, and the Preprocessed route guides.

* Outputs from the TritonRoute would be a detailed routing solution with optimized wire-length and via count.

* Constraints needed in TritonRoute are the route guide honouring, connectivity constraints and design rules.
  
**TritonRoute method**
  
* TritonRoute handles connectivity through 2 ways
  + Access Point (AP)
  + Access Point Cluster (APC)
  
* **Access point**: on-grid point on the metal layer of the route guide, and is used to connect to lower-layer segments, upper-layer segments, pins or IO ports. 
  
* **Access Point Cluster**: a union of all Access Points derived from the same lower-layer segment, upper-layer guide, a pin or an IO port. 
  
* Access point refers to the point where the via can be placed to allow connectivity between layers. 
  
* The objective of the Mixed Integer Liner Programming (MILP) is to connect one access point to another optimally. 
  1. Choose one of the access points where the via should be dropped
  2. Determining how the first access point will be connected to the next access point.

![image](https://user-images.githubusercontent.com/118953917/215107218-454cb310-8936-43c7-90ed-695569d3fef8.png)

</details>

<details>
  <summary>Lab 1: Routing topology algorithm and final files list post-route</summary>
 
### Routing topology algorithm and final files list post-route
  
**Optimization algorithm for routing topology**
  
* For each APC, the algorithm needs to find the cost associated with the distance between 2 APCs which are the minimum spanning tree, MST, between the APCs and the costs. 
  
* The objective of the algorithm
  1. To find the minimal and most optimal point between the 2 APCs.
  
![image](https://user-images.githubusercontent.com/118953917/215117524-620c7049-f13d-4a3c-80b0-3d650d7ca0b7.png)

* There are 3 violations as shown in the figure below

* TritonRoute strategy = 0 is chosen right now
  
* If TritonRoute strategy = 14 is chosen, the violations might be 0 but it might take some time to finish running
  
* Therefore, we need to fix the violations manually
  
![image](https://user-images.githubusercontent.com/118953917/215118656-b1f2df2a-c34c-4b9d-aa57-1cb22a4f9b9a.png)
  
* Referring to the below figure, there are 3 violations on li1 layer that needs to fix manually

![image](https://user-images.githubusercontent.com/118953917/215119749-96387581-8583-496b-9330-fafa6972ac76.png)

* Creating a new spef file that requires merged.lef and picorv32a.def

![image](https://user-images.githubusercontent.com/118953917/215129767-a7fa598b-a2c3-4c20-9f58-a967493567aa.png)
	
</details>

## Day-20

### Topic: Floorplanning and power planning labs

<details>
  <summary>Theory</summary>
 
### Physical Design Flow
  
* Refers to a fundamental process of converting synthesized netlist design restriction and standard library to a layout as per the design rules provided by the foundary. The layout is sent to the foundary for the chip creation.
  
* It is an algorithm with definite objectives, some of them consist of wire length, minimum area, and power optimization.
  
* Steps in the Physical Design Flow are divided into several main processes. 
  
* Firstly, partitioning, where it divides a circuit into smaller sub-circuits or modules, each of which can be constructed and examined separately.
  
* Chip planning may consists of floorplanning and power planning process.
  
* Floorplanning determines the dimensions of all the blocks and place them in appropriate spots on the chip.  
  
* Another step is power planning, which distributes power (VDD) and ground (GND) nets throughout the chip, and is commonly associated with floorplanning.  
  
* Placement is the process of determining the geographic placements of all cells within a block.  
  
* Clock network/tree synthesis establishes how the clock signal is buffered, gated and routed to fulfil specified skew and latency criteria. 
  
* The next step would be signal/global routing which allocates routing resources that are used for connections. Within the global routing resources, detailed routing assigns routes to individual metal layers and routing tracks. 
  
* Lastly, timing closure is used for unique placement or routing strategies to improve circuit performance.
  
*Source: https://chipedge.com/steps-in-vlsi-physical-design-flow/#:~:text=VLSI%20Physical%20Design%20Flow%20is,the%20creation%20of%20the%20chip.*
  
*Source: slide material provided for Day 20 of training*
  
![image](https://user-images.githubusercontent.com/118953917/215411723-547f98c2-d8ac-446c-92b2-19e020ed9f1c.png)
  

**Main steps in Physical Design Flow**
  
* Create a gate-level netlist (after synthesis)
  1. The netlist is the result of the synthesis process and it is the foundation for physical design. 
  2. Synthesis translates RTL designs written in VHDL or Verilog HDL into gate-level specifications that can be understood by the next set of tools. 
  3. The cells employed, their interconnections, the area used, and other parameters are all listed in this netlist.
  
* Floorplanning
  1. Under this step, we calculate the dimensions of all the blocks and place them in appropriate spots on the chip. 
  2. This step is performed to keep the blocks that are highly connected close to one another. 
  
* Partitioning
  1. The next step of partitioning helps in dividing the chip into separate chunks. 
  2. This procedure is performed primarily to distinguish between distinct functional blocks and to facilitate placement and routing. When the design engineer separates the overall design into sub-blocks and then proceeds to design each module during the RTL design phase, this is known as partitioning. 
  
* Placement
  1. Placement is the process of placing the standard cells inside the core boundary in an optimal location. 
  2. The tool tries to place the standard cell in such a way that the design should have minimal congestions and the best timing. 
  3. Every PnR tool provides various commands/switches so that users can optimize the design in a better way in terms of timing, congestion, area, and power as per their requirements. 
  4. Based on the preferences set by the user, the tool tray to place and optimize it for better QoR. 
  5. Placement does not place only the standard cells present in the synthesized netlist but also places many physical only cells and adds buffers/inverters as per the requirement to meet the timings, DRV, and foundry requirements. 
  6. Here are the basic steps which the tool performs during the placement and optimization stage. 
  
* Static Time Analysis  
  1. Static timing analysis (STA) is a method of validating the timing performance of a design by checking all possible paths for timing violations. 
  2. STA breaks a design down into timing paths, calculates the signal propagation delay along each path, and checks for violations of timing constraints inside the design and at the input/output interface. 
  3. Another way to perform timing analysis is to use dynamic simulation, which determines the full behaviour of the circuit for a given set of input stimulus vectors. 
  4. Compared to dynamic simulation, static timing analysis is much faster because it is not necessary to simulate the logical operation of the circuit. 
  5. STA is also more thorough because it checks all timing paths, not just the logical conditions that are sensitized by a set of test vectors. 
  6. However, STA can only check the timing, not the functionality, of a circuit design.
  
* Clock Tree Synthesis (CTS)  
  1. Clock Tree Synthesis(CTS) is one of the crucial steps in VLSI physical design flow. 
  2. It is used to reduce skew and insertion delay. 
  3. This step helps distribute the clock evenly among all sequential elements of a design.
  
* Routing  
  1. Routing helps in making the links between the cells and the blocks. 
  2. There are two types of routing: global routing and detailed routing. 
  3. Connections are routed through global routing, which assigns routing resources. 
  4. It also keeps track of a network’s assignment. 
  5. Whereas, the actual connections are made by detailed routing. 
  
* Physical verification 
  1. Physical verification ensures that the produced layout design is valid. 
  2. This involves ensuring that the layout is correct and includes all technological prerequisites, density verification, cleaning density etc.  
  
*Source: slide material provided for Day 20 of training*
  
![image](https://user-images.githubusercontent.com/118953917/215418212-f6a6c325-c64d-43c9-8628-ef15c05ae168.png)
  
</details>

<details>
  <summary>Lab</summary>
 
### Physical Design Flow
  
Sources
  1. https://github.com/Devipriya1921/VSDBabySoC_ICC2#getting-started-with-vsdbabysoc

  
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20
git clone https://github.com/manili/VSDBabySoC.git
git clone https://github.com/Devipriya1921/VSDBabySoC_ICC2.git
git clone https://github.com/bharath19-gs/synopsys_ICC2flow_130nm.git
git clone https://github.com/kunalg123/icc2_workshop_collaterals.git
git clone https://github.com/google/skywater-pdk-libs-sky130_fd_sc_hd.git
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```
  
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files
gvim vsdbabysoc.tcl &
gvim avsdpll.lib &
```
  
**vsdbabysoc.tcl**
  
* Modifying the contents to my path, remove -lib in read_lib commands, and replace MYCLK to clk since the clock used in the design is {clk}
* All of the commands have been inserted in gvim and the tool will run it once at a time
  
![image](https://user-images.githubusercontent.com/118953917/215930668-24e8267c-5265-4406-9c33-b39c6227e8bc.png)
  
**avsdpll.lib**
  
* Remove the unwanted pins 
  
![image](https://user-images.githubusercontent.com/118953917/215930725-1f1c96f4-b71b-4fe3-824b-26259c964e5c.png)
  
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell
/p/hdk/bin/cth_psetup -p ipde/rc -cfg 76p31_r08hp71_ipg.cth -ward . -tool ipde_all -quiet -x '$SETUP_IPDE -b ip76p31ddrgen6mod_ddriolvrpgcombo' 
dc_shell
source /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/vsdbabysoc.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/215796297-d6e947f8-be20-4265-ae4a-4b27677cf596.png)

![image](https://user-images.githubusercontent.com/118953917/215796409-4f6e8041-365d-4515-8579-df04c14fa8ff.png)
  
**Reports**
  
**Report area**
  
![image](https://user-images.githubusercontent.com/118953917/215930931-9978ad14-a2f7-4b64-b995-abb653450e34.png)
  
**Report power**

![image](https://user-images.githubusercontent.com/118953917/215930965-ebf8d41f-3169-45f3-929c-83dbef4c7c58.png)
  
**Report timing**

![image](https://user-images.githubusercontent.com/118953917/215931015-297d3787-2f87-418c-97d0-a487abc579be.png)
  
**Report constraints**

![image](https://user-images.githubusercontent.com/118953917/215931057-fcb52a51-7403-4826-b3d4-139b27337cbd.png)
  
### Output schematic
  
![image](https://user-images.githubusercontent.com/118953917/215931319-503a58df-8829-46aa-bd6c-1a472bb0171a.png)
  
**RVMYTH core**
  
![image](https://user-images.githubusercontent.com/118953917/215931465-2f9ae8f5-93f5-47b3-8eef-b450b5992a3d.png)
![image](https://user-images.githubusercontent.com/118953917/215931636-d06c40be-90cc-4970-9bf7-91ff75e03066.png)

### Performing physical design 
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/top.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/icc2_common_setup.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/icc2_dp_setup.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/init_design.read_parasitic_tech_example.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/init_design.mcmm_example.auto_expanded.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/pns_example.tcl
```
  
**Modifying files**
  
**top.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444467-1a0d3e0b-e1b6-41ae-a798-e22174bd48dc.png)
  
**icc2_common_setup.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444586-51960b86-aa08-4423-871d-425cc5095c59.png)
  
**icc2_dp_setup.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444639-a9ba7e73-7e04-43a8-bcb1-2be6afa0f382.png)
  
**init_design.read_parasitic_tech_example.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444705-4a05dc7e-2c6f-468e-a75f-fd8ed3137841.png)
  
**init_design.mcmm_example.auto_expanded.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444754-f035b43a-796f-4bfa-b2b9-8b66d45acf35.png)
  
**pns_example.tcl**
  
![image](https://user-images.githubusercontent.com/118953917/217444856-7f1901ce-e404-4bc7-8ae7-aa6d971c7051.png)

**Output Layout**
  
> Invoking icc2_shell
```
cd /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell
/p/hdk/pu_tu/prd/sams/mig76_wlw/setup/enter_p31 -cfg ip76p31r08hp7rev03 -ov ./
icc2_shell
source /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/top.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/217445180-7f455991-e9fb-4d05-a2a1-8a698d652e4f.png)
  
![image](https://user-images.githubusercontent.com/118953917/217445236-1b20ecdd-fc43-4bc2-81af-a0610b9136a1.png)
![image](https://user-images.githubusercontent.com/118953917/217445278-f91ea81e-7111-4ad9-b58b-531efd60a7fc.png)
![image](https://user-images.githubusercontent.com/118953917/217461202-5efeff6b-1bbe-4231-ba40-d0598fd76208.png)


> In icc2_shell
```
set_propagated_clock [all_clocks]             (Converting clock object from ideal clock to propagated clock)
report_timing
estimate_timing
report_constraints -all_violators -nosplit -verbose -significant_digits 4 > /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/violators.rpt
```

![image](https://user-images.githubusercontent.com/118953917/217459536-d2b6a0b9-d6b7-4340-b2b3-9df250cba357.png)
  
* estimate_timing report could not be generated since there is no estimate timing rules detected on nets
  
![image](https://user-images.githubusercontent.com/118953917/217459611-95571078-02a6-4dba-a8ba-7154a18f183f.png)
  
**violators.rpt**
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files/violators.rpt	     (Reviewing violations report within the design)
```

![image](https://user-images.githubusercontent.com/118953917/217480198-b0ed756b-8c72-4969-b95c-480bbceb6082.png)
	
	
### Observing for 40% of utilization
	
**Modifying constraints**
	
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files2/vsdbabysoc.tcl
```
	
![image](https://user-images.githubusercontent.com/118953917/217759090-7eb31412-14ed-4604-8da3-81b85447ddd1.png)
	
* Rerun the script in dc_shell and generate reports
	
**Generated vsdbabysoc.sdc after synthesis**
	
![image](https://user-images.githubusercontent.com/118953917/217759913-3466353f-7348-4904-bc93-26ed35fe5491.png)
	
**Modifying core utilization = 40% in top.tcl**
	
![image](https://user-images.githubusercontent.com/118953917/217760917-e17bb74b-4a65-4726-b8e2-da932beec9c8.png)

**Output Layout**
	
* The core of DAC now seems to be bigger in size as compared to previous run where core utilization = 7%
	
![image](https://user-images.githubusercontent.com/118953917/217760159-f7f62af4-7a64-4fd9-ac0e-f6993a39235b.png)
![image](https://user-images.githubusercontent.com/118953917/217760431-5db2e483-8a60-484d-859b-92361b3e3248.png)

**Slacks**
	
* The slack seems to be decreased from the previous run
	
![image](https://user-images.githubusercontent.com/118953917/217763560-a4b29179-7668-4293-8314-db84d78140c9.png)
![image](https://user-images.githubusercontent.com/118953917/217763610-ba7375f8-6a26-4c60-8a00-906cdf3d2b02.png)
![image](https://user-images.githubusercontent.com/118953917/217763674-b681b822-f7ab-475c-b426-aff679b102a9.png)

	
</details>

## Day-21

### Topic: Placement and CTS labs

<details>
  <summary>Theory</summary>
 
### Placement
  
* Pre-placement sanity check: floating pins in netlist, unconstrained pins, timing, pin direction mismatch, and etc.
  
**What is placement?**
  
* Standard cell
* Placement stages including:
  + Global placement
  + Legalization
  + Detailed placement
  
**Placement objectives**
  
* Congestion
* Performance
* Timing
* Routability
* Runtime
  
### Clock Tree Synthesis (CTS)
  
**Inputs of CTS**
  
* Placement DB
* CTS Spec file
  
**CTS Steps**
  
1. Clustering
2. DRV Fixing
3. Insertion Delay Reduction
4. Power reduction
5. Balancing
6. Post-conditioning
  
**CTS Quality Checks**
  
* Skew
* Pulse width
* Duty cycle
* Latency
* Clock tree power
* Signal integrity and Crosstalk 
* Timing analysis and fixing
  
*Source: notes were taken from lecture slides*
  
</details>

<details>
  <summary>Lab</summary>
 
### Placement, CTS and Routing
  
**Using core utilization = 40% in top.tcl**
  
**Script in top.tcl**
  
* ```create_placement``` is used to create placement for the design. ```floorplan``` option is selected to make the design planning styled as placement. 
* Pin Placement is done by sourcing pns.tcl to sync with the current technology file regarding power grid creation.
  
![image](https://user-images.githubusercontent.com/118953917/218297745-96602f27-19c0-44a6-979e-e81bf0bc81cf.png)
![image](https://user-images.githubusercontent.com/118953917/218297768-d0730840-039b-4ccc-a2d3-a2002d5d9141.png)

**Reports that were generated from the run**
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/place_pins/check_design.pre_pin_placement
```
  
* There are 3 warnings in total for pre-placement while checking the design.
  
![image](https://user-images.githubusercontent.com/118953917/218298713-739fb52c-e1e5-4e39-8de7-17e8789cd72c.png)
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/place_pins/report_port_placement.rpt
```
  
![image](https://user-images.githubusercontent.com/118953917/218299564-5e967467-86e8-422a-aaff-f257de6513d4.png)
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/icc2_output.txt
```
![image](https://user-images.githubusercontent.com/118953917/218299493-57808111-de38-4335-b5f0-9b318f396143.png)
![image](https://user-images.githubusercontent.com/118953917/218298961-aefdde53-150b-4f37-83de-ce857be8f10e.png)
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/timing_estimation/vsdbabysoc.post_estimated_timing.rpt
```
  
* Post estimated timing report for the design shows the slack has met with the value of 0.67

![image](https://user-images.githubusercontent.com/118953917/218299368-03ff1290-7716-45ee-a329-ca1d90f110d2.png)

```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/timing_estimation/vsdbabysoc.post_estimated_timing.qor
```
  
* Post estimated timing qor shows there is no violating path reported with 92 nets having violations, 79 max trans violations, and 83 max cap violations.
  
![image](https://user-images.githubusercontent.com/118953917/218299765-d3206736-8890-4cea-8e50-5a602b27254d.png)
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/timing_estimation/vsdbabysoc.post_estimated_timing.qor.sum
```
  
* Summary of Post estimated timing qor
  
![image](https://user-images.githubusercontent.com/118953917/218299961-09f62744-36a4-4d49-8749-616a64b94490.png)

**CTS schematic design**
  
*Note: before CTS, the clock would be ideal, while after CTS, the clock will be propagated*
  
![image](https://user-images.githubusercontent.com/118953917/218315845-f5377f9c-c93c-4be1-8fa1-38723bc24b0c.png)

![image](https://user-images.githubusercontent.com/118953917/218317392-6ae95cc9-a0bd-4dc2-83f8-779f972ba514.png)

  
</details>

## Day-22

### Topic: CTS analysis labs

<details>
  <summary>Theory</summary>
 
### CTS
  
**What is CTS?**
  
* Clock Tree Synthesis
* A technique for distributing the clock equally among all sequential parts of VLSI design
* It will balancing the delays to all clock input pins when the clock is distributed equally
* The goal of CTS is to minimize skew and insertion delay
  
![image](https://user-images.githubusercontent.com/118953917/217413608-7e43ff8e-67b5-4c46-acea-04d2bf6898ec.png)

**Various algo’s used for CTS**
  
![image](https://user-images.githubusercontent.com/118953917/217414647-8c241be6-200a-4a4a-b854-337c95911ede.png)

**H-tree algorithm**
  
1. Find out all the flops present
2. Find out the center of all the flops
3. Trace clock port ot the center point
4. Divide the core into two parts, trace both the parts and reach to each center
5. From the center, again, divide the area into two and again trace till center at both the end
6. Repeat this algo till the time we reach the flop clock pin
  
![image](https://user-images.githubusercontent.com/118953917/217415097-2f1675c7-533e-4d1b-858f-524f7a2cbd77.png)

**Various CTS checks**
  
* Skew check
* Pulse width check
* Duty cycle check
* Latency check
* Power check
* Crosstalk Quality check
* Delta Delay Quality check
* Glitch Quality check
  
**Some useful commands**
  
* This command checks and reports issues that can lead to bad QoR
  + Clock tree structure
  + Constraints
  + Clock tree exceptions
  
```
check_clock_tree
```
  
* This command checks the design whether the placement done input is perfect or not
  
* If it is legal, it is well and good
  
```
check_legality
```
  
* Else, use below command
  
```
legalize_placement
```
  
* There are some default constraints that CTS used, refer table below
  
![image](https://user-images.githubusercontent.com/118953917/217416747-e4f7ede4-49ed-4f99-8cc3-d4016d7a99e4.png)
  
* To edit those default constraints, use command below

```
set_clock_tree_options
```
  
* Below are some examples (be careful keeping min and max values in sight)
  
```
-max_capacitance
-max_transition 
```

![image](https://user-images.githubusercontent.com/118953917/217417327-52c7cfa3-2d30-44b0-a6f2-3f60eccf0c50.png)

* IC Compiler uses the CTS design rule constraints for all optimization phases, as well as for CTS
  
* For information about setting the clock tree synthesis design rule constraint, below are the commands
  
![image](https://user-images.githubusercontent.com/118953917/217417626-e74f29f4-7353-42a8-9776-1562647ed9dd.png)

* We can use ICC2 with debug mode by using below command
  
*Note: Please refer the ICC2 manual from synopsys*
  
```
-set cts_use_debug_mode true
```
  
* The main command we need to do is as below command
  
```
compile_clock_tree
```
  
**CTS results analysis**
  
* We can use the report for the tree that has been built using below command
  
```
report_clock_tree
-summary 
-settings 
```

* Other reports to see
  + Reports Max global skew
  + Late/Early insertion delay
  + Number of levels in clock tree
  + Number of clock tree references (Buffers)
  + Clock DRC violations 
  
* Also, another report related to clock timing report for paths that are related
  + Reports actual
  + Relevant skew
  + Latency
  + Interclock latency 
  
```
report_clock_timing
–type skew
```
  
* After observing the reports, if we see the clock tree could be better, perform CTS and incremental physical optimization as command below
  
* This process results in a timing optimized design with fully implemented clock trees
  
* The command below does the following:
  + Performs clock tree power optimization
  + Synthesizes(Re-Synthesizes) the clock trees
  + Optimizes the clock trees
  + Adjusts the I/O timing 
  + Performs RC extraction of the clock nets and computes accurate clock arrival times
  + Performs placement and timing optimization
  
```
clock_opt
```
  
* Sometimes, there will be some unrouted clock trees
  
* To remove them, perform the command below
  
```
remove_clock_tree
```
  
**After CTS, we do synthesis**
  
* Before we synthesize the clock trees, use below command to verify that the clock trees are properly defined
  
```
check_clock_tree 
icc2_shell> check_clock_tree -clocks my_clk
```
  
**Another useful commands**
  
![image](https://user-images.githubusercontent.com/118953917/217419707-46912d99-d641-4234-b994-490871c9442c.png)
  
*Source: notes were taken from lecture slides*

</details>

<details>
  <summary>Lab</summary>
 
### CTS Lab analysis
  
> In icc2 terminal
```
check_clock_tree                        (Checking the issues that can lead to bad QoR)
check_legality                          (Checking the legality of the current placement and report out the violation statistics)
report_clock_timing -type summary   
report_clock_timing -type skew
report_clock_timing -type latency
report_clock_timing -type transition
```
  
![image](https://user-images.githubusercontent.com/118953917/218360297-13c3d2ac-623e-437d-a131-63d6a13e9137.png)

![image](https://user-images.githubusercontent.com/118953917/218360583-10a7b5b7-8400-47a7-adea-0a0977709e0e.png)
  
![image](https://user-images.githubusercontent.com/118953917/218360420-4ba1de78-6ba0-4359-a770-8580a131b70b.png)
![image](https://user-images.githubusercontent.com/118953917/218360450-f00b6e86-6080-431d-822a-001393eb81ef.png)
  
</details>

## Day-23

### Topic: Clock gating technique

<details>
  <summary>Theory</summary>
  
**What have been done till now?**
  
*Source: notes were taken from lecture slides*
  
![image](https://user-images.githubusercontent.com/118953917/218362327-fbe5a8a3-abe2-406f-b15a-403f3bd95518.png)

**Advanced H-Tree for million flop clock end-points randomly placed**
  
* When CTS is performed, power consumption also needs to be taken care of, especially when designing a large number of clocks where the design might induce a larger power, as well as a larger power usage
  
* A digital circuit with a lot of clocks would be so huge with many buffers etc when designing its clock tree
  
* In order to fix that, the whole chip is sectioned into smaller versions where each section will have its own clock tree, and managed to get a complete routed tree
  
* Therefore, Clock Gating (CG) technique is introduced
  
![image](https://user-images.githubusercontent.com/118953917/218363457-02173a31-3f02-4da7-8c5b-6e5e649b6c8b.png)

### Introduction to Clock Gating technique
  
**What is Clock Gating (CG)?**
  
It is used to reduce the clock power consumption by cutting off the idle clock cycles
  
![image](https://user-images.githubusercontent.com/118953917/218364256-e5986c32-df81-4cf1-a9ba-63e82d0f0fc1.png)
  
**Where/when clock gating is applied?**
  
It is being inserted in synthesis stage and being optimized in the implementation stage (Physical Design stage)
  
**Types of clock gating**

* AND gate
* OR gate
* Universal AND gate
  
### Routing
  
**What is routing?**
  
The process of making physical connections between signal pins using metal layers
  
**Types of routing**
  
* P/G routing
* Clock routing
* Signal routing: Global & Detailed routing
  
**Basic flow of routing**
  
* Basically, ```route_opt``` command is used during routing stage
  
![image](https://user-images.githubusercontent.com/118953917/218365473-578d4d99-6268-4f26-b7cd-5fd016cd1c03.png)

</details>

<details>
  <summary>Lab</summary>
 
### Routing 
  
**Script in routing stage**
  
*  P/G routing  
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files2/pns_example.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/218367194-91aef276-5660-4c73-a2da-ad095b4a7898.png)

* Clock and signal routing

```place_opt``` is used to place and optimize the current design
  
```clock_opt``` is used to synthesize and route the clocks, and then further optimize the design based on the propagated clock latencies
  
```route_auto``` is used to run global routing, trace assignment, and detailed routing at once/automatically
  
```
/nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files2/top.tcl
```
  
![image](https://user-images.githubusercontent.com/118953917/218368079-f5823292-3140-4e87-a14f-32b980267ee6.png)
  
</details>

## Day-24

### Topic: Timing violations and ECO

<details>
  <summary>Theory</summary>
  
### Introduction to Engineering Change Order (ECO)
  
* Basically, ECO is the way on how we incorporate last minute changes in our design
  
* Typically, ECO has been done on the gate level netlist, but designer needs to edit the gate-level netlist and perform the same changes in RTL
  
* Then, all the verifications must be passed before it is being passed onto the layout and ensure that the ECO is passing a formal and functional verification before we start editing the layout
  
* In this stage, all the violations are fixed and all the sign-off checks that were not done during the PD flow are sealed
  
* Steps to perform ECO
  1. Investigate the problem using the recent database
  2. ECO generation to address the problem
  3. ECO implementation with the recent database
  4. After implementing and fixing the problem, save it in the database for future
  
* ECO strategies
  
![image](https://user-images.githubusercontent.com/118953917/218370188-c5e95462-e61e-4cb5-8637-352703b55461.png)
  
</details>

<details>
  <summary>Lab</summary>
 
### Timing violations and ECO
  
**Reviewing full report timing**
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/rpts_icc2/timing_estimation/vsdbabysoc.post_estimated_timing.rpt
```
  
* Estimated report timing before CTS
* Clock network delay is ideal, hence there is no delay reported and the slack is good
  
![image](https://user-images.githubusercontent.com/118953917/218665586-61ee4256-e9dd-4eb5-9fda-598218330217.png)
  
```
report_timing -from core/CPU_is_add_a3_reg -to core/CPU_Xreg_value_a4_reg[24][31] -corner estimated_corner -mode [all_modes]
```
  
* Estimated report timing after CTS
* Clock network delay is propagated, hence there is some delay which makes the slack is slightly higher than pre-CTS
  
![image](https://user-images.githubusercontent.com/118953917/218665665-cf31a551-ce38-4357-bc30-5083d303ab0a.png)
  
```
report_timing -from core/CPU_is_add_a3_reg -to core/CPU_Xreg_value_a4_reg[24][31] -path_type full_clock_expanded -capacitance -nets -physical
```
  
* Need to upsize the cell to improve the timing
* Upsizing the cell will increase the drive strength of the cell which will help in reducing the delay
* Upgrading the drive strength depending on the analysis stated in the report timing
  
![image](https://user-images.githubusercontent.com/118953917/218665739-6fce88e8-9f72-45c1-9038-0da25907596b.png)
  
* Picking some cells to upsize in order to reduce the delay arrival time
  
> Upsizing the cell
```
size_cell core/U6 sky130_fd_sc_hd__nand2_4
size_cell core/U561 sky130_fd_sc_hd__a21oi_4
size_cell core/U67 sky130_fd_sc_hd__nand2_8
```
  
```
report_timing -from core/CPU_is_add_a3_reg -to core/CPU_Xreg_value_a4_reg[24][31] -path_type full_clock_expanded -capacitance -nets -physical
```
  
* The slack is still violated, however, the slack has improved after upsizing the cell
  
![image](https://user-images.githubusercontent.com/118953917/218665848-c55afe4c-2aa5-4f86-a1c1-64a8cae39968.png)
  
**Comparison reports before and after ECO**
  
```
report_qor
```
	
* Timing perspective --> the timing has improved
  
![image](https://user-images.githubusercontent.com/118953917/218699141-b4f53577-adfb-403b-ae38-447ec1b11b44.png)
  
* Area perspective --> the area has increased since the the cell has been upsized
  
![image](https://user-images.githubusercontent.com/118953917/218699223-9a3ead61-bd63-42f5-bf11-7677a35383a0.png)
  
```
report_power
```
	
* Power perspective --> theoretically, total power usage will increase since the area has increased due to upsizing cell. However, the power usage for both pre and post CTS are the same since the total area increased is not that much.

![image](https://user-images.githubusercontent.com/118953917/218699307-226d4417-e434-4676-89c0-29119e26f237.png)
  
### Adding in decaps
  
```
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files2/top.tcl       	(Insert decaps command in top.tcl)
source /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/files2/top.tcl
gvim /nfs/png/disks/png_mip_gen6p9ddr_0032/nazahah/lab/d20/shell/icc2_output.txt
```
  
![image](https://user-images.githubusercontent.com/118953917/218705451-28cb9312-ad5d-4651-bc3d-58d95218e9bd.png)
  
```
report_power
```
  
![image](https://user-images.githubusercontent.com/118953917/218706906-cc9a14df-48aa-453b-a562-0219043d33b7.png)  
  
</details>
