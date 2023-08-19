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

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/afc24b6ff5118eda2448534db9fd8df4751c1efd/Samsung_PD_%23day0/lc_shell.png">

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
src="  "> 
