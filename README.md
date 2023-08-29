

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

# Day - 2 Timing libs, hierarchical vs flat synthesis and efficient flop coding styles


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

The above screenshot clearly shows the comparison between the flavours of the cell.
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

The below screeshot shows how the cells are being instantiated directly in flat synthesis rather tham sub_blocks/modules being synthesised in hierarchial synthesis.
![flat_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/199cba63-5e14-4ed4-b0ca-245a190e6d4a)

The below screenshot represents the netlist of the flattened synthesis of the design.
![flat_synthesiss_netlist](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/05e6055f-c9b9-4334-a33f-a8939f08c336)


</details>

<details>
<summary> Various Flop Coding Styles </summary> </summary>
Flops are iused as storage elemments in digital circuits which give stable output despite of glitches or unintended changes in input signals.
With increasing number of combinational circuits, the glitches also increase ,thereby making output highly unstable.This property of Flop are used to avoid glitches in combinational circuits.

<img width="1700" alt="asyncff_waveform" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/cefdd811-5be5-4760-9be7-f8bc34e19059">

The above waveform shows the operation of D flip-flop with asynchronous reset
As soon as asynchronous reset is high, irrespective of Clock, the Q follows D.

<img width="1720" alt="sync_reset" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/f53de749-ba17-491b-a995-6fabab5aaaa6">

The above screenshot represents the synchronous reset.
Here we observe that the low(0) signal is seen at the output at the next positive clockedge after the apply of sychronous reset signal and not at the same instant as observed in asynchronous reset.

The below screenshot represents the synthesised design of Asynchronous set D Flipflop.
In Asynchronous set D Flipflop irrespective of the clock edge, the q value is  forced to 1 when async_set signal is high(1).
Here along with the normal procedure of synthesis in yosys, one additional command being used is:
dfflibmap -liberty <lib_path>

This command will only look for d flip flops in the library and not all the cells.
 <img width="1716" alt="async_set" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/96bfeb83-e7c9-48ad-b0c6-91a0aef33737">

 The below screenshot represents the synthesised design of Synchronous Reset D Flipflop.
 In Synchronous Reset D Flipflo, Q value is set to 0 when the reset signal is high(1) but only at the next positive edge of clock signal.
 <img width="1725" alt="sync_res" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/45fe1860-0a1a-440a-96e2-67be36357306">

</details>

<details>
<summary> Optimizations </summary> </summary>
Certain optiizations can be done in such a way that the logic can be realized without the usage of any hardware. Here are 2 such examples, 
1st one is multiplying a 3bit number by 2, called as mult_2.
<img width="1231" alt="mul2 verilog" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/bc506996-1203-475e-b46d-e5369963caea">

It is seen that the result can be obtained directly by connecting the same input bits to the output and grounding the LSB.
The synthesised netlist for the same is shown below

<img width="1704" alt="mul2 synthesis" <img width="1208" alt="mul2 netlist" 
src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/38effaa9-8678-4e71-823a-1eb0bc65ec6e">

Another such optimization is found in multiplying a 3bit number by 9.
This is realized by applying a simple distributive property
a* (9) =y;  
a*(8+1)=y;
(a*8) + (a*1) = y;
<img width="1211" alt="mult_8 verilog" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/b8bfea20-062f-4441-8240-0086788dfa71">
src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/5425fbd3-db96-47dc-a0d9-30c70de29b03">

The below screenshot represents the final netlist of the design. The result is given by simply represting the inputs i.e. (a,a)

<img width="1206" alt="mult8_netlist" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/3eaedf70-4980-4cd0-8dc9-175425d86e0f">
</details>

# Day-3 Combinational and sequential optimizations 

<details>
<summary> Combinational logic optimizations with examples</summary> 
Combinational logic optimization involves refining digital designs to enhance efficiency in terms of area and power. This is achieved through synthesis tools that apply techniques like constant propagation and Boolean logic optimization, often using methods like Karnaugh maps or the Quine-McCluskey algorithm. These methods help in streamlining the logic circuit to achieve a more efficient and effective design.

An example for constant propagation


Example for Boolean logic optimization
y=a?(b?c:(c?a:)):(!c)

The given concurrent statement utilizes a ternary operator to create a sequence of multiplexers. Upon analyzing the boolean expressions at the outputs of each multiplexer and applying boolean reduction methods, the resulting expression for output 'y' simplifies to ~(a XOR c). This effectively represents the logic of the initial expression. To optimize the circuit using Yosys, you can utilize the command "opt_clean -purge" within the Yosys environment. This command aids in streamlining the circuit design.

Example-1

By pulling one of the inputs to logic 0, the floo gets minimized to an And gate.
<img width="467" alt="Screenshot 2023-08-24 at 10 33 41 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/a80577f5-283b-45a9-b27e-216d18eb1fe2">
Optimized circuit 
<img width="1714" alt="Screenshot 2023-08-24 at 10 43 06 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/0cefc2f9-acaf-4e42-a6a9-812d303bc7b6">

Example 2
The given Verilog code corresponds to the logic equation y = a'b + a. As a result of optimization, the synthesized outcome will be a basic OR gate.

![opt_check2_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/4a4cea07-c748-4647-9b53-6d1ee52023bc)

<img width="1728" alt="Screenshot 2023-08-24 at 10 45 51 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/315078e5-c4a7-4f93-9bf8-89bb087e0f5f">

Example 3

Originally, the provided code aimed to implement two multiplexers. However, through optimization, it condenses into a 3-input AND gate, as illustrated below.

![opt_check3_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/f2013533-c9a9-4b3d-805a-6626beea263d)


<img width="1702" alt="Screenshot 2023-08-25 at 9 14 54 AM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/497fdb67-678b-45a9-a13c-756d1e6c2c64">


Example 4

 ![opt_check4_veri](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/77714b16-abd8-499d-b002-141ce1c11b78)

After optimization the result is an xor Gate.

![opt_check4_v]
(https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/545cb4c8-c9bb-4524-ab8f-7a04cbe58fbf)

Example 5 Multiple modules

Here the multiple modules are being used, but with optimization we check if these are actually required and used or not.

![multiple_module_opt2_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/266d74d3-8936-45d0-bd94-2c3862f7fd69)

Without Flatten

![multiple_opt2_synthesiswitoutflat](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/b982c7b2-08ad-4a33-819f-3454ea6ca2ee)

With Flatten

![multi_opt2_withflatten_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/c3011331-32e6-498d-a0f0-37c79bf3e74c)


Example 6

![multiopt_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/1887119b-d73d-4004-a294-e11313967fb4)

Without flatten

![muti_opt_syntheiswithoutflatten](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/93d04f84-4da3-4f8a-9891-c14d3c70e401)

With flatten

![multi_opt_withflatten](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/06dae011-baaa-4167-aef5-a1299067cd5a)


</details>

<details> 
	
<summary>Sequential Logic Optimizations </summary>

Basic Methods:

Sequential Constant Propagation: This initial approach focuses on optimizing logic circuits by capitalizing on situations where the output of a flip-flop remains persistently zero. However, when the second flip-flop's output is in a constant state of change, it's unsuitable for this optimization technique.

Advanced Strategies:

State Optimization: More advanced in nature, this technique centers around enhancing efficiency by identifying and removing unused states within a circuit. The outcome is a leaner and more efficient state machine.

Retiming: A potent strategy involving the strategic movement of registers within the combinational logic of a circuit. This optimization improves performance by finding the right balance between power consumption and delay, all while preserving the original input-output behavior.

Sequential Logic Cloning (Floor Plan Aware Synthesis): Particularly relevant during the physical synthesis phase, this method tackles routing delay challenges. By introducing intermediary flip-flops between a source flip-flop and more distant ones, the aim is to reduce delays. The term "cloning" is used due to the creation of new flip-flops with identical functionality to the source.

Example 1

The below code represents a D flip-flop with an asynchronous reset. This reset function allows the system to be reset independently of its clock signal. After the reset, the system returns to its regular operation synchronously for the next cycle. 

![dff_const1_V](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/646c09a8-d604-4ee0-ac34-78f9e261b6f6)

Simulation

![dff_const1](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/7c27b21c-377b-412b-a187-f9f8b5781cb7)

Synthesis

![dff_const1_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/ac672e3f-b3a8-45e0-ba37-974abde252b5)

We can see that 1 flop is enough to realize the design.

Example 2


![dff_const2_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/fa2af418-a916-4aa7-ad67-c4d463ad16eb)

Simulation

![dff_const2](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/9b72a06b-51e3-4e34-a9ed-d03b6f506001)

Synthesis

![dff_const2_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/6179c411-6d9c-4d1b-95ed-74636d7cb9a8)

It's noticeable that the output consistently remains at '1' regardless of changes in the reset or clock signals. Based on this waveform, it seems that utilizing a buffer cell with its input tied to a logic '1' is sufficient to accurately represent and achieve the desired behavior of the design.
Hence flop wont be enabled as the output is always high.

Example 3

![dff_const3_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/fad1fde8-44a7-41e8-a0c1-e19360b71bce)

Simulation

![dff_const3_simulation](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/0f2cbe02-6725-4e85-8aed-d1ca5cc528a0)

Synthesis

In this design, when the reset is going from '1' to '0' q1 will be set to '1' in next edge of clock cycle and q will be latched a data from q1. Because of Clk-Q delay(Tc-q) q is latched with '0' and will be changed to '1' in next edge of cock cycle.

![dff_const3_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/0a7f86ee-36a6-404b-8eb5-0a5b0f92694d)

Example 4

![dff_const4_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/3d3c8c0d-9cee-47df-bff2-db7719811e97)


Simulation

![dff_const4](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/74617ffb-d6db-4186-8a06-a27bb8808eb0)

Synthesis

![dff_const4_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/797e7cc2-0f15-4912-9404-6b6a3f6a3dbd)

The tool has finally optimized the design to 2 buffers with input pulled to logic 1.
Example 5

![dff_const5_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/a29946be-4afd-4816-ae36-3410c546dcf3)

Simulation

![dff_const5](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/1c8986ee-2d29-43d2-911b-a1414987bf4b)

Synthesis

![dff_const5_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/ac0538fd-85c1-4a99-9fb4-e593b5204e24)

Because the values of q1 and q change based on both the reset signal and the clock, the design has been optimized by using two D flip-flops. The first flip-flop's data (D) input is directly connected to a logic '1', and its output is then connected to the input of the second flip-flop. This arrangement helps manage the transitions more effectively.


</details>

<details> 
	
<summary>Unused output </summary>

Sequential optimizations for unused outputs are techniques used to improve the efficiency and power consumption of digital circuits by minimizing the impact of unused or unnecessary outputs.These outputs consume power and can contribute to signal integrity issues.

Counter verilog
A 3bit counter is realized and syntheised.

![counter_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/fb581a31-a654-469c-9042-87493a29e171)

Counter Synthesis

During the synthesis process, when the 0 bit is solely used for output, only a single flip-flop is created with an inverter for the toggle function. The other bits remain unused, resulting in their respective flip-flops not being generated.

![counter_syntheswis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/498aae90-0297-45c5-bd6e-56cff8045d94)

Counter 2 verilog

![counter_opt2_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/5c5e80d0-c178-4525-8fe0-cf3ce4d647d6)

Counter synthesised netlist

![counter_opt2_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/230783bb-17d0-405a-b879-c8bef03aa3aa)

In this scenario, all three bits are utilized, necessitating the presence of three flip-flops. Additionally, an adder circuit has been incorporated to handle the counting logic.
</details>

# Day 4 - GLS, blocking vs non-blocking and Synthesis-Simulation mismatch

<details>
<summary> GLS, Synthesis-Simulation mismatch and Blocking/Non-blocking statements </summary>

GLS involves comparing the behavior of the synthesized gate-level netlist with that of the original RTL (Register Transfer Level) code. This comparison aims to ensure that the synthesized netlist maintains both the logical functionality and the expected timing of the original design.

When mismatches occur between synthesis and simulation, GLS helps identify and resolve these issues. It's essential to use the same testbench for both RTL simulation and GLS. This ensures that if the netlist and the RTL are logically the same, running the same testbench should yield matching outputs for both.
Gate level verilog models come in two main types: timing-aware models that assess both functionality and timing, and functional models that focus solely on functionality. This distinction helps capture and rectify differences between the synthesized netlist and the RTL design.

These are some reasons why we should check the netlist after synthesis

Missing Sensitivity List: The simulator detects changes in inputs to determine when computations should occur. If the sensitivity list is incomplete, the simulator might not catch all required input changes, leading to incorrect or stagnant outputs.

Blocking and Non-Blocking Assignments: The way assignments are made in Verilog can impact the simulation results. Mixing blocking and non-blocking assignments improperly can cause mismatches between synthesis and simulation.

Non-Standard Verilog Coding: Using coding practices not recognized by synthesis tools can lead to differences in how the code is interpreted during synthesis versus simulation. This can result in unexpected behavior.

Blocking and non-blocking statements are foundational concepts in Verilog, crucial for accurately simulating digital circuit behavior:

Blocking Statements: With the "=" symbol, blocking assignments execute in a sequence, pausing the execution of subsequent statements. They provide immediate updates to variables, instantly reflecting the changes made.

Non-blocking Statements: Denoted by "<=", non-blocking assignments allow parallel execution and don't impede subsequent statements. They capture simultaneous behaviors, mimicking the action of registers and flip-flops.

Sequential Flow: Blocking statements follow a sequential flow, processed in the order they're written. This characteristic makes them suitable for representing combinational logic.

Concurrent Operation: Non-blocking assignments model hardware components like registers and flip-flops, accommodating their concurrent updates. This aligns with the simultaneous nature of these elements in actual hardware.

Risk of Race Conditions: Incorporating blocking assignments within "always" blocks containing multiple assignments can introduce race conditions. These conditions emerge when the assignment order influences the final result.

Coveats with blocking statements
#insert here

</details>
<details>
<summary> Labs on GLS and Synthesis-Simulation Mismatch
</summary>

Example 1:
This verilog code represents a mux that selects between i1 and i0 based on the select line.

![ternary_mux_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/72ca3c54-ec25-4c7f-9ebb-1c55be7e7e84)

The below snap represents the waveform before synthesis

![mux_gtkwave](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/326669fd-9042-44d8-b52c-546794022a5f)

The below schematic represents the design after synthesis

![ternary_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/d8f125a6-2f56-4d5c-b71e-875dae58ae8a)

The below snap represents the waveform after synthesis, and we can observe that the waveforms before and after synthesis match each other, hence there is no synthesis simulations mismatch observed in this case.
![ternary_gls_gtk](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/eaaa8858-b48c-41de-a7f3-aaac53f56481)

Example 2
The below code shows the verilog code of a mux with the usage of Non-blocking statements
![bad_mux_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/13470f44-897b-407a-b220-036da43b3562)

The below snap shows the waveform before synthesis and here we can observe that the output is updating only when the value of the select line is changing. The subsequent changes observed in the selected input lines (i0 or i1) does not reflect in the output waveform.
This is not the intended function which was expected to be observed.

![bad_mux_gtkwave](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/df12546d-2d4e-42d7-af6f-fcd41410a960)

The below snap represents the the schematic of the design after synthesis

![bad_mux_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/9cc0b1c8-5bbd-4ae7-bf52-12f1391fe21a)

The below snap shows the waveform after syntheis.
It can be observed that the RTL simulation and GLS simulation are different from each other.

![bad_mux_gls](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/536b3897-8e70-428d-bcfa-e8ae11b4b163)

Example 3
In this example, the always block uses (*) symbol. With this the always block is evaluated when any signal changes. 

![good_mux_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/48847860-993e-4bc4-b66b-2eafd9b8a944)

The output of the simulation is shown below, which is the functionality of a mux.

![good_gtk](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/97dbf7a0-a367-41a6-bc02-ce5b4042a259)

The schematic after synthesis is shown below

![goodmux_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/42961c60-7edb-4068-a791-b744d3aa29b1)

The below snap represents the simulation of netlist with testbench.

![goodmux_gls](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/09c979a3-8dec-4b74-8a41-4f87e375021b)

The Gate level simulation and the RTL simulation show similar simulation results, due to which we can conclude that this style of coding preserves the intended functionality of the Mux.
</details>


<details>
<summary> Labs on synth-sim mismatch for blocking statement </summary>

The below snap represents the design for which we are going to run the simulation and synthsis. It comprises an OR and AND gate.
![blocking_c_v](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/dc47b1be-82fb-4866-ab27-919a8597ab2c)

The code mentioned above has a situation where the variable 'y' retains its previous or leftover value (referred to as garbage or q0 value). This causes a delay in the output similar to what happens in a flip-flop delay. This delay results in the output being visible one clock cycle later, as shown in the accompanying image.

![blocking_gtk](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/09d41fa2-47ab-4e16-88db-3d434cdedfd5)

After performing synthesis we get schematic as below, which is a OA21 as output.

![blocking_synthesis](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/9ca391ac-20b7-4dcf-8a30-7bd5354cafb6)

When we look at the image provided for the GLS below, it's evident that the output differs significantly from the results obtained during regular simulation. We can clearly observe the delay caused by flip-flops, and the output resembles that of an OA21 gate's expected output.


![blocking_glsgtk](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/77a20582-1969-4986-a65e-783279e2f9)
</details>
<details>
<summary> Summary </summary>

To prevent these kinds of discrepancies, it's necessary to perform Gate Level Simulation to verify the circuit against expected outputs. This process helps identify any inconsistencies between the circuit's synthesis (the gate-level representation) and its simulated behavior. By running GLS, we can catch any potential mismatches that might arise during the synthesis and simulation stages.

</details>
