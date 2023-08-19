# Samsung_PD_Training

## Day-0-Installation

	
 <details>
 <summary>icc2_shell </summary>
I invoked icc2_shell using the following commands: icc2_shell
     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f81f46c9f861cb08ef7596f570cbd10cc01e9091/Samsung_PD_%23day0/icc2_shell.png">

 <details>
 <summary>lc_shell </summary>
I invoked lc_shell using the following commands: lc_shell
     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="

<details>
 <summary>pt_shell </summary>
I invoked pt_shell using the following commands: pt_shell
     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e0245a8279215425e6a0e2ccf73813ad8d797a02/Samsung_PD_%23day0/pt_shell.png">

## Day-1 Introductio to Verilog RTL design and Synthesis
<details>
 <summary>  Introduction to open-source simulator iverilog</summary>
	
RTL Design : It is a set of codes that has actual intended functionality to meet with the required specifications..
If this design is relevent or not to the specifications, is checked through simulation

Test Bench: It is a set of stimulus that is applied as input, so that output can be checked with required specifications.

<img width="1085" alt="testbench" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9e9b2ccf08d08d98cf3391071bc9e8cdf23bdb25/Test_bench.png">

Iverilog simulates the design with testbench and gives a vcd file as an output.

vcd : Value change dump format

gtkwave is used to see the waveforms of output corresponding to input to verify the functionality of the design.

<img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/8fc352c80011d6e96499c5e888e259c13eee9d6e/iverilog%20represntation.png">

<details>
 <summary> Labs using iverilog and gtkwave </summary>

 my_lib : Contains all the standard cells which are presnt as .lib extension.

 verilog_files : Contains all designs, source files and testbench files.

 These are the commands used to load and execute the simulation 

 iverilog good_mux.v tb_good_mux.v    /Loads the corresponding verilog and testbench file
 ./a.out                              /Dumps the vcd file
 gtkwave tb_goodmux.vcd               /loads the corresponding waveform

 <img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d1b3c06d6bdfb1be0defff1a5c1928fd9a239524/iverilog.png"> 

<img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/6fc399a1d0b7dca892fa3f25ad518f11af132285/Samsung_PD_%23day0/gtkwave.png">

<details>
 <summary> Introduction to Yosys and Logic synthesis </summary> </summary>
 Yosys is a tool used for converting RTL to netlist

 The following commands are used in the simulation

 read_verilog    /reads the verilog design
 read_liberty    /reads .lib file
 write_verilog   /create output netlist

 .lib contains different flavours of gates(slow, medium, fast etc)
 Combination delay in logic path determines the max speed of operation of digital logic circuit.

 Fclk = 1/Tclk
 More the clock speed, better is the performance

 Tradeoff between different cells;  
 Load in digital circuit is due to capacitance.
 To charge/discharge the capacitance fast, we need transistors capable of sourcing more current -> wide transistors, low delay but more area and power.

 Narrow transistors are used for less Area and power but more delay

 <img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/83673d85b9d212bc5f5ba8bb78d6f59cba5088e6/yosys.png">

show : This command shows

 <img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e7b25070eae5670927c16ebfcd6dbcbd2e6834b9/yosys%20with%20show.png">

<details>
 <summary> Labs using Yosys and Sky130 PDKs</summary> </summary>
 commands used for synthesis

 read_verilog    /reads the verilog design
 read_liberty    /reads .lib file
 synth -top good_mux    
 abc -liberty ../lib/sky       /Converts rtl to netlist, gates from .lib
 write_verilog   /create output netlist 
 
