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

  
  
## Day-8

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

## Day-7

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
