

## Day-0-Installation

	
 <details>
 <summary>icc2_shell </summary>
I invoked icc2_shell using the following commands: icc2_shell


IC Compiler II is a complete netlist-to-GDSII implementation system that includes early design exploration and prototyping, detailed design planning, block implementation, chip assembly and sign-off driven design closure.
     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f81f46c9f861cb08ef7596f570cbd10cc01e9091/Samsung_PD_%23day0/icc2_shell.png">
</details>
	
<details>
<summary>lc_shell </summary>
I invoked lc_shell using the following commands: lc_shell


The Library Compiler tool from Synopsys captures ASIC libraries and translates them into Synopsys internal database format for physical synthesis or into VHDL format for simulation. 
     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="lc_shell" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/3598414705a3bd628359947ffa97dfbfb6037bd3/Samsung_PD_%23day0/lc_shell.png">
</details>


<details>
 <summary>pt_shell </summary>
I invoked pt_shell using the following commands: pt_shell

Synopsys' PrimeTime static timing analysis tool provides a single, golden, trusted signoff solution for timing, signal integrity, power and variation-aware analysis.     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e0245a8279215425e6a0e2ccf73813ad8d797a02/Samsung_PD_%23day0/pt_shell.png">

</details>

<details>
 <summary> yosys </summary>
I invoked yosys using the following commands: yosys

Yosys is a framework for RTL synthesis and more. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys is the core component of most our implementation and verification flows.     

     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/1626dbcc4c0acf3e2a1dac7f69d15f93b18925b4/yosys_invoke.png">
</details>

<details>
 <summary>dc_shell </summary>
I invoked dc_shell using the following commands: dc_shell

dc_shell is used for RTL (Register Transfer Level) synthesis, which involves transforming a high-level hardware description (often written in languages like Verilog or VHDL) into a gate-level representation that can be used for further steps in the chip design process. It optimizes the design for factors like area, power, and timing, helping to generate an efficient gate-level netlist that meets the specified design constraints.     
Below is the screenshot showing sucessful launch:

<img width="1085" alt="dc_shell" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/cb56333cdd3add1a26f7f2a16da543d2a47ea5d4/Images/dc_shell.PNG">
</details>

<details>
 <summary>gtk_wave </summary>
I invoked gtkwave using the following command: gtkwave

With gtkwave, designers can visualize the behavior of their digital designs over time. It allows user to load and display simulation output files, often in formats like Value Change Dump (VCD) or Signal List (SL), which contain information about how signals change over simulation cycles.

By visualizing waveforms, designers can identify issues such as incorrect logic behavior, timing violations, or unexpected signal transitions, helping them debug and validate their designs more effectively.Below is the screenshot showing sucessful launch:

<img width="1085" alt="gtkwave" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/7341c5b49af39cc39c2ef7ad08bf3cb8b82c529d/Images/gtkwave.png">
</details>

<details>
 <summary>iverilog </summary>
I invoked Icarus Verilog using the following commands: iverilog

iverilog allows user to write Verilog code to describe digital circuits, and then it can simulate the behavior of those circuits to help the user catch and fix bugs before manufacturing. It's often used for tasks like functional verification, testbench development, and even simple logic synthesis for small designs.


<img width="1085" alt="iverilog" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/df6b7d65dc9539c0d3b0f5cc1296cec6c6251501/Images/icverilog.png">

</details>


# Day-1 Introduction to Verilog RTL design and Synthesis
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

</details>

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

</details>

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

</details>

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
</details>

# Day - 2

<details>
<summary> Introduction to timing libs </summary> </summary>

A ".lib" file contains the following information

Cell Definitions: The file contains definitions for various standard cells used in digital circuit design. Each cell is associated with a specific functionality.

Timing Information: The ".lib" file includes data about cell delays, rise and fall times, input/output transition times, etc. This information helps in estimating the overall timing behavior of the designed circuit.

Power Characteristics: ".lib" files often include data about power consumption for different operations and conditions, aiding in power analysis and optimization.

Functional Behavior: The ".lib" file provides information about the logical behavior of each cell, including its truth table or Boolean equation representation. This data is essential for the synthesis process that translates a high-level description of the circuit into actual logic gates.

Process, Voltage and Temperature Variations: Modern VLSI designs need to account for variations in process,voltage and temperature. ".lib" files might provide data on how cell behavior changes with different operating conditions.( P V T)
Process: Variation due to Fabrication. As cells cant be fabricated in the exact same way when done in millions.
Voltage : Variations due to different voltages.
Temperature : Should work fine in Siachen glacier and Thar desert too.

Sizing Information: The ".lib" file might include sizing information for cells, helping designers choose appropriate sizes based on performance and power considerations.

<img width="1166" alt="lib untro" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/97d50aec-fa08-46f5-8d66-4ce6389d7c48">

The above image shows that this library is in 
Cmos Technology with 130 nm teachnology,
typical typical process variation considered,
1.8 Voltage,
25 degree celcius temperature,
and it also shows how the different parameters are measured further and on which units.

<img width="1182" alt="lib_different_flavours" <img width="674" alt="lib_different_flavours2" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/328dfe52-aef3-4b72-8d07-ac6801b2c013">
src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/32588b1e-6181-41a7-9d1e-74afc6fd4e02">

The above screenshots show different flavours of the same cells which are present in the library.
It also shows how the parameters differ for each combination of input applied to the cell.
<img width="1576" alt="lib_comparison" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/57780378-7bda-4898-a102-b06b79ccec56">

The above screenshot clearly shows the comparison between the flovours of the cell.
With wider cells being the fastest but having the highest area in comparison to smaller cells which have less area but more delay. the Cell in between has parameters between these two cells. i.e Less area than wider cells and more area than smaller cells.

</details>

<details>
<summary> Hierarchial Vs Flat </summary> </summary>

Hierarchical synthesis involves breaking down a complex design into smaller, manageable blocks or modules. Each module is synthesized separately, and then these synthesized modules are integrated into the overall design hierarchy. This approach is beneficial for handling large and complex designs because it allows for better organization, and easier design reuse.
![herarchial_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/afac86fd-c11d-4c81-9f2e-3e6e50851459)

In the beloww screenshot , we can observe that the hierarchies are preserved. Hence the name Hierarchial synthesis.
The and and Or gates are instantiated in their respective sub modules. The top module "multiple_modules" contains both the modules that make up the entire design.

![Modules](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/de4301b0-9cd2-4194-943a-d2e7e968dcbf)

The below screenshot shows the final netlist after synthesis.

![Hier_syn_netlist](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/8a0663b3-82a9-4cb9-8599-b1142c883506)


Flat synthesis, on the other hand, involves synthesizing the entire design as a single unit or block. All modules and sub-modules are synthesized together in a single step. This approach is simpler in terms of design setup, but it may become impractical for large and complex designs due to the increased complexity and longer synthesis times.

</details>

<details>
<summary> Various Flop Coding Styles </summary> </summary>

Flops are used to avoid glitches in combinational circuits

<img width="1700" alt="asyncff_waveform" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/cefdd811-5be5-4760-9be7-f8bc34e19059">

The above waveform shows the operation of D flip-flop with asynchronous reset
As soon as asynchronous reset is high, irrespective of Clock, the Q follows D.

<img width="1720" alt="sync_reset" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/f53de749-ba17-491b-a995-6fabab5aaaa6">

The above screenshot represents the synchronous reset.
Here we observe that the low(0) signal is seen at the output at the next positive clockedge after the apply of sychronous reset signal and not at the same instant as observed in asynchronous reset.


 <img width="1716" alt="async_set" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/96bfeb83-e7c9-48ad-b0c6-91a0aef33737"><img width="1725" alt="sync_res" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/45fe1860-0a1a-440a-96e2-67be36357306">

<img width="1725" alt="sync_res" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/3a6ec4ba-ff11-486e-bfa3-d8baf7c26929">
</details>

<details>
<summary> Optimizations </summary> </summary>

<img width="1231" alt="mul2 verilog" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/bc506996-1203-475e-b46d-e5369963caea"><img width="1211" alt="mult_8 verilog" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/b8bfea20-062f-4441-8240-0086788dfa71">

<img width="1704" alt="mul2 synthesis" <img width="1208" alt="mul2 netlist" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/38effaa9-8678-4e71-823a-1eb0bc65ec6e">
src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/5425fbd3-db96-47dc-a0d9-30c70de29b03">
<img width="1206" alt="mult8_netlist" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/3eaedf70-4980-4cd0-8dc9-175425d86e0f">
