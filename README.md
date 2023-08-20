# Samsung_PD_Training

## Day-0-Installation

	
 <details>
 <summary>icc2_shell </summary>
I invoked icc2_shell using the following commands: icc2_shell


IC Compiler II is a complete netlist-to-GDSII implementation system that includes early design exploration and prototyping, detailed design planning, block implementation, chip assembly and sign-off driven design closure.
     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f81f46c9f861cb08ef7596f570cbd10cc01e9091/Samsung_PD_%23day0/icc2_shell.png">

 <details>
 <summary>lc_shell </summary>
I invoked lc_shell using the following commands: lc_shell


The Library Compiler tool from Synopsys captures ASIC libraries and translates them into Synopsys internal database format for physical synthesis or into VHDL format for simulation. 
     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="lc_shell" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/3598414705a3bd628359947ffa97dfbfb6037bd3/Samsung_PD_%23day0/lc_shell.png">


<details>
 <summary>pt_shell </summary>
I invoked pt_shell using the following commands: pt_shell

Synopsys' PrimeTime static timing analysis tool provides a single, golden, trusted signoff solution for timing, signal integrity, power and variation-aware analysis.     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e0245a8279215425e6a0e2ccf73813ad8d797a02/Samsung_PD_%23day0/pt_shell.png">

<details>
 <summary> yosys </summary>
I invoked yosys using the following commands: yosys

Yosys is a framework for RTL synthesis and more. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys is the core component of most our implementation and verification flows.     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/1626dbcc4c0acf3e2a1dac7f69d15f93b18925b4/yosys_invoke.png">


## Day-1 Introductio to Verilog RTL design and Synthesis
<details>
 <summary>  Introduction to open-source simulator iverilog</summary>
	
RTL Design : It is a set of codes that has actual intended functionality to meet with the required specifications.
This design's relevence to the specifications, is checked through simulation.

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

read_verilog    #reads the verilog design

read_liberty    #reads .lib file

write_verilog   #create output netlist

.lib contains different flavours of gates(slow, medium, fast etc)
Combination delay in logic path determines the max speed of operation of digital logic circuit.

Fclk = 1/Tclk
More the clock speed, better is the performance

Tradeoff between different cells;  
Load in digital circuit is represnted by capacitance.
To charge/discharge the capacitance fast, we need transistors capable of sourcing more current -> wide transistors, low delay but more area and power.

Narrow transistors are used for less Area and power but more delay

Hence an ideal trade off is to be performed with the usage of different cells as per the requirement and specifications that are intended.

<img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/83673d85b9d212bc5f5ba8bb78d6f59cba5088e6/yosys.png">

show : This command shows the design connections visually.

<img width="1085" alt="iverilog" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e7b25070eae5670927c16ebfcd6dbcbd2e6834b9/yosys%20with%20show.png">

<details>
<summary> Labs using Yosys and Sky130 PDKs</summary> </summary>
commands used for synthesis

read_verilog                          #reads the verilog design
read_liberty                          #reads .lib file
synth -top good_mux    
abc -liberty ../lib/<lib name>        #Converts rtl to netlist, gates from .lib
write_verilog                         #create output netlist 

The result shows the consolidated no of different gates being used in the netlist and the no of inputs and outputs.


write_verilog -noattr
-noattr reduces the netlist size by deleting the additional information attatched to the design elements making the netlist compact.

The below screenshot shows the synthesised netlist of a good_mux i.e a 2:1 Mux 

<img width="1085" alt="yosys" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/404bb412d6b276af1dce4b8629cabc08f9411996/synthesised_netlist.png">
