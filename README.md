
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

Here are the understandings on Coveats with blocking statements

![Coveats1](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/8186086c-2aab-4e39-a855-b80c88605d59)

![coveats2](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/8d0f672b-5610-4620-bb15-a68e754e0172)
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

# Day 6: Introduction to Logical Synthesis

<details> 
<summary>Logical Synthesis, An Overview
</summary>

 Synthesis : 

Objective of Synthesis:

The core aim of synthesis is to convert a high-level description of a digital circuit, often expressed in a hardware description language (HDL) like VHDL or Verilog, into a gate-level netlist. This netlist consists of logical gates (e.g., AND, OR, NOT), flip-flops, and interconnections, providing a blueprint for how the digital circuit will be physically realized.

Example: For a described  complex algorithm in VHDL for an application-specific integrated circuit (ASIC). Synthesis transforms this abstract algorithm into a synstematic arrangement of gates and flip-flops that can be manufactured.

The process of synthesis is as follows:

1. Translating High-Level to Gate-Level:

Initially, during VLSI design, engineers describe the desired functionality of a circuit in a high-level, abstract manner, without specifying the physical implementation details. Synthesis bridges this gap by mapping high-level constructs (like conditionals and loops) to their equivalent combinations of gates and flip-flops.

Example: If your VHDL code includes a complex if-else statement, synthesis will determine how to construct that logic using fundamental gates and flip-flops.

2. Optimization:

Synthesis tools are equipped with optimization algorithms that aim to enhance the design's performance, area efficiency, and power consumption. They identify redundant logic and simplify the gate-level representation to achieve a more efficient implementation.

Example: Synthesis may recognize that certain gates can be combined or eliminated, resulting in a more compact and faster circuit.

3. Technology Mapping:

During synthesis, the design is aligned with a specific technology library tailored to the manufacturing process (e.g., 28nm, 7nm). This library contains the available gates and flip-flops. The choice of gates from this library significantly impacts the final characteristics of the integrated circuit.

Example: For a 7nm process, synthesis selects gates and flip-flops optimized for this technology to ensure the circuit operates efficiently.

4. Timing Analysis:

Timing analysis is crucial in synthesis, ensuring the design meets vital timing constraints such as setup time, hold time, and clock-to-q delays. The synthesis tool identifies and optimizes critical paths to satisfy these constraints.

Example: If your circuit has a specific clock frequency requirement, synthesis will analyze and adjust the design to meet this frequency.

5. Area and Power Estimation:

Synthesis tools provide estimates of the chip's area utilization and power consumption based on the gate-level netlist. These estimates help designers gauge resource usage and power requirements.

Example: Synthesis might estimate that your design will occupy a certain amount of silicon area and consume a particular amount of power under specified conditions.

6. Constraints and Guidelines:

Designers provide synthesis tools with constraints and guidelines that dictate how the synthesis process should proceed. These constraints encompass clock frequencies, input-output delays, and other design requirements.

Example: If your design must operate within a specific power budget, you'd set power constraints within the synthesis tool.

7. Iterative Process:

Synthesis is often an iterative process. Designers may need to revise the high-level description, adjust constraints, or make changes based on synthesis results to achieve the desired outcome.

Example: After synthesis, you realize that meeting timing constraints requires modifying your HDL code to simplify logic pathways.

8. Output for Further Stages:

The gate-level netlist produced by synthesis serves as the foundation for subsequent stages of the design flow, such as physical design, place-and-route, and ultimately, the manufacturing of the integrated circuit.

Example: The gate-level netlist becomes the basis for configuring the physical layout of the chip in the next stage of the design process.
</details>

<details>
<summary>Design Compiler</summary>
Design Compiler (DC), often abbreviated as DC, stands as a crucial high-level synthesis tool from Synopsys, a premier EDA solutions provider. It holds a central role in the intricate world of integrated circuit (IC) design, serving as an indispensable component of contemporary VLSI design workflows.

Key Terminologies:

1)Synopsys Design Constraints (SDC): These are essential design constraints supplied to DC, enabling precise optimization to achieve the optimal implementation.

2).lib: A Design Library housing Standard cells, pivotal building blocks for IC design. DC recognizes libraries in the .lib format.

3).db: Similar to .lib but presented in a distinct format, DC comprehends libraries in the .db format, broadening compatibility.

4).ddc: A Synopsys proprietary format tailored for storing design information. DC possesses the capability to both generate and parse .ddc files, streamlining data exchange.

5)Design: RTL (Register-Transfer Level) files embodying the behavioral model of the design, serving as the foundation for subsequent IC design stages.

Here is the RTL code for the design that is going to be synthesized.
It cosists of a Mux and a flop with Reset
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/dc_synopsis/lab1_v.png">

The following netlist will be obtained when the libraries are not mapped 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/lab1_synth_gtechf.png">

The below snap shows the netlist after mapping.
The main mappings performed are setting up target and link libraries
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/lab1_syn_netlist.png">

The results after Compile is shown below
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/lab1_compile.png">

Design Vision: Design Vision, a highly utilized tool within Electronic Design Automation, originates from the Synopsys. Its primary role encompasses functions such as logic synthesis and formal verification, serving as a cornerstone in the VLSI design process.

To initiate Design Vision, a series of commands are employed. Firstly, the c shell is activated, followed by the execution of the "design_vision" command.

Upon launching Design Vision, the initial step involves converting the design into a .ddc file format. This crucial transformation is achieved through the "write -f ddc -out <filename_name>" command.
The schematic of the design obtained after reading .ddc file is shown below.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/dv_schematic.png">

Upon double clicking, the entire design with implemented gates will be shown
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/dv_full_schematic.png">

 synopsys_dc.setup: 
 All repetitive tasks which is needed for tool setup can be pointed in this file.
 These need not be set each and every time explicitly 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/dc_setup.png">
</details>

<details>
<summary> tcl Scripting </summary>
Tool command Language (tcl) is a language designed for various purposes, including automation, rapid prototyping, and embedding within other software applications. 

Syntax and Commands
Assigning a variable
~~~ruby
set a 10
ser b 10
set a [expr $a + $b]
~~~
if else condition
~~~ruby

if { condition } {
<statements>
} else {
<statements>
}
~~~
while loop
~~~ruby

while {<condition>} {
/statements
}
~~~
For loop
~~~ruby
for {<looping variable>} {condition} {incr/decr} {
/statements
}
~~~
For each
~~~ruby

foreach var list{
statement
}
~~~
For each with respect to Collection 
~~~ruby
foreach_in_collection var collection {
statement
}
~~~

Difference between collection and list: 

Both "collection" and "list" are data structures used to store and manipulate data. However, they have distinct characteristics and use cases:

Collection:

A collection in TCL refers to a group of items stored together, which can be of different types, including strings, integers, and other data structures like lists.
Collections in DC are often used to represent more complex data structures, such as hierarchical information about the design, including cells and instances.
They are typically accessed using methods and functions specific to Synopsys tools like Design Compiler.

List:

A list in TCL is a basic data structure that stores a sequence of elements.
Lists are commonly used for managing and iterating through simpler data, such as file names, command-line arguments, or strings.
TCL provides a range of built-in commands to manipulate lists, making them a versatile choice for handling sequential data.


tcl Labs:

Variables Assignment
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/set.png">

For Loop
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/for_loop.png">

While Loop
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/while_loop.png">

Foreach in Collection
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/foreach_in_collection.png">

Creating a new sample tcl file
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/sample_tcl.png">

Sourcing the sample tcl file to Print the gates, a small multiplication table and a list as shown.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/dc_synopsis/tcl/source_sample_tcl.png">

</details>

# Day 7 Basic SDC

<details>
<summary> STA </summary>
Static Timing Analysis (STA) plays a pivotal role in the design and verification of digital integrated circuits, ensuring they meet timing requirements and operate reliably.

STA assesses the timing performance of circuits without actual simulation, ensuring signals traverse the circuit within specified time limits, ensuring proper functionality and performance goals.

Delay:

Delay measures the time taken for a signal to travel from one point in a digital circuit to another, impacting performance, power consumption, and reliability.

Max Delay Constraint:

A Max Delay Constraint sets an upper limit on signal propagation delay through a specific path or circuit. For example, in a setup with 2 D flip-flops connected by combinational logic:
Tck >= Tcq + Tcomb + Tst

Min Delay Constraint:

A Min Delay Constraint establishes a minimum allowable delay for signal propagation, preventing signals from propagating too quickly and causing timing violations:
Thold < Tcq + Tcomb

Delay Analogy:

Understanding delay is akin to two buckets being filled by different water inflow rates. This relates to VLSI, where higher inflow (current) corresponds to lower transition delay and bucket size reflects load capacitance.

Cell Delay Function:

A cell's delay depends on input transitions and load capacitance, reflecting how quickly it can process signals.

Timing Arc:

Timing arcs in VLSI design describe the intricate relationship between input and output transitions of logic elements, considering rising/falling edges, setup/hold times, and propagation delays. They are crucial for precise timing analysis.
The difference between the Combinational and sequential timing arcs are mentioned below.

Combinational Timing Arc:

Focus: Combinational timing arcs are concerned with the timing behavior of combinational logic elements, such as gates and multiplexers.
Characteristics: They define the relationship between input transitions (changes in logic levels) and the resulting output transitions within a single combinational logic element.
Propagation Delay: Combinational timing arcs primarily capture the propagation delay of the combinational logic, which is the time it takes for the output to respond to changes in the input.
No Memory: Combinational logic has no memory; it depends solely on the current input values to produce an output.

Sequenctial Timing Arc:

Focus: Sequential timing arcs are specific to sequential elements like flip-flops (registers).
Characteristics: They define the timing behavior of sequential elements in terms of setup time, hold time, and clock-to-q delay.
Setup Time: Setup time refers to the minimum time before the clock edge when data must be stable to ensure proper capture by the flip-flop.
Hold Time: Hold time represents the minimum time after the clock edge during which data must remain stable.
Clock-to-Q Delay: This is the time it takes for the data to propagate from the flip-flop's input (D) to the output (Q) after the clock edge.
Memory Elements: Sequential elements have memory, as they store data from one clock cycle to the next

Unateness:
Unateness refers to a property of a logic function or a Boolean equation that describes how the output of a gate or circuit behaves with respect to changes in the input variables. It characterizes how the output responds to transitions in its inputs, specifically whether it prefers rising (from 0 to 1) or falling (from 1 to 0) transitions or if it doesn't exhibit a preference. Unateness is a concept used in various stages of digital design, including synthesis, optimization, and timing analysis.

There are two main types of unateness:

Positive Unateness:

In a positively unate logic function, the output of a gate or circuit is more sensitive to one input transition than the other.
Specifically, a gate with positive unateness responds faster or more strongly to a particular input transition (either rising or falling) and is less sensitive to the opposite transition.
For example, a gate may exhibit positive unateness for rising transitions, meaning it responds more quickly to input transitions from 0 to 1 than from 1 to 0.

Negative Unateness:

In a negatively unate logic function, the output of a gate or circuit is more sensitive to the opposite input transition compared to the other.
A gate with negative unateness responds faster or more strongly to the input transition it is not sensitive to in the positively unate case.
For example, a gate may exhibit negative unateness for falling transitions, meaning it responds more quickly to input transitions from 1 to 0 than from 0 to 1.

There is also one more type of Unateness called as complex unateness described with respect to pins.
Here certain pins will have positive and others will have negative unateness.

Some important points to remember:
Setup or Hold is always measured w.r.t. Sampling point.

Therfore for Pos DLatch: setup is measured before negedge and hold is measured after negedge.
For Neg D latch: Setup is measured before posedge and Hold is measured after posedge.

</details>
<details>
<summary> Labs on Scripting </summary>

A Timing File (.lib) 
This serves as a text-based repository of essential data related to Standard Cells used in VLSI design. This file encapsulates information about Timing, Area, and Power characteristics. It adheres to a PVT naming convention, signifying Process, Voltage, and Temperature specifications. For instance, "sky130_fd_sc_hd_tt_025C_1v8" implies 130 nm technology, standard process, 25°C temperature, and a 1.8 V voltage.

Key components within the Timing File:

Library and Technology:

The file includes the library name and the technology used. This helps identify the specific set of standard cells and design rules employed.
Units:

The Timing File specifies units for various parameters such as time, power, voltage, current, resistance, and capacitance. This ensures consistency and accurate interpretation of data.
Operating Conditions:

It provides values for the operating conditions, encompassing process variations, voltage levels, and temperature ranges. These conditions include maximum (Max), minimum (Min), and typical values.

Key components within the Timing File:
.lib contains the delay and power information in terms of a Matrix called as look up table. 2 parmeters will be mentioned and the delay or power for all their possible values will be given as shown. In case the value doesnt exist directly in ghe table, the tool takes the nearest values and interpolates it accordingly.

Cell-specific details in the Timing File encompass:

Cell Information:

Cell name is stated, identifying each standard cell.
Area of the cell is outlined, describing the physical space it occupies.
Pin Data:

Details about pins are recorded, including pin names and their functional direction (input, output, etc.).
Information about leakage power concerning input pin logic states is presented.

Pin Characteristics:

Pin-level information covers aspects like internal power consumption, capacitance, and other electrical properties.
Capacitance values for rising and falling transitions are documented.
Fanout load data is included, reflecting how a pin's output affects connected components.


It is observed that as the input transition and load capacitance increases the delay also goes on increasing.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/day_7/lookup_table.png">

The unateness of the cells mentioned in the .lib is shown below
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/4029c5524a4bee7d90d5b81148ecd3415da29d34/day_7/neg_unate.png">


The setup information about the cells will also be mentioned in the .lib. The following snaps show this information 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/setup_rising.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/setup_falling.png">

The pin information will be clearly described for each cell, for the clock pin, the Clock attribute will be true as shown below
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/clock_true.png">

Traversing through the library cells and printing all the cells with 'and'. This shows both and and nand cells.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/and_cells.png">

The below snap represents deriving the pin information for a 2 pin And cell
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/get_libs_and.png">

The same is being shown with respect to 4 pin And cell
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/get_libs_and4.png">

Deriving the Pin information for nand4bb.
The results show that 2 inputs are being barred, hence the name. These types of differences account fir the different flavour of cellls found in .lib
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/get_lib_pins_nand4bb.png">

Deriving the functional Atributes of and4 and nand gate with get_lib_attribute 

Deriving attibutes follows the below syntax
~~~ruby
get_lib_attribute <lib_cell/lib_pin> <attribute_name>
~~~

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/attribute_nand4bb.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/nand_function.png">

Deriving the area and capacitance of cells.
It is observed that the capacitance of clock pin would be higher than other pins as the clock signal will be traveeling multiple places and connected to many elements across the design.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/763dad82f9051dab6e55fc1540134775c50878d3/day_7/get_lib_area.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/763dad82f9051dab6e55fc1540134775c50878d3/day_7/get_lib_capacitance.png">
Creating a new script, in which a list is created and for each cell mentioned in the list, its output pin and functionality is displayed.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/my_script_tcl.png">

On sourcing the script the respective information is being displayed.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9cb4853784dabb74ab8236a53bc1a4841595a1b7/day_7/my_script_run.png">


</details>

# Day 8 Advanced Constraints
<details>
<summary> Clock </summary>
Each timing path in a digital circuit must be controlled and regulated by a clock signal. This regulation involves setting specific parameters for the clock, such as its timing period and waveform characteristics. The clock's period essentially acts as a constraint on the maximum time allowed for the combinational logic to process data, as the other parameters like setup and hold times are defined in the library (.lib) files. Up until the Clock Tree Synthesis (CTS) phase in the Application-Specific Integrated Circuit (ASIC) design process, the clock is assumed to be perfect or ideal. This clock signal is typically generated using components like oscillators, Phase-Locked Loops (PLLs), or external clock sources.

Clock Skew
=========


Skew is the difference in arrival of clock at two consecutive pins of a sequential element. Clock skew is the variation at arrival time of clock at destination points in the clock network. The difference in the arrival of clock signal at the clock pin of different flops.
Two types of skews are defined: Local skew and Global skew.
- Local skew
Local skew is the difference in the arrival of clock signal at the clock pin of related flops.
- Global skew
Global skew is the difference in the arrival of clock signal at the clock pin of non related flops. This also defined as the difference between shortest clock path delay and longest clock path delay reaching two sequential elements.

<img width="710" alt="Screenshot 2023-09-11 at 11 53 00 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/00aadf2e-d798-413c-a1a9-3198622b2ac2">

Clock skew can become a more challenging problem as clock frequency increases, as the margin for error significantly decreases with a higher clock frequency. To minimize clock skew, complex synchronous circuits employ clock distribution networks similar to the one shown in Figure 5. These are often also referred to as clock trees. Each inverter in the clock tree amplifies the clock signal to drive the next level of the clock tree. The goal is to have the clock signal simultaneously arrive at all register inputs.

Skew can be positive or negative. When data and clock are routed in same direction then it is Positive skew. When data and clock are routed in opposite direction then it is negative skew.
Positive Skew improves setup timing but can lead to hold violations. Whereas negative skew can lead to setup violations but can improve hold timings.

Clock Latency
=============

Clock latency is an ideal mode term. It refers to the delay that is specified to exist between the source of the clock signal and the flip-flop clock pin. This is a delay specified by the user – not a real, measured thing. When the clock is actually created, then that same delay is now referred to as the “insertion delay”. Insertion delay (ID) is a real, measurable delay path through a tree of buffers. Sometimes the clock latency is interpreted as a desired target value for the insertion delay.

Clock latency is the time taken by the clock to reach the sink pin from the clock source. It is divided into two parts – Clock Source Latency and Clock Network Latency. Clock Source Latency defines the delay between the clock waveform origin point to the definition point. Clock Network Latency is the delay form the clock definition point to the sink pin. Clock Latency is also called Clock Insertion Delay. Please see the below 2 pictures to get a better understanding of what Clock Latency is.

<img width="788" alt="Screenshot 2023-09-12 at 7 00 40 AM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/0e87a689-9a37-44ce-8081-632883079d76">

Clock Uncertainity
=================

Clock uncertainty is the deviation of the actual arrival time of the clock edge with respect to the ideal arrival time. In ideal mode the clock signal can arrive at all clock pins simultaneously. But in fact, that perfection is not achievable. So, to anticipate the fact that the clock will arrive at different times at different clock pins, the “ideal mode” clock assumes a clock uncertainty. For example, a 1 ns clock with a 100 ps clock uncertainty means that the next clock tick will arrive in 1 ns plus or minus 50 ps.
A deeper question gets into why the clock does not always arrive exactly one clock period later. There are several possible reasons but here will list 3 major ones:
(a) The insertion delay to the launching flip-flop’s clock pin is different than the insertion delay to the capturing flip-flop’s clock pin (one paths through the clock tree can be longer than another path). This is called clock skew.
(b) The clock period is not constant. Some clock cycles are longer or shorter than others in a random fashion. This is called clock jitter which can be contributed from PLL or crystal osillator, cables, transmitters, receivers, internal circuitry of the PLL, thermal noise of the osillator etc. In the case of Pre CTS, since clock tree is not built, uncertainty = skew + jitter . Post CTS uncertainty = jitter .
(c) Even if the launching clock path and the capturing clock path are absolutely identical, their path delays can still be different because of on-chip variation (OCV). This is where the chip’s delay properties vary across the die due to process variations or temperature variations or other reasons. This essentially increases the clock skew.

Jitter
=====

clock jitter is the deviation of a clock edge from its ideal position in time. Simply speaking, it is the inability of a clock source to produce a clock with clean edges. As the clock edge can arrive within a range, the difference between two successive clock edges will determine the instantaneous period for that cycle. So, clock jitter is of importance while talking about timing analysis. There are many causes of jitter including PLL loop noise, power supply ripples, thermal noise, crosstalk between signals etc.



For example:
A clock source (say PLL) is supposed to provide a clock of frequency 10 MHz, amounting to a clock period of 100 ns. If it was an ideal clock source, the successive rising edges would come at 0 ns, 100 ns, 200 ns, 300 ns and so on. However, since, the PLL is a non-ideal clock source, it will have some uncertainty in producing edges. It may produce edges at 0 ns, 99.9 ns, 201 ns etc. Or we can say that the clock edge may come at any time between (<ideal_time>+- jitter); i.e. 0, between 99-101 ns, between 199-201 ns etc (1 ns is jitter). However, counting over a number of cycles, average period will come out to be ~100 ns.

<img width="809" alt="Screenshot 2023-09-12 at 7 06 08 AM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/1490a783-cc95-4e05-b19e-c183019a44b8">

</details>
<details>
<summary> Advanced constraints </summary>
To effectively specify constraints in SDC (Tcl format) for your design, follow these commands:

1. *Querying Ports and Clocks:*
   - To get all ports in the design: `get_ports *`
   - To get a specific port (e.g., clk): `get_ports clk`
   - To get ports with names containing 'clk': `get_ports clk`
   - To get all input ports: `get_ports * -filter "direction == in"`
   - To get all output ports: `get_ports * -filter "direction == out"`
   - To get all clocks: `get_clocks *`
   - To get a specific clock (e.g., clk): `get_clocks clk`
   - To get clocks with names containing 'clk': `get_clocks clk`
   - To get clocks with a period greater than 10: `get_clocks * -filter "period > 10"`

2. *Querying Cell Attributes:*
   - To list all cells (both physical and hierarchical): `get_cells * -hier`
   - To check if a cell is hierarchical (true/false): `get_attribute [get_cells u_combo_logic] is_hierarchical`

3. *Clock Definition:*
   - To create a clock named `<clock_name>` with a period of `<PERIOD>` at a clock generator point (e.g., primary IO pin clk): `create_clock -name <clock_name> -per <PERIOD> [get_ports clk]`

4. *Clock Uncertainty and Latency:*
   - To set clock latency (network delay): `set_clock_latency 3 <clock_name>`
   - To set clock uncertainty (jitter & skew): `set_clock_uncertainty 0.5 <clock_name>`

5. *Waveform Definition:*
   - By default, a 50% duty cycle waveform is defined with rise at 0 and 10 and fall at 5ns. You can customize with `-wave {<starting rise edge> <first fall edge>}`.
6. *Constraining IO Paths:*
   - Input Ports:
     - Set maximum input delay with respect to the clock: `set_input_delay -max 3 -clock [get_clocks <clock_name>] [get_ports IN_*]`
     - Set minimum input delay with respect to the clock: `set_input_delay -min 0.5 -clock [get_clocks <clock_name>] [get_ports IN_*]`
     - Set maximum input transition: `set_input_transition -max 1.5 [get_ports IN_*]`
     - Set minimum input transition: `set_input_transition -min 0.75 [get_ports IN_*]`
   - Output Ports:
     - Set maximum output delay with respect to the clock: `set_output_delay -max 3 -clock [get_clocks <clock_name>] [get_ports OUT_Y]`
     - Set minimum output delay with respect to the clock: `set_output_delay -min 0.5 -clock [get_clocks <clock_name>] [get_ports OUT_Y]`
     - Set maximum output load: `set_output_load -max 80 [get_ports OUT_Y]`
     - Set minimum output load: `set_output_load -min 20 [get_ports OUT_Y]`

</details>

<details>
<summary>Labs</summary>
Here the 'regexp' is used to compare 2 strings and return a boolean value indicating if they are same or not. The below snap represents a script that prints only the CLOCK pins among all the pins.

	
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_regexp_match.png">

The below script shows how to print the referenec name along with the instance name for the components in the design.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/ref%26inst_name.png">

The below snap represents a script taht fetches all the pins with its direction in the design

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8dvpindir_ofn5.png">
After reading the ddc file in Design Vision, the schematic is shown as below.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_schematic.png">

On report_timing, the timing report of the design is seen in which it shows that the design is unconstrained.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/report_timing_before_clk.png">

After creating a clock, <get_clocks *> fetches all the clocks that are present in the design as shown below.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_create_clock.png">

The timing report after creating clock shows that the design's data path is now constrained.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/report_timing_after_create_clock.png">

 IO Delay
 ========
 In digital design, we manage IO delays using commands like set_input_delay and set_output_delay:

set_input_delay:

This command controls when data should reach the input port concerning the clock edge.
Positive delay means data arrives after the clock edge, while negative delay implies data arrives before it.
Use -add for multiple paths and -clock_fall for different clock edges.

set_output_delay:

This command constrains when data should reach the output flop relative to the clock edge.
Positive delay tightens the maximum constraint, while negative delay tightens the minimum constraint.
The -add switch appends constraints.
Constraining IO Paths:

For pure combinational logic, employ set_max_latency or create a virtual clock.
set_max_latency sets a maximum propagation time from one port to another.
A virtual clock, defined with create_clock, helps allocate time for IO paths without an actual clock.

set_driving_cell:

For module-level IOs with similar technology, use this command to model input transitions based on load/fanout.
Specify the library cell name and relevant ports.

The below snap specifies Input delay being added as constraint.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_input_delay.png">

The timing report after specifying the Input/output delay constraints.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/report_timing_after_io_delay.png">

The timing report after specifying input transistion.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_report_timing_afterinput_transition.png">

The timing report after specifying Output external delay

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_reportiming_after_out_delay.png">

The timing report with the capacitance and transition values specified.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_report_timing_withcaptrans_afteriodelay.png">

The timing report after specifying the output load constraints.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/1/lab8_report_timing_after_outload.png">

</details>

<details> 
<summary> Generated Clock </summary>
When dealing with clocks in digital design, it's common for the clock used in the external world and the clock reaching the input module to be physically separate due to long routing distances. These lengthy connections often involve buffer stages, which can introduce delays into the clock network.

To overcome this, we create what's known as a "generated clock" at a different location to ensure logical and physical synchronization. This generated clock is always defined in relation to a "master" clock, which is the primary clock source or the clock signal arriving at the primary IO pins.

Here's the command used to define such a generated clock:
~~~ ruby
create_generated_clock -name MYGEN_CLK -master [get_clocks MY_CLK] -source [get_ports clk] -div 1 [get_ports out_clk]
~~~

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/clock/gen_clk.png">

The timing report displaying the master clock along with the Gen_Clock with all its specifications.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/clock/report_timing_gen_clock.png">

The completely constrained design after sourcing the tcl file containing all the constraints.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/clock/completely_comnstrained_design_tcl.png">
</details>

<details>
<summary> VCLK </summary>
	
Virtual Clock
============
	
A virtual clock is an abstract or imaginary clock signal that is used to specify timing constraints for certain paths or elements in a digital design. It's called a "virtual" clock because it doesn't represent an actual clock signal that drives flip-flops or registers within the design; rather, it serves as a reference for timing analysis.

Eg : For an input signal IN_C and an output signal OUT_Z that are part of a purely combinational logic path. You want to specify that the data from IN_C to OUT_Z should arrive within 1 nanosecond, even though there's no physical clock driving this path. You can define a virtual clock, for example, named "my_vclk," and set timing constraints using this virtual clock:

~~~ruby
create_clock -name my_vclk -period 5
set_input_delay -max 1.5 -clock my_vclk [get_ports IN_C]
set_output_delay -max 2.5 -clock my_vclk [get_ports OUT_Z]
~~~


Creating a virtual Clock as mentioned in the example above

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/3/create_virt_clock.png">

The schematic of the design after the creation of virtual Clock

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/3/schematic_lab14.png">

The below snaps show how the the time violations improved for the given path.
The 2 ways to meet timings are (Set_max_delay and Vclk and the choice depends on the design and designer)

By adding an inverter and Xnor gate the slack is being met. This is also an optimization done by the tool.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/3/slack_violated.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d2c490ebdd83cf5fa1b4eaa5ff4a65a520a4f073/day_8/3/slack_not_violated.png">

</details>

# Day9 Optimizations
<details>
<summary> Optimization techniques </summary>
Optimization goals primarily revolve around achieving the best trade-offs between power consumption, performance, and area utilization. These goals are often conflicting, and optimizing one can negatively impact the others. Cost function-based optimization is commonly employed to balance these objectives. Let's delve into each of these optimization goals and their trade-offs:

1. Power Optimization:
 - Goal: Minimizing power consumption is crucial to extend battery life in portable devices and reduce overall energy consumption.
 - Methods: Techniques like voltage scaling, clock gating, and power gating are used to reduce dynamic and leakage power.
 - Trade-offs: Aggressively reducing power can slow down performance and require larger areas due to the need for power-efficient components.

2. *Performance Optimization*:
- Goal: Enhancing performance aims to maximize the speed and throughput of the VLSI design.
- Methods: Techniques include high clock frequencies, pipelining, and parallel processing to improve performance.
- Trade-offs: Focusing too much on performance can increase power consumption and may require larger chip areas to accommodate complex circuitry.

3. *Area Optimization*:
- Goal: Minimizing chip area is essential to reduce manufacturing costs and allow for integration of more functions on a single chip.
- Methods: Logic optimization, area-efficient circuit designs, and efficient placement and routing can help reduce area utilization.
- Trade-offs: Reducing chip area often results in increased power consumption and can limit the performance due to constraints on component size and complexity.

Some examples of Tradeoff related issues

- *Power-Performance Trade-off*: Aggressively optimizing for power can lead to lower clock frequencies and reduced performance. Conversely, pushing for higher performance may result in increased power consumption.

- *Performance-Area Trade-off*: Achieving higher performance may require more complex and larger circuits, thus increasing the chip area and possibly manufacturing costs.

- *Power-Area Trade-off*: Minimizing power and area simultaneously can be challenging, as low-power designs may necessitate larger transistors or additional components, which can increase area.


COMBINATIONAL


*1. Constant Propagation:*
- Constant Propagation: When one input is made constant in a Boolean expression, the circuit can be simplified. For example, (AB+C)' can be reduced to C', saving area and power.

*2. Boolean Logic Optimization:*
- Karnaugh Maps (K-Maps): K-Maps are graphical tools used to minimize Boolean functions by grouping adjacent minterms or maxterms.
- Quine-McCluskey Algorithm: This method systematically finds the prime implicants of a Boolean function to achieve minimal logic expressions.

*3. Resource Sharing:*
- Multiplexer Optimization: Consider a ternary operator y=sel?ab:cd. Instead of using separate multipliers for a*b and c*d, you can share the same sel condition, reducing area and power consumption.

*4. Logic Sharing:*
- Shared Logic: When multiple gates can use the same intermediate logic, it reduces redundancy. For example, if you have y=a&b&c and z=(a&b)|c, sharing the common AND gate results in a more area and power-efficient design.

*5. Balanced vs. Preferential Implementation:*
- Balanced Implementation: Ensures equal time allocation to all timing arcs. This approach is suitable when all signals have similar timing requirements.
- Preferential Implementation: Gives priority to signals with tight timing constraints, allowing them to have shorter delays. This strategy optimizes for critical paths but may not be energy-efficient for non-critical paths.

*6. Nested Ternary Operator Optimization:*
- Nested Ternary Operators: Simplifying nested ternary operators can significantly reduce logic complexity. For example, optimizing a nested ternary operator with 3 multiplexers can be reduced to an XOR (exnor) gate, leading to area and power savings.

SEQUENTIAL

*Basic Sequential Optimization:*

1. Sequential Constant Propagation:
- Goal: Identify and propagate constants through sequential logic to simplify the design.
- Method: When a flip-flop's D input is connected to a constant value (e.g., high or low), the optimization tool can replace it with a direct connection to Vdd or Vss to save area and power.

2. Retiming:
- Goal: Reorder flip-flops in the design to optimize for critical paths and minimize clock-to-q delays.
- Method: By moving flip-flops across combinational logic, retiming aims to balance the pipeline stages, improve performance, and meet timing constraints.

3. Unused Flop Removal:
- Goal: Eliminate flip-flops that are not contributing to the functionality of the design.
- Method: If a flip-flop's output is unused or redundant, it can be safely removed from the circuit, reducing area and power consumption.

4. Clock Gating:
- Goal: Reduce power consumption by gating the clock signal to flip-flops when their operation is unnecessary.
- Method: Clock gating logic is introduced to enable/disable clock signals to flip-flops based on certain conditions, saving dynamic power.

*Advanced Sequential Optimization:*

1. State Optimization:
- Goal: Optimize the state encoding in finite state machines (FSMs) to reduce area and improve performance.
- Method: Re-encoding the states in an FSM can lead to a more compact representation, reducing the number of flip-flops required.

2. Sequential Logic Cloning:
- Goal: Replicate specific sequential logic elements to meet timing constraints.
- Method: Cloning allows for the duplication of critical flip-flops to ensure that timing requirements are met, even at the expense of area.

*Optimization of Unused Outputs:*

1. Unused Output Optimization:
- Goal: Minimize the generation of outputs that are not used in the design.
- Method: When certain outputs are not required, the optimization tool can eliminate the associated logic and flip-flops, leading to area and power savings.

The use of boolean variables like `compile_seqmap_propagate_constants`, `compile_delete_unloaded_sequential_cells`, and `compile_register_replication` allows  to control these optimization processes. Enabling or disabling these variables helps tailor the optimization to specific design requirements and constraints.
</details>
<details>
<summary> Labs </summary>
The opt_check design has a Multiplexer in its design, but after optimization it reduces into an AND gate and an inverter as shown below.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/opt_check_schematic1.png">

In the design opt_check2.v the ternary operator reduces to an OR gate as shown below
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/optcheck2_2.png">

The optimization reduces the design into a 3input Nand gate as shown below
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/opt_check3_3.png">

In the below snaps, The design shows 3 Multiplexers which after optimization reduces ti just a single Ex-Nor Gate as shown.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/opt_check4_beforeopt_4.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/opt_check4_afteropt_5.png">

The below snaps show how the resource sharing works by reducing the no of cells and accordingly reducing the area.
This also includes the usage of an application variable that is set_max_area.
Here it is restricted to 800 micro metre².


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/resource_sharing_max_area800_7.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/resource_sharing_R1_6.png">

The Schematic after applying delay  to select line
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/resource_sharing_delay_to_sel_7.png">

The schematic showing the usage of tie cells 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/dff_const_tiecellis_shown_9.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/dff-const2_10.png">

Boundary Optimization
==================

Boundary optimization is a vital strategy employed during the logic synthesis phase of chip design to achieve optimal balance in terms of area usage, timing performance, and power efficiency. When implementing boundary optimization, it's possible to realize a notable reduction of approximately 5-10% in the standard cell area, along with a timing enhancement of roughly 2-5%. 

In the synthesis process, an essential decision involves selecting which specific modules or components should undergo boundary optimization and which should remain unaffected. This choice plays a crucial role in fine-tuning the overall design, ensuring that critical areas such as area utilization, timing constraints, and power consumption are optimized to meet the desired specifications.


The below snap shows the schematic without optimization 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/dff_const3_no_opt_11.png">

The below snap shows the schematic when the seq_mapping is set to false.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/dff_const2_seq_map_false_12.png">

The below snaps show the schematic of Boundary optimization when boundary optimization is enabled and set to false  respectively.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/check_boundary_schematic_13.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/check_bound_opt_false_14.png">

Retiming
======
The below snaps show how the retiming concept works; by removing and adding adding logic between other flops where there is availability of slack with corrsponding timing reports.

Retiming is an optimizing algorithm for improving the circuit performance. It moves registers across combo-logic without affecting the functionality of design at primary input/output ports. Registers shall be added and to or removed from the design while performing retiming. However, additional registers do not add clock latency to the design’s performance.
Critical paths are examined along with their non-critical adjacent paths. There shall be many non-critical paths with positive slack. The strategy is to leverage positive slack on one side of a sequential element to balance negative slack on the other. 

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/boundry_schem_16.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/retime_after_15.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/report_timing_after_buff_18.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/report_timing_before_19.png">

Multicycle Path
==============

A Multi-Cycle Path (MCP) in digital circuit design represents a path connecting two flip-flops, where the intermediate combinational logic can introduce delays spanning more than one clock cycle. This design approach allows certain paths to take their time propagating data from source to destination, acknowledging that not all data needs to meet standard single-cycle timing constraints. Unlike false paths, MCPs are valid and must be analyzed, but over multiple clock periods.

In standard timing analysis without MCP constraints, setup checks assess the time for data to travel from a source flip-flop's clock edge to the destination flip-flop's next clock edge, while hold checks ensure data stability within the same clock period. However, with MCPs, the analysis expands to multiple clock periods, recognizing that data on these paths may propagate more slowly but remains valid and reliable for specific design purposes.

The below snaps shows the timing report before considering the multipath cycle.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/mcp_before_timing_20.png">

The below snap shows the timing report after the Multicycle path.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/mcp_after_mcp_21.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/mcp_final_report_after_buff_22.png">

The below snap shows the timing report of the entire design after the multicycle path has been initiated.
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/fe9612408ad4f51dbc5e543d1ba62ce4243ccc6c/day9/mcp_report_0cycle_path_22.png">

</details>

# Day 10 QOR
<details>
<summary> Introduction to QOR</summary>
	
Quality of Results or Quality Checks
===============

Quality checks are integral to the VLSI design and manufacturing process, serving to ensure the reliability and functionality of integrated circuits. These checks are ongoing and iterative, occurring at various stages to guarantee that ICs meet performance, reliability, and manufacturability standards. Advanced simulation and verification tools are frequently employed to automate and streamline these checks.

In the realm of digital electronics and integrated circuits, propagation delay assumes a pivotal role. It signifies the time required for an electrical signal to travel from a digital logic gate's input to its output. Propagation delay, measured in units like nanoseconds (ns) or picoseconds (ps), significantly influences circuit speed and performance. Various factors, such as technology choices, wire lengths, and circuit complexity, impact this parameter.

**Delay**


Rising Edge Propagation Delay (tpdr) characterizes the duration needed for an output signal to change from a low state (0) to a high state (1) following a corresponding transition in the input signal.

On the other hand, Falling Edge Propagation Delay (tpdf) represents the time required for the output signal to shift from a high state (1) back to a low state (0) in response to a similar transition in the input signal.

It's important to note that tpdr and tpdf are not equal because the mobility of electrons and holes, essential components in electronic circuits, differs. This discrepancy in mobility leads to variations in signal propagation times during transitions from low to high and high to low states
 
</details>

<details> 
<summary> report_timing </summary>
The 'report_timing' command in VLSI design is a valuable tool for analyzing the timing characteristics of a digital circuit. It provides essential information about timing paths, including cell delays, signal transitions, capacitance, and slack. By default, 'report_timing' displays setup delay with two significant digits.


**Theoretical Explanation:**

**Timing Analysis Fundamentals:**
- Timing analysis evaluates signal propagation in a digital design to ensure it meets specific timing constraints.
- Key parameters include setup time, hold time, clock-to-q delay, propagation delay, and slack.

**Design Compiler's Role:**
- Design Compiler performs timing analysis and generates reports.
- Helps guarantee correct operation at the desired clock frequency.

**Usage:**

**1. Open Design Compiler:**
- Launch the Design Compiler tool and load your synthesized design.

**2. Compile the Design:**
- Ensure your design is compiled with necessary constraints (e.g., SDC files).

**3. Run Timing Analysis:**
- Use the report_timing command in the Design Compiler command-line interface.

**4. Basic Syntax:**
- `report_timing -from <source> -to <destination>`

**Key Options:**

**-from <source>:**
- Specifies the source signal or path for analysis.

**-to <destination>:**
- Specifies the destination signal or path for analysis.

**-fall_from <source> and -rise_from <source>:**
- Analyze falling or rising edge timing paths from a source.

**-delay_type max/min:**
- Report maximum or minimum delays for timing paths.

**Examples:**

**1. Basic Timing Analysis:**
- Analyze timing from input A to output Z:
  ```
  report_timing -from A -to Z
  ```

**2. Analyze Falling-Edge Timing:**
- Analyze falling-edge timing from input A to output Z:
  ```
  report_timing -fall_from A -to Z
  ```

**3. Report Maximum Delay:**
- Report the maximum delay from input A to output Z:
  ```
  report_timing -from A -to Z -delay_type max
  ```

**4. Maximum Path Analysis:**
- Report the 5 worst-case timing paths in the design:
  ```
  report_timing -max paths -nworst 5
  ```

**5. Specific Path Analysis:**
- Report the single worst-case timing path in the design:
  ```
  report_timing -max paths -nworst 1
  ```

**6. Balanced Path Analysis:**
- Report the top 10 worst-case timing paths:
  ```
  report_timing -max paths -nworst 10
  ```

The above examples showcase various ways to use the report_timing command to analyze and optimize design's timing characteristics. The choice of options and values depends on specific design goals and debugging requirements.

<img width="1109" alt="Screenshot 2023-09-19 at 7 15 40 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/331095b4-d2fe-4d85-a84a-067350bea262">


In a design with multiple sequential elements, such as flip-flops (DFF_A, DFF_B, DFF_C), you may have various timing paths to consider. For instance, there are two critical paths: one from DFF_A to DFF_C with a maximum delay of 1.65ns and another from DFF_B to DFF_C with a minimum delay of 1ns. In this context, 'delay_type max' analyzes the A-to-C path, while 'delay_type min' assesses the B-to-C path.

To ensure proper circuit operation within a specified clock cycle (e.g., 5ns), it's crucial for the clock's rising edge to arrive no earlier than the data signal. This condition ensures a non-negative slack. 'check_design' identifies design inconsistencies, 'check_timing' verifies constraint specifications, and 'report_constraints' assesses design feasibility regarding electrical parameters like power and capacitance.

The 'report_timing -rise_to DFF_C/D' command reports a maximum delay of 1.5ns for the A-to-C path and a minimum delay of 1.15ns for the B-to-C path. Slack, the time margin for meeting setup and hold requirements, is calculated as required time minus arrival time. For setup, the A-to-C path exhibits positive slack of 2.85ns, indicating timing compliance. Similarly, the B-to-C path, in terms of hold requirements, has positive slack of 0.9ns, indicating a met hold condition.

When assessing multiple paths, the 'report_timing -max_paths' command identifies the worst violated path per endpoint. Combining it with 'nworst' helps select the number of paths to report per endpoint, providing a comprehensive view of critical timing issues in the design.

<img width="1266" alt="Screenshot 2023-09-19 at 7 16 46 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/a6c420d6-4876-42d1-a66f-60e5d046086a">

In the design, there are four distinct timing paths to consider, each with its own characteristics. To assess these paths, the '-max_paths' switch is employed, allowing you to retrieve information about the most critical paths in the design. For example, using 'report_timing -max_paths 2' will generate reports for the two most critical timing paths, revealing details like slack values (-1vand -1.2ns).

It's crucial to understand that 'max_paths' focuses on identifying the worst violated path for each specific endpoint, rather than providing an overview of the worst violations across the entire design. To obtain more comprehensive insights into critical timing issues, the 'nworst' switch complements 'max_paths' by specifying the number of worst violated paths to report for each endpoint. This combined approach lets you effectively pinpoint and address critical timing challenges within the design.
</details>
<details>
<summary> Lab </summary>

setup check is being analyzed with report_timing.

points to note, for identifying if the check is for setup
- The path type shown as max
- Slack is reqd time - arrival time
- launch and captire edges are different
- Library setup time is included in the report

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/rep_time1.png">

The fall to rise and rise to fall delay mismatch can be observed between the above snippet and the one below for the same nor gates in the design but for different conditions i.e. Rise and fall

Library setup time for capturing rise and fall are also different.

All these factors add up to show a different delay value altogether as shown 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/rep2.png">

The below snap reports Hold check.
Points to identify it is hold check
- Path type is Min
- Library hold time is mentioned
- slack is reqd - arrival
- The check is happening for same clock cycle.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/rep_hold3.png">

Check_design shows the presence of Feedthrough

Feedthrough
=========

Feedthrough refers to the situation where the synthesis tool generates logic or routing that allows a signal to propagate between unrelated parts of the design, potentially causing unintended interactions and issues.

**Causes of Feedthrough in VLSI Synthesis:**

- Logical Errors: Errors in the RTL (Register Transfer Level) description of the design, such as missing or incorrect constraints, can lead to feedthrough issues during synthesis.
- Insufficient Constraints: Insufficient timing, area, or other constraints provided to the synthesis tool can result in suboptimal or incorrect logic being generated, leading to feedthrough.
- High-Level Abstractions: Sometimes, high-level abstractions or design descriptions may not accurately capture the intended behavior of the design, causing feedthrough to occur.
  
**Mitigation of Feedthrough in VLSI Synthesis:**

- Constraints: Providing accurate and comprehensive design constraints is crucial to guide the synthesis tool in generating the desired logic.
- Static Timing Analysis (STA): Use STA tools to verify and analyze the synthesized design. STA can help identify potential feedthrough issues by analyzing signal paths and timing violations.
- Design Reviews: Conduct thorough design reviews to identify and rectify logical errors or ambiguities in the RTL code.
- Retiming: Retiming is a synthesis optimization technique that can help reduce feedthrough by repositioning flip-flops or registers in the design. It can be used to minimize the impact of feedthrough on critical paths.
- Gate-Level Simulation: Simulate the synthesized design at the gate level to validate its functionality and timing correctness.
- Sequential Equivalence Checking: Use sequential equivalence checking tools to ensure that the synthesized logic behaves equivalently to the original RTL description and does not introduce feedthrough.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/check_design_feedthrough4.png">

In the below schematic we can see the single enable_pin drawing the entire design which is a high fanout pin in the design.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_dv_en_split.png">

check_timing gives the overall picture if the constraints are applied or not.
As seen below, the following end points are not constrained which will be constrained further later.

Note: Clock pins can never be constrained, only frequency of their operation can be changed.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/check_timing5.png">

report_constraint shows all the violations that are occurring on the deisgn 
 The below snao shows the violation of transition, capacitance and leakage power.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/report_constraints6.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/report_constraint.png">


High net fanout can be observed on the enable pin i.e. 128
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_high_fanout.png">
In the below snap we can see the high fanout being reduced to 17 and tge subsequent introduction of buffers in the design.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_after_set_max.png">

set_max_tranistion being applied to the design
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_before_set_transition.png">

After max transition is mentioned, the transition constraint gets nullified as shown.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_transition_after.png">

The timing report that is observed after providing maximum transition is shown below. The transition value is being limited which was earlier mentioning some library value that was fed from .lib
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_trans_met.png">

The final design schematic after the the application of constraints. We can observe that the load on select/enable pin is reduced deastically by the introduction of buffers which drive the subsequent nets.
We can see fhe usage of divide and rule policy, where the fanout on single load pin is divided by the usage of local buffers.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f0293c75dc3300fdd82b952cebf6770a73e009de/day10/en_dv_en_split.png">
</details>
<details>
<summary> Summary </summary>
The key aspects of constraining a design in the context of a synthesis script using TCL (Tool Command Language) in synthesis flow and optimization knobs is as follows:

**1. Clock Constraints:**
   - Clock constraints involve specifying clock sources, clock edges, and clock relationships in the design.
   - Create commands like `create_clock` define clock domains.
   - You can set clock latency and uncertainty using `set_clock_uncertainty`.

**2. Input and Output Constraints:**
   - Input and output constraints ensure proper data arrival and departure times.
   - `set_input_delay` and `set_output_delay` specify timing requirements.
   - Transition and driving cell are set using `set_input_transition` and `set_driving_cell`.
   - `set_load` defines the output load conditions.

**3. Design Metrics Constraints:**
   - Constraints like `set_max_capacitance`, `set_max_transition`, and `set_max_area` define design limits for capacitance, transition times, and area.

**4. Synthesis Flow:**
   - Read the Verilog description of the design.
   - Read the technology library (database).
   - Check the design for issues.
   - Source the constraints file.
   - Check timing constraints after constraint sourcing.
   - Perform the synthesis, often using a high-efficiency compile step.
   - Report constraint violations and area usage.
   - Generate the final netlist.
   
**5. Optimization Knobs:**
   - Boundary Optimization: Adjusting logic near the boundary for better timing.
   - Retiming: Reordering registers to optimize for performance.
   - Constant Propagation: Replacing constants with their values to simplify logic.
   - Unused Flop Removal: Identifying and removing unused registers.
   - Isolate Ports: Separating ports for better timing or area trade-offs.

In a nutshell, TCL scripts are used to specify how a digital design should be synthesized, including timing, clock domains, and optimization strategies. The synthesis flow involves checking, compiling, and reporting, while optimization knobs fine-tune the design for better performance or area efficiency. Proper constraints and optimization can significantly impact the final quality of the synthesized design.
</details>

# Day 11 SOC
<details>
	
<summary> My Phone Processor </summary>

Qualcomm Snapdragon 888 Octa-Core Processor
======

The Qualcomm Snapdragon 888 is a high-end octa-core processor designed for mobile devices. Here are its key architecture and design specifications:

1. **CPU Architecture**:
   - The Snapdragon 888 uses a tri-cluster CPU architecture.
   - It features one high-performance core, three high-performance cores, and four power-efficient cores.

2. **CPU Cores**:
   - 1x Cortex-X1 core clocked at up to 2.84 GHz for maximum performance.
   - 3x Cortex-A78 cores clocked at up to 2.4 GHz for sustained high performance.
   - 4x Cortex-A55 cores clocked at up to 1.8 GHz for power efficiency.

3. **Manufacturing Process**:
   - Built using a 5nm process technology for improved power efficiency and performance.

4. **GPU**:
   - Adreno 660 GPU for graphics processing, offering excellent gaming performance and graphics rendering.

5. **AI and Machine Learning**:
   - Hexagon 780 AI processor with improved AI and machine learning capabilities.
   - 26 TOPS (Trillions of Operations Per Second) AI performance.

6. **Modem**:
   - Integrated X60 5G modem for high-speed 5G connectivity with support for mmWave and sub-6 GHz bands.

7. **Camera Support**:
   - Up to a 200-megapixel single camera or dual 64-megapixel cameras.
   - 8K video recording and playback support.
   - Advanced image signal processing capabilities.

8. **Display Support**:
   - Support for QHD+ displays with up to a 144Hz refresh rate.
   - HDR10+ support for high-quality visuals.

9. **Connectivity**:
   - Bluetooth 5.2, Wi-Fi 6E, and Wi-Fi 6 for fast and reliable wireless connections.

10. **Security**:
    - Hardware-based security features, including a secure processing unit (SPU) for enhanced device security.

11. **Audio**:
    - Qualcomm Aqstic audio technology for improved audio quality.

12. **Charging and Battery**:
    - Support for Qualcomm Quick Charge 5 technology for fast charging.
    - Enhanced power efficiency for longer battery life.

13. **Operating System Support**:
    - Compatible with various Android-based operating systems.
   
</details>

# Day 12 Baby SOC modelling

<details>
<summary>RISCV </summary>
RISC-V is an open-source instruction set architecture (ISA) based on reduced instruction set computing (RISC) principles. It's designed to be highly customizable and adaptable for various computing needs. RISC-V stands out for its openness, allowing anyone to implement it without licensing fees, which has led to its growing popularity in both academia and industry. It has the potential to be used in a wide range of applications, from embedded systems to supercomputers

Main Key stages

1. **Fetch (IF - Instruction Fetch):** In this stage, the CPU fetches the next instruction from memory. The program counter (PC) is used to determine the address of the instruction in memory. The fetched instruction is then stored in an instruction register.

2. **Decode (ID - Instruction Decode):** In this stage, the CPU decodes the fetched instruction. It determines what operation the instruction specifies, which registers are involved, and what immediate values might be needed. This stage also determines the control signals required for subsequent stages.

3. **Register File Read:** The CPU reads the values from the registers specified by the instruction in this stage. It typically involves reading values from two source registers (e.g., Rs1 and Rs2) based on the decoded instruction.

4. **Execute (EX - Execute):** This stage performs the actual operation specified by the instruction. It can include arithmetic operations (e.g., addition, subtraction), logical operations (e.g., AND, OR), and data movement operations (e.g., load, store). The ALU (Arithmetic Logic Unit) is often used for these computations.

5. **Register File Write:** If the instruction involves writing back a result to a register (e.g., Rd), this stage writes the result into the appropriate register in the register file. This is necessary to update the state of the CPU and make the result available for subsequent instructions.

6. **Control Logic:** Throughout all the stages, the control logic manages the flow of data and control signals. It determines when to advance to the next stage, when to stall or flush the pipeline in case of hazards, and when to branch to a different instruction address if a branch instruction is encountered.

The RISC-V architecture is designed to be simple and efficient, which is why it follows a reduced instruction set computing (RISC) philosophy. This means that instructions are generally simple and execute in one clock cycle, which makes it easier to design and implement a CPU based on the RISC-V ISA (Instruction Set Architecture). Additionally, the use of a register file and a pipeline architecture helps improve instruction throughput and performance.
 </details>
 <details>
<summary> Modelling </summary>


In the realm of Very-Large-Scale Integration (VLSI), modeling is the art of crafting abstract representations of electronic circuits and systems destined for integrated circuits (ICs) or chips. The significance of VLSI modeling cannot be overstated as it is the linchpin in the design, simulation, and validation of intricate semiconductor devices and electronic systems.

Within the realm of VLSI design, modeling unfolds as an iterative dance. Designers waltz from high-level concepts to the nitty-gritty particulars, all while making sure that their creation adheres to its specifications, performance benchmarks, and power constraints. The ritual of modeling and simulation is akin to the artist's canvas, with the potential to reduce design flaws, optimize performance, and ultimately usher reliable semiconductor devices into the market.

Now, let's explore the notion of Intellectual Property (IP) in the context of VLSI. In this realm, IP embodies the legal fortress safeguarding the designs, innovations, and creations born out of the semiconductor and integrated circuit (IC) design domain. IP serves as the protector of the investments and inventive endeavors undertaken by designers, semiconductor enterprises, and organizations.

Within the tapestry of VLSI's intellectual property, we spotlight three distinguished models:

RVMYTH Modelling:

RVMYTH, inspired by the open-source RISC-V architecture, is gaining prominence. RISC-V, a moniker denoting "Reduced Instruction Set Computing - Version 5," has captivated the computing world for its open-source ethos and adaptable nature.
RISC-V is the bedrock for crafting bespoke processors tailored to diverse applications, spanning from embedded systems to high-performance computing.
RISC-V offers two cardinal integer variants, known as RV32I (32-bit) and RV64I (64-bit), each orchestrating a symphony of fundamental operations for manipulating integer data.
PLL Modelling:

The Phase-Locked Loop (PLL) emerges as a cornerstone in VLSI design, particularly within the realm of analog and mixed-signal integrated circuits.
PLLs exhibit chameleon-like versatility, finding application in diverse domains. They are the architects of clock generation, frequency synthesis, clock recovery, and more in semiconductor devices.
PLLs, akin to a symphony orchestra, comprise vital components like phase detectors, voltage-controlled oscillators (VCOs), and loop filters.
DAC Modelling:

The Digital-to-Analog Converter (DAC) emerges as a luminary in VLSI, its role akin to translating the binary script into an analog melody.
DACs metamorphose discrete digital values into a continuous analog symphony. They wield the binary baton to conjure specific analog voltages or currents.
The stage for DACs spans a wide spectrum, from telecommunications to audio systems, shaping signals and harmonizing the digital and analog worlds.
In essence, these intellectual property models embody the cornerstone of VLSI design, nurturing innovation and fostering the evolution of advanced electronic devices and systems.


Why RISC is preferred:

Simpler instructions: RISC processors 
Streamlined Instruction Set: RISC processors adopt a concise repertoire of straightforward instructions. This streamlining simplifies the decoding process, enabling swift execution. The elegance of simplicity not only accelerates instruction execution but also eases the burden on hardware, resulting in more efficient processing.

Enhanced Speed: The elegance of simplicity in RISC pays off in terms of speed. RISC processors, unburdened by the complexity of extensive instruction sets, can swiftly fetch, decode, and execute instructions. This streamlined execution engine propels RISC-based systems to achieve faster processing times, making them the go-to choice for applications demanding rapid calculations and responses.

Optimized for Performance: RISC architecture excels in optimizing performance. By focusing on a limited number of instructions that encompass fundamental operations, RISC processors deliver consistently high performance. This makes them well-suited for scenarios where computing power is paramount, such as scientific simulations, real-time data processing, and advanced graphics rendering.

Reduced Power Appetite: RISC processors exhibit an appetite for power that's easier on the grid. Their streamlined instruction set and efficient execution translate into lower power consumption. This virtue is particularly advantageous in the realm of portable and battery-powered devices, where energy efficiency directly impacts battery life.

Scalability: RISC architecture's modularity and simplicity lay a solid foundation for scalability. Designers can easily add specialized instructions or customize processors for specific tasks without overcomplicating the architecture. This flexibility fuels innovation, enabling RISC-based systems to adapt to evolving technological demands.

Compiler-Friendly: RISC's simplicity extends a welcoming hand to compilers. Compilers can readily optimize code for RISC processors, capitalizing on the straightforward instruction set. This synergy between architecture and compiler boosts code efficiency and, consequently, system performance.

Reduced Heat Generation: With lower power consumption and efficient execution, RISC processors generate less heat during operation. This not only prolongs the lifespan of components but also reduces the need for elaborate cooling solutions, contributing to quieter and more reliable systems.

In sum, RISC architecture's benefits lies in its elegant simplicity, which translates into speed, efficiency, and adaptability. These qualities make RISC processors the preferred choice in a multitude of computing applications, from high-performance computing clusters to the palm-sized devices we carry in our pockets.
</details>



<details> 
<summary> DAC and PLL</summary>





 </details>
 
 <details>
<summary> Encoder Task </summary>
	

An 8:3 encoder, also known as a priority encoder, is a digital circuit that encodes one of eight active inputs into a 3-bit binary output code. 

Code of Encoder

	
~~~ ruby
module encoder8_3( input [7:0]y, input en, output reg [2:0]a);

always @(*)
begin
if (en)
case (y)
8'b0000_0001: a=3'd0;
8'b0000_0010: a=3'd1;
8'b0000_0100: a=3'd2;
8'b0000_1000: a=3'd3;
8'b0001_0000: a=3'd4;
8'b0010_0000: a=3'd5;
8'b0100_0000: a=3'd6;
8'b1000_0000: a=3'd7;
endcase
else ;
end
endmodule
~~~

testbench 
~~~ ruby
`timescale 1ns / 1ps
module test_encoder;
reg [7:0]Y;
reg EN;
wire [2:0]A;
encoder8_3 uut(.y(Y), .en(EN),.a(A));
initial
begin
EN=1;
Y=8'h0_1;
#30;
Y=8'h0_2;
#30;
Y=8'h0_4;
#30;
Y=8'h0_8;
#30;
Y=8'h1_0;
#30;
Y=8'h2_0; #30;
Y=8'h4_0;
#30; Y=8'h8_0;
#30; 
$finish; 
end
initial
begin
$dumpfile("encoder_tb.vcd");
$dumpvars;
end
endmodule
~~~


**Breaking down its operation**

1. Inputs:
- 01: 0001
- 02: 0010
- 04: 0100
- 08: 1000
- 10: 0001 0000
- 20: 0010 0000
- 40: 0100 0000
- 80: 1000 0000

2. 8:3 Encoder Operation:
- The encoder prioritizes the highest active input and generates a 3-bit binary output that represents the position of the highest active input.
- The most significant bit (MSB) of the output indicates whether input 80 is active or not.
- The second bit indicates the presence of input 40.
- The least significant bit (LSB) indicates the presence of input 20.

3. Waveform for Inputs:
   To visualize the operation of the 8:3 encoder with the given inputs, you would observe the following waveforms for the inputs and outputs over time (assuming each input is active for a brief moment):
   
- When 01 is active: Output = 001
- When 02 is active: Output = 010
- When 04 is active: Output = 100
- When 08 is active: Output = 1000
- When 10 is active: Output = 1000 (continues from the previous state)
- When 20 is active: Output = 1000 (still continues)
- When 40 is active: Output = 1100 (the 2nd bit becomes 1)
- When 80 is active: Output = 1110 (the 1st bit becomes 1)

This waveform illustrates how the encoder encodes the highest priority active input into a binary output code, with the most significant bit representing the highest priority input and the least significant bit representing the lowest priority input.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/encoder_gtk.png">
</details>

<details>
<summary> Labs </summary>

DAC
==

The below snap shows the Verilog and corresponding testbench of Digital to analog Converter and its GTKWave observed after simulation.

Commands
~~~ruby
iverilog avsddac.v avsddac_tb_test.v
./a.out
gtkwave avsddac_tb_test.vcd
~~~

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/dac_v.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/dac_tb.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/dac_gtk.png">

rvmyth
==

The rvmyth processor operates as a RISC-V processor with a five-stage pipeline, consisting of fetch, decode, read, execute, and write stages. At its output, it produces 10-bit digital codes. Its primary function is to perform addition by incrementing a 10-bit binary value by 1, with the 11th bit reserved for a sign flag. When the sign flag is set, it begins counting down instead of up.
The below snaps show the GTKWave of the RVMyth processor

Commands
~~~ruby
iverilog mythcore_test.v tb_mythcore_test.v 
./a.out
gtkwave tb_mythcore_test.vcd
~~~


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/mythcore_gtk_reset.png">




<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/mythcore_gtk.png">

Pll
==

The below snaps show the GTKwave of Pll after simulation which is the clock generator in the design.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/pll_gtk.png">

rvmyth interfaced with dac
===

The below snap shows the simulation of the rvmyth interfaced with DAC Block.


Commands
~~~ruby
verilog rvmyth_avsddac.v rvmyth_avsddac_TB.v
./a.out
gtkwave rvmyth_avsddac.vcd
~~~


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/rv_dac_int.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/rv_dac_int_gtk.png">



rvmyth interfaced with pll
==

The below snap shows the simulation after the integration of Rvmyth with PLL. In the first snap we can observe how the 2 designs under test merge to give the resultant design.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/rv_pll_int.png">




<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/rv_pll_int_gtk.png">

VSDSOC
===

The simulation of the final Top module:
rvmyth with PLL and DAC integrated together is shown below.


Commands
~~~ruby
iverilog vsdbabysoc.v testbench.v avsdpll.v avsddac.v mythcore_test.v
./a.out
gtkwave dump.vcd
~~~

This snap shows all the blocks as unit under tests.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/vsd_full.png">

The below snap shows the final simulation.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/56885b0215f657d90e4cc5fdb4c23a5f4346e908/day12/vsdsoc_gtk.png">

</details>

# Day 13 Post Synthesis Simulation

<details>
<summary> Introduction </summary>

	
**Synthesis** refers to the process of translating a high-level hardware description of a digital circuit into a lower-level representation that consists of gates, flip-flops, and interconnections. It's a critical step in the design flow when moving from an abstract design description (usually in RTL - Register Transfer Level) to a form that can be physically implemented in hardware.

**Pre-Synthesis**:

- **Necessity**: Pre-synthesis refers to the design verification and simulation that occurs before the synthesis process. It's necessary for several reasons:
  - To ensure that the high-level behavioral description (e.g., RTL) of the design functions correctly according to the desired specifications and requirements.
  - To catch and rectify design errors and functional issues at an early stage when they are relatively easier and less costly to fix.
  - To validate that the design meets its functional goals before investing time and resources in the synthesis process.


**Gate Level Simulation**
===


Gate-level simulation is a crucial step in the digital design and verification process. It involves simulating a digital circuit at the gate level, meaning that the simulation models individual logic gates, flip-flops, interconnections, and their timing characteristics. Here's why gate-level simulation is necessary:

**1. Realistic Representation:**
   - Gate-level simulation provides the most detailed and realistic representation of a digital circuit, as it takes into account the actual gates and flip-flops used in the design.
   - It accounts for gate delays, which are the time it takes for signals to propagate through logic gates, ensuring that the simulation mirrors real-world behavior accurately.

**2. Timing Analysis:**
   - Gate-level simulation is essential for timing analysis, which includes checking critical aspects like setup time, hold time, clock-to-q delays, and propagation delays.
   - Timing analysis ensures that signals in the circuit meet their timing requirements, which is crucial for stable and reliable operation.

**3. Verification of Physical Implementation:**
   - It allows designers to verify that the physical implementation (layout) of the circuit, which consists of actual gates on an integrated circuit (IC), matches the intended behavior.
   - Any mismatches or issues between the logical design and the physical implementation can be detected and corrected.

**4. Identification of Glitches and Hazards:**
   - Gate-level simulation can uncover hazards and glitches in the circuit, which are transient issues that can lead to incorrect behavior in certain conditions. Detecting and addressing these issues is essential for reliable operation.

**5. Debugging and Troubleshooting:**
   - During the design process, gate-level simulation helps identify and debug logic errors, race conditions, or other issues that may not be apparent at higher abstraction levels.
   - It provides detailed insights into the circuit's behavior, aiding in the resolution of design problems.

**6. Full Circuit Verification:**
   - It verifies the entire digital circuit, including its combinational and sequential logic, to ensure that it functions correctly under various input conditions.
   - It verifies that the circuit meets its functional requirements and behaves as expected.

**7. EDA Tool Validation:**
   - Gate-level simulation is used to validate Electronic Design Automation (EDA) tools like synthesis, place-and-route, and physical design tools. By comparing simulation results before and after these tools are applied, designers can ensure that the tools are working correctly.

In summary, gate-level simulation is necessary because it provides a detailed and accurate representation of a digital circuit's behavior, including timing aspects, and helps ensure that the circuit meets its functional requirements and operates reliably in real-world conditions. It is a critical step in the design and verification process to identify and address issues before physical implementation, reducing the risk of costly errors in integrated circuits.

**Post Synthesis**
===

This phase comes into play after the high-level RTL (Register-Transfer Level) design has been transformed into a gate-level representation. Here, the focus shifts to a series of intricate tasks and actions, all geared toward fine-tuning and enhancing the design. The goal is clear: ensure that the design aligns with stringent performance, area, and power constraints, ultimately bringing forth an optimized and efficient digital circuit ready for the next stages of the design flow.

- **Necessity**: Post-synthesis occurs after the design has been synthesized into gates and interconnections. It's necessary for these reasons:
  - To verify that the synthesis tool has correctly translated the high-level RTL description into a gate-level implementation without introducing errors or altering the design's intended functionality.
  - To ensure that the design still meets its functional requirements and constraints after the synthesis process.
  - To identify any issues related to gate-level delays, timing violations, or other issues that may arise during physical implementation.

**Matching Pre and Post Synthesis**:

Ensuring that pre-synthesis and post-synthesis results match is essential for several reasons:

1. **Functional Verification**: If pre-synthesis and post-synthesis results don't match, it indicates a potential issue in the synthesis process. Ensuring that they match confirms that the synthesis tool has accurately transformed the high-level design into gate-level implementation while preserving functionality.

2. **Error Detection**: Mismatches between pre and post-synthesis simulations can reveal issues introduced during synthesis, such as incorrect logic transformations, optimization errors, or improper handling of design constraints. Addressing these issues early in the design process is crucial for preventing costly downstream problems.

3. **Confidence in Implementation**: Matching results provide confidence that the final hardware implementation will behave as expected and meet its functional requirements. It minimizes the risk of discovering functional errors in the physical hardware, which can be time-consuming and costly to fix.

In summary, pre-synthesis verifies the design's high-level functionality, while post-synthesis ensures that the synthesis process has correctly translated the design into gates and interconnections. Ensuring that pre and post-synthesis results match is vital for detecting and resolving errors, validating the synthesis process, and building confidence in the correctness of the final hardware design.
</details>
<details>
<summary> Encoder </summary>
	
Synthesis of Encoder using DC shell:
The following are the sequence of steps:

~~~ruby
set target_library <path_of_the_target_library>
set link_library {* <path_of_the_target_library>}
read_verilog <file_name.v>
link
compile_ultra
~~~
The schematic seen after the design is loaded and observed in design vision is shown below.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/day%2013/encoder_schematic.png">

The Encoder output discussed in the pre-synthesis simulation matches the post-synthesis simulation output. The following are the sequence of steps for simulating the output:

~~~ruby
iverilog <netlist_file_name> <testbench>
./a.out
gtkwave <vcd_file_name>
~~~

The 'iverilog' command uses the gate-level netlist obtained after syntehsis and the same testbench for post-synthesis simulation. Running './a.out' generates a VCD format file corresponding to the netlist, which can be viewed using 'gtkwave'. 
The gtkwave simulation observed post synthesis is shown below.

There is a clear match between pre-syntheiss and post-synthesis simulation.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/day%2013/encoder_post_synth_gtk.png">

</details>

<details> 
<summary> BabySoc </summary>
Among the three Intellectual Properties (IPs), namely RVMYTH, DAC, and PLL, only RVMYTH is synthesizable. Consequently, the synthesis process is performed exclusively on the RVMYTH IP. The following commands outline the steps for synthesizing this block:

 ~~~ruby
set target_library <path_of_target_library>
set link library { * <path_of_target_library> }
read_verilog mythcore_test.v
link
compile_ultra
write -f verilog -output rvmyth_core_test.v
~~~

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/day%2013/mymyth_gtk1.png">

The functionality of the design remains consistent with the pre-synthesis stage. It continues to compute the sum of the first n natural numbers up to 1000 and then decrements in the same manner, reflecting a seamless transition from the pre-synthesis behavior to the post-synthesis phase.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/day%2013/mymyth_gtk2.png">

After this synthesis process, the simulation results can be analyzed to ensure that the design meets its functionality requirements as both pre synthesis and post synthesis waveforms are matching, confirming the successful synthesis of the RVMYTH IP.

The below waveform representats the simulation results of the entie VSDBABYSOC after synthesis.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/day%2013/vsd_top_gtk.png">

</details>



 
# DAY 14 Synopsys DC and Timing Analysis

<details>
<summary> PVT </summary>
PVT corners, or Process-Voltage-Temperature corners, are fundamental considerations in VLSI (Very Large Scale Integration) design. They account for the varying conditions integrated circuits might encounter during their operation, and understanding these corners is essential for achieving optimal chip performance, power efficiency, and reliability.

1. **Process Corner**:
   - *Process Variations*: Semiconductor manufacturing processes inherently introduce variations in transistor characteristics, including threshold voltage, mobility, and oxide thickness.
   - *Process Corners*: Designers define three primary process corners:
     - **Nominal (N)**: Represents the typical or ideal process conditions.
     - **Fast (F)**: Reflects conditions where transistors are faster with lower threshold voltages.
     - **Slow (S)**: Represents conditions where transistors are slower with higher threshold voltages.

2. **Voltage Corner**:
   - *Voltage Variations*: Integrated circuits can operate at different supply voltages, affecting speed and power consumption.
   - *Voltage Corners*: Designers consider three voltage corners:
     - **Low Voltage (LV)**: Indicates operation at the lowest allowable supply voltage.
     - **Nominal Voltage (NV)**: Represents the standard supply voltage.
     - **High Voltage (HV)**: Indicates operation at the highest allowable supply voltage.

3. **Temperature Corner**:
   - *Temperature Variations*: Temperature fluctuations impact transistor performance due to changes in electron and hole mobility.
   - *Temperature Corners*: Designers account for temperature variations with:
     - **Low Temperature (LT)**: Signifies operation at the lowest expected temperature.
     - **Nominal Temperature (NT)**: Represents the standard operating temperature.
     - **High Temperature (HT)**: Indicates operation at the highest expected temperature.

**Importance of PVT Corner in VLSI**:
   - PVT corner analysis is vital to ensure reliable chip operation under diverse conditions.
   - It identifies worst-case scenarios where the chip might fail to meet performance, power, or reliability requirements.
   - PVT corners help designers optimize circuits for a balance of performance, power efficiency, and reliability.
   - PVT-aware designs are essential for robust integrated circuits, particularly in critical sectors like automotive, aerospace, and medical devices, where reliability is paramount.
</details>

<details>
<summary> LABS </summary>

Here are the steps to perform the series of tasks for different PVT corners :

1. **Clone the Repository and Handle .lib Files**:
   - Clone the GitHub repository at https://github.com/Geetima2021/vsdpcvrd.git.
   - For each .lib file in the repository, remove lines that contain errors.

2. **Load the LC Shell and Convert to .db**:
   - Launch the LC shell.
   - Use the following commands:
     - `read_lib <library_name>` to load the library.
     - `write_lib <library_name> -f db -o <name_of_the_db_file>` to convert it into a .db file.

3. **Generate a Constraint File**:
   - Set time units to nanoseconds using `set_units -time ns`.
   - Create a clock definition named "MYCLK" with a period of 2 ns for a specific pin (pll/CLK) using `create_clock`.
   - Set clock latency to 1 time unit for "MYCLK" with `set_clock_latency`.
   - Define setup and hold clock uncertainties for "MYCLK" using `set_clock_uncertainty`.
   - Set input and output delays and transitions using `set_input_delay`, `set_output_delay`, and `set_input_transition`.
   - Limit the maximum area to 800 units with `set_max_area`.
   - Set load and max/min values for inputs and outputs using `set_load` and `set_input_delay`.

4. **Set Required DB Files and Compile**:
   - Specify the target library as a combination of "<sky130_PVT_corner>", "avsddac.db", and "avsdpll.db".
   - Link the library with `set link_library`.
   - Read the Verilog design file "vsdbabysoc.v".
   - Link the design with `link`.
   - Load the previously created constraint file with `source <constraints_file_name>`.
   - Compile the design using `compile_ultra`.

5. **Report Quality of Results (QoR)**:
   - Generate a report to assess the quality of the results with `report_qor`.

These steps are essential for configuring and compiling a VLSI design using specific libraries, constraints, and tools.

The snippets of results after the above mentioned steps, are mentioned below for the specific PVT corner.

sky130_fd_sc_hd__ff_100C_1v65 

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_100C_1v65_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_100C_1v65_2.png">

sky130_fd_sc_hd__ff_100C_1v95

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/2251a148581c3726f2bf9768e3c4dbb452d91d80/DAY14%3E%3E/ff_100C_1v95_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/2251a148581c3726f2bf9768e3c4dbb452d91d80/DAY14%3E%3E/ff_100C_1v95_2.png">

sky130_fd_sc_hd__ss_100C_1v40

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_100C_1v40_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_100C_1v40_2.png">

sky130_fd_sc_hd__ss_100C_1v60

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_100C_1v60_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_100C_1v60_2.png">

sky130_fd_sc_hd__ff_n40C_1v56

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v56_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v56_2.png">


sky130_fd_sc_hd__ff_n40C_1v65

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v65_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v65_2.png">

sky130_fd_sc_hd__ff_n40C_1v76

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v76_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ff_n40C_1v76_2.png">

sky130_fd_sc_hd__ss_n40C_1v28

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v28_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v28_2.png">


sky130_fd_sc_hd__ss_n40C_1v35

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v35_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v35_2.png">

sky130_fd_sc_hd__ss_n40C_1v40

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v40_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v40_2.png">

sky130_fd_sc_hd__ss_n40C_1v44

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v44_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v44_2.png">

sky130_fd_sc_hd__ss_n40C_1v76

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v76_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/ss_n40C_1v76_2.png">


sky130_fd_sc_hd__tt_025C_1v80

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/tt_025C_1v80_1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/bff3c58b0c23c639be9f29a91e0b21585f2955a8/DAY14%3E%3E/tt_025C_1v80_2.png">
</details>

<details>
<summary> Tables and Graphs </summary>
	
The table for all WNS and TNS in setup condition is shown below:

	
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/b24c1c6b93c69513fff5fc5811f9ccae23ebaecb/DAY14%3E%3E/setup%20%20table.PNG">



The table for all WNS and TNS in Hold conditions is shown below:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/b24c1c6b93c69513fff5fc5811f9ccae23ebaecb/DAY14%3E%3E/Hold%20table.PNG">
 
The snapped graphs generated for all the PVT corners for setup and Hold are mentioned below.


WNS SETUP
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e6d1e4c7918bbbf7b5a822ef82d321c93c906f6d/DAY14%3E%3E/wns_setup_graph.PNG">

TNS SETUP

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e6d1e4c7918bbbf7b5a822ef82d321c93c906f6d/DAY14%3E%3E/tns_setup_graph.PNG">

WNS HOLD

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e6d1e4c7918bbbf7b5a822ef82d321c93c906f6d/DAY14%3E%3E/wns_hold_graph.PNG">

TNS HOLD

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e6d1e4c7918bbbf7b5a822ef82d321c93c906f6d/DAY14%3E%3E/tns_hold_graph.PNG">
</details>

<details>
<summary> Summary and Understanding </summary>

1. **Hold Violations in Faster Cells**:
   - Faster cells, often referred to as "fast corners" in semiconductor design, have transistors with lower threshold voltages and faster switching speeds.
   - Hold time is the minimum amount of time data must be stable before the clock signal arrives.
   - In faster cells, data changes quickly, and it may not meet the required hold time, leading to hold violations.
   - These violations occur when the data changes too close to the clock edge, potentially causing incorrect data to be latched.

2. **Setup Violations in Slower Cells**:
   - Slower cells, known as "slow corners," have transistors with higher threshold voltages and slower switching speeds.
   - Setup time is the minimum time data must be stable after the clock signal arrives.
   - In slower cells, data changes relatively slowly, and it may not meet the required setup time, leading to setup violations.
   - These violations happen when data changes too late after the clock edge, potentially causing incorrect data to be captured.


The most critical corner in terms of setup timing is the "ss_n40C_1v28." Ensuring that setup requirements are met at this corner essentially guarantees that setup timing will be satisfied at all other corners as well. Meeting the setup criteria at this specific corner acts as a benchmark for the entire design.

On the other side, the most favorable PVT corner is the "ff_n40C_1v76." This corner exhibits no setup violations and only minimal hold violations. In other words, it represents the best-case scenario for timing performance, ensuring that the design operates optimally with excellent setup timing and minimal issues related to hold timing across different process, voltage, and temperature corners.


In summary, faster cells are prone to hold violations because they process data quickly, potentially violating the minimum hold time requirement. Slower cells are more susceptible to setup violations because they change data relatively slowly, potentially missing the minimum setup time requirement. Designers must carefully analyze and address these timing issues to ensure proper operation of digital circuits.
</details>

# Day 15 Inception of EDA and PDK
<details>
<summary> Introduction </summary>

A chip (integrated circuit) is typically mounted on a printed circuit board (PCB) to create a functional electronic system.

 <img width="799" alt="Screenshot 2023-10-03 at 6 55 52 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/b739bc5d-5a9e-48af-9b09-93d8a80a3de3">

The complete system is represnted as shown below

<img width="1146" alt="Screenshot 2023-10-03 at 6 55 28 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/9cbb2935-6bf8-4414-8d9a-edcaece504ef">


*Die:*
The term "die" refers to the individual silicon wafer that contains the integrated circuit. In the semiconductor manufacturing process, multiple copies of the same integrated circuit are fabricated on a single silicon wafer. Each of these copies, when separated from the wafer, is called a "die." Each die represents a single instance of the SoC design.

*Pad:*
Pads are the physical external connections or terminals on the SoC. These are the points through which the SoC interfaces with the external world, such as input and output pins for connecting to other electronic components, power supply pins, ground pins, and so on. Pads are typically located around the perimeter of the die and are used for soldering or connecting wires to the SoC.

*Core:*
The "core" in an SoC refers to the central processing unit (CPU) or the primary processing element of the chip. It is the heart of the SoC and typically consists of one or more CPU cores, along with other essential components like memory, caches, and various hardware accelerators. The core is responsible for executing instructions, running software, and performing computations.

- The "die" is the physical silicon wafer containing the integrated circuit.
- "Pads" are the external connection points on the chip.
- The "core" is the central processing unit and primary computing component of the SoC.

This particular component is housed in a QFN-48 package, which stands for Quad Flat No Leads and has 48 pins. Each of these pins serves as a connection point that interfaces with other components or packages on the design board. The package itself measures 7mm by 7mm in size. At the heart of this package, there is typically a microchip positioned in the center. The pins on the periphery of the package, often referred to as "outbounds," play a crucial role in facilitating the exchange of data between the external world and the chip contained within the package. 

<img width="920" alt="Screenshot 2023-10-03 at 6 47 28 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/fc0e5c3b-1d94-4b20-8c1b-624a568f93de">




The journey from system architecture to layout design involves a sequence of steps where application software, the operating system, and various software tools collaborate to compile, convert, link, and synthesize the design into a netlist that represents the integrated circuit.

<img width="1565" alt="Screenshot 2023-10-03 at 6 48 38 PM" src="https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/456f8778-7a54-4d96-8a1f-7c18dee217f2">

</details>

<details>
<summary> RTL2GDS </summary>

The RTL2GDS flow is a series of steps that starts with the initial RTL (Register Transfer Level) design and concludes with the creation of the final layout in GDSII format. This entire process relies on a Process Design Kit (PDK) for guidance.

*Synthesis*

Synthesis is a crucial step within this flow. It involves converting the RTL description into a circuit composed of components from the standard cell library (SCL). The output of this step is a gate-level netlist, described in HDL (Hardware Description Language), which is functionally equivalent to the original RTL.

Standard cells are fundamental building blocks used in this process. They have a regular layout, and each cell is represented in various views or models, including electrical, HDL, and SPICE. Additionally, there are abstract and detailed layout views available for standard cells. These standard cells play a pivotal role in constructing the final layout of the integrated circuit.

*Floor Planning and Power Planning*

1. Chip Floor Planning:
   - Chip floor planning involves dividing the chip's physical area into sections for various system components and arranging input/output pads.
   - It's about how to allocate space on the chip for different functions and where to position the connection points.

2. Macro Floor Planning:
   - Macro floor planning entails determining the size, positions of pins, organization of rows, and specifying macro properties.
   - It focuses on defining the dimensions and layout of large functional blocks within the chip.

3. Power Planning:
   - Power planning revolves around ensuring that every component in the design receives the required power supply.
   - Typically, the distribution of power is achieved through the use of upper metal layers due to their thicker conductivity compared to lower metal layers.

*Placement*

1. Placement:
   - Placement involves the task of arranging cells within predefined rows on a floor plan, aligning them with specific sites.
   - It's the process of determining a suitable physical location for each cell within a chip block.

2. Macro Placement:
   - During macro placement, gate-level netlist cells are positioned on designated rows, with a focus on minimizing the distance between cells to reduce interconnect delays and facilitate efficient routing.
   - This placement process typically occurs in two main stages:

   - Global Placement: In this initial stage, cells are placed within the core area with consideration for timing and congestion, aiming to generate a rough placement solution. This may occasionally violate certain placement constraints but provides a global perspective of the entire netlist.
   - Detailed Placement: Following global placement, the positions of cells are minimally adjusted to fine-tune their locations while retaining the overall structure established during the global placement.

*CTS*


1. Clock Tree Synthesis (CTS):
   - CTS is the stage in chip design where the clock signal is routed before the primary routing process begins.
   - Its primary goal is to establish a clock distribution network.

2. Creating a Clock Distribution Network:
   - CTS involves setting up a network that efficiently carries the clock signal to all sequential elements, typically Flip Flops.
   - The aim is to minimize any timing variations or skew in the clock signal distribution, although achieving zero skew is extremely challenging.

3. Achieving a Good Shape:
   - During CTS, the clock distribution network is designed to have a favorable structure.
   - This structure often takes the form of a tree, which can be configured in different shapes, such as an H or X, depending on the design requirements.


*Routing*

   - Routing is the phase in chip design where the interconnections are realized using the available metal layers.
   - These metal layers act as tracks on a grid, and due to the vast grid size, a divide-and-conquer approach is typically used.

1. Global Routing:
   - Global routing involves creating routing guides or high-level plans for how the interconnections should be established.
   - It's a preliminary stage that lays out the general path for the wiring.

2. Detailed Routing:
   - In detailed routing, the routing guides generated during global routing are used to execute the actual wiring of the interconnects.
   - It's the step where the specific paths and connections are implemented based on the earlier plans.

*Sign-off*
   - Sign-off refers to the final stage in chip design where the completed layout undergoes rigorous verifications to ensure its integrity and functionality.

 Physical Verifications:
   - This step involves several checks:
     - Design Rule Checking (DRC) ensures that the layout complies with all design rules and constraints.
     - Layout vs. Schematic (LVS) compares the final layout with the gate-level netlist to confirm consistency.
     - Timing Verification is crucial for Static Timing Analysis (STA), which guarantees that timing constraints are met, and the circuit will operate at the designated        clock frequencies.


</details>

<details>
<summary> Open Lane Flow  </summary>
	
OpenLANE, the tool used in this flow, is built upon various open-source projects such as OpenROAD, KLayout, Yosys, QFlow, ABC, Magic VLSI Layout Tool, Fault, and more. It leverages these tools to automate and streamline the design process.

1. Synthesis Exploration:
   - Synthesis exploration is a utility used to generate reports that display the design's delay and area characteristics.
   - It helps identify the most suitable design strategy to proceed with by analyzing these reports.
   - Additionally, it can be used to sweep through various design configurations and create reports, which are then observed to ensure that the final layout meets requirements.

2. Design for Testability (DFT):
   - After synthesis, DFT steps prepare the design for testing before fabrication (optional).
   - These steps include:
     - Scan Insertion
     - Automatic Test Pattern Generation (ATPG)
     - Test Patterns Compaction
     - Fault Coverage Analysis
     - Fault Simulation

3. Physical Implementation (Automated PnR):
   - Physical implementation, often referred to as Automated Place and Route (PnR), is conducted using open-source tools like OpenRoad.
   - It encompasses various steps:
     - Floor and Power Planning
     - End Decoupling Capacitors and Tap Cells Insertion
     - Placement (Global and Detailed)
     - Post Placement Optimization
     - Clock Tree Synthesis (CTS)
     - Routing (Global and Detailed)
     - Logic Equivalent Check (LEC) to ensure functionality consistency after netlist modifications.

4. Dealing with Antenna Rules Violations:
   - A specific phase during physical implementation addresses Antenna Rules Violations.
   - It involves inserting Antenna Diodes to mitigate issues caused by long metal wire segments acting as antennas, which can accumulate charge and potentially damage transistor gates during fabrication.
   - Solutions include bridging and adding antenna diode cells.

5. Static Timing Analysis (STA):
   - STA involves several steps, including RC extraction (from .def to .spef format) and the use of tools like OpenSTA (within OpenROAD).
   - It generates timing reports to check for violations in timing paths and ensure that the design meets its timing constraints.

6. Physical Verification (DRC & LVS):
   - Magic is utilized for Design Rule Checking (DRC) and SPICE Extraction from Layout.
   - Netgen, along with Magic, is employed for Layout vs. Schematic (LVS) checks, comparing the extracted SPICE data from Magic with the Verilog netlist.


</details>

<details>
<summary> Labs </summary>

1. Skywater PDK Files:
   - The "Skywater-pdk" directory holds various files related to the PDK (Process Design Kit) provided by the foundry.
   - "Open_pdks" contains scripts that bridge the compatibility gap between closed-source and open-source PDKs for Electronic Design Automation (EDA) tools.
   - "Sky130A" contains open-source compatible PDK files, ensuring accessibility for open-source EDA tools.
  
     
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/Skywater_PDK_Files.png">


2. Invoking OpenLane:
   - To utilize OpenLane, you use a script named "flow.tcl" that manages the entire OpenLANE flow.
   - OpenLane can be run interactively or autonomously.
   - For interactive usage, you can employ the "-interactive" option with the "./flow.tcl" script.


     
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/invoking_openlane.png">

Importing the Package :



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/package_imporing.png">

The design Hierarchy is shown in the below snap:



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/design_hierarchy.png">

Preparing Design:
   - The "prep" phase sets up the file structure for your design within OpenLane.
   - After running it, you'll find a new directory structure created in the "openlane/design/picro32a" folder, specifically under the "runs" subdirectory.
   - This directory structure enables the OpenLANE flow for your design.

 *Configuration File*
   - The "config.tcl" file located in the design's directory contains all the parameters used by OpenLANE for a particular run.
   - This file specifies various settings and options that govern the behavior of the OpenLANE flow for your specific design.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/prepare_design_1.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/prep_design_2.png">


*Merging Technology and Cell Information*
   - During the preparation of the design in OpenLANE, the tool combines technology-specific LEF (Library Exchange Format) information with cell LEF data.
   - Technology LEF includes layer definitions and essential design rules crucial for Place and Route (PnR) flow.
   - Cell LEF contains obstruction information for each standard cell, which helps minimize Design Rule Checking (DRC) errors during the PnR process.
     
This is shown in the below snaps.
     
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/merging_lef.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/master/Day%2015/run_synthesis.png">


To calculate the percentage of flip flops:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/641334e69ad026c3ba430a4dbc3065448c9aa5a1/Day%2015/ff_percentage.png">

Total number of d flip flops = 1613

Total Number of cells = 14876

D flip flop ratio is given by = 1613/14876 = 0.108429

Hence the Percentage is => 10.8429%
 
</details>

# Day 16 Good and Bad Floorplan

<details>
<summary> Utilization factor </summary>


1. **Core and Die Dimensions**:
   - In chip design, the dimensions of the core and the die are determined by the cumulative area of the standard cells and flip-flops present in the design.
   - For instance, if we assume that each standard cell and flip-flop occupies 1 square unit of area, the minimum area required for the netlist would be 4 square units.

2. **Core Definition**:
   - The core of a chip is the specific region where the essential logic components of a design are placed.
   - It serves as the primary area for housing the fundamental circuitry.

3. **Die and Encapsulation**:
   - A die, which includes the core, is a small semiconductor material where the primary circuit is fabricated.
   - The core is encapsulated within the die, ensuring that the key logic elements are contained within this boundary.

4. **Utilization Factor**:
   - The utilization factor is a critical metric, denoting the proportion of the core's area occupied by the netlist or design.
   - It is calculated as the area occupied by the netlist divided by the total core area.
   - When the utilization factor reaches 1, it implies that the core is completely filled with logic, leaving no room for further optimization.

5. **Ideal Utilization Factor**:
   - To allow room for optimization and flexibility, it's common to target a utilization factor of around 50-60%.
   - This ensures that there is some unoccupied space within the core for potential design adjustments.

6. **Aspect Ratio**:
   - The aspect ratio is a measure of the chip's shape, determined by the ratio of its height to width.
   - A square chip has an aspect ratio of 1, while a rectangular chip has an aspect ratio different from 1.

7. **Example Scenario**:
   - Let's consider an example with a utilization factor of 0.5 and an aspect ratio of 0.5.
   - If the die's length is 2 units and the height is 4 units, the aspect ratio is calculated as 2/4, resulting in 0.5.
   - With a required logic area of 4 units, the utilization factor is computed as 4/(2 x 4), equating to 0.5.

   ![die_core](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/4e2c3d48-8c05-4b6e-adfb-6df890fd5187)

Let us consider another core with area of 4x4 sq.units with the same netlist. So, The utilization factor now would be (2x2)/(4x4)= 0.25. So, Only 25% of area is utilized, the reamining area can be used for optimization.The aspect ratio here is 1, so it is a square chip.

 t![272643562-1832eb88-5287-44ea-a55d-f47a64f223ea](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/fbd070ac-a4bf-457a-869a-70b4502c226b)
In summary, core and die dimensions in chip design are influenced by the area occupied by the logic components, the utilization factor reflects the core's usage, and the aspect ratio describes the chip's shape, with a typical utilization factor target of 50-60% to allow room for optimizations.

</details>

<details>
<summary> Preplaced cells and Decoupling </summary>

1. **Preplaced Cells in Chip Design**:
   - Preplaced cells are specialized sections of combinational logic, such as macros or IPs (Intellectual Properties), that are intended for reuse multiple times in a chip design.
   - These cells are strategically positioned within the chip, and their locations are carefully defined based on the design scenario.

![272645026-b873a560-8336-4b82-a3fe-76d7ce5e72ed](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/dbfbb575-6960-40b8-ab20-22c2db850c1a)


2. **Reusability and IP Modules**:
   - To illustrate the concept, consider a combinational logic circuit with 100k gates that can be divided into smaller, reusable blocks.
   - These blocks can have their input/output (IO) pins extended and can be separated into distinct IP modules.
   - The logic within these blocks remains a "black box," hidden from the main netlist, and can be used multiple times throughout the design.

3. **Functionality as IP**:
   - These reusable models encapsulate specific functionalities and are defined as IPs, allowing designers to define their functionality once and reuse them across the chip.
   - This IP-based approach is established before the actual placement and routing of the chip begins.

4. **Fixed Locations and Floorplanning**:
   - Pre-placed cells have user-defined, fixed locations within the chip layout.
   - The arrangement of these IPs, along with other components, is referred to as floorplanning, forming the foundational structure of the chip's layout.

5. **Preservation of Pre-placed Cells**:
   - During the automated placement and routing process, the tool does not alter the positions of these pre-placed cells.
   - This ensures that the strategically located IPs remain in their designated positions.

6. **Decoupling Capacitors for Pre-placed Cells**:
   - Pre-placed cells need to be surrounded by decoupling capacitors.
   - When a logic gate transitions from 0 to 1 or vice versa, it demands a current from the output capacitance.
   - The Vdd (supply voltage) is responsible for providing the necessary voltage for these logic transitions.

7. **Handling Currents and Signal Integrity**:
   - In chip design, Vss (ground) must effectively handle the currents discharged by logic when transitioning from logic 1 to 0.
   - Additionally, the physical wires connecting various components in the design experience voltage drops due to resistance, inductance, and capacitance, which need to be managed for signal integrity.

   

In summary, preplaced cells in chip design offer reusability and flexibility, and their precise arrangement, along with considerations like decoupling capacitors, plays a crucial role in ensuring efficient and reliable chip functionality.

</details>

<details>
<summary> Noise margin and its effects </summary>
	

**Managing Voltage Drop and Signal Integrity**:

During the dynamic switching operation of a circuit, there's a demand for switching current. As this current flows, it encounters resistance within the wires and other components, causing a voltage drop. The voltage available at the circuit's inputs becomes Vdd (supply voltage) minus the IR drop.

Now, when this voltage drops below a certain threshold, known as the noise margin, an issue arises. If the voltage falls within the range between Vol (Output Low Voltage) and Vil (Input Low Voltage), it's considered a logic '0.' Conversely, if it's within the range between Voh (Output High Voltage) and Vih (Input High Voltage), it's interpreted as logic '1.' The voltage between Vil and Vih is an undefined region, where signals can behave unpredictably.

**Decoupling Capacitors for Noise Mitigation**:

To counteract the noise caused by long distances from the supply voltage, decoupling capacitors are introduced. These capacitors are connected in parallel with the circuit.

Here's how they work: Every time the circuit switches, it demands a surge of current. Decoupling capacitors, denoted as Cd, act as a reservoir of electrical charge. When the circuit switches, it draws this current from the decoupling capacitor.

To maintain stable voltage levels, an RL network (Resistance and Inductance) is often employed. It helps replenish the charge into Cd, ensuring that the voltage remains within the acceptable range.

![272646834-ffb2006a-7b5d-4486-b26f-a30da19d379a](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/be98d2f2-3410-47e8-a4c5-8af8bf7ddf32)

![272647684-8bcfa01e-5d14-4227-b1d0-558d26f2b894](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/885196da-4010-4a31-b4a1-4e5aad25a1fb)

**Benefits of Decoupling Capacitors**:

The addition of decoupling capacitors serves several critical purposes:

1. **Noise Mitigation**: By providing a nearby source of electrical charge, decoupling capacitors reduce voltage fluctuations due to the switching of distant components.

2. **Crosstalk Prevention**: They help prevent crosstalk, which occurs when signals from one part of the circuit interfere with signals in another, by maintaining consistent voltage levels.

3. **Logic Integrity**: Decoupling capacitors contribute to maintaining the integrity of logic levels by preventing voltage drops that could lead to signal misinterpretation.

![272645751-07f30b08-f84d-48a4-ba93-41858a8522ce](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/34e936c4-3d66-4859-9284-ec30024f0b8b)

In summary, decoupling capacitors are like reservoirs of electrical charge that support the stability of voltage levels in a circuit during dynamic operations. They play a vital role in ensuring reliable signal processing and preventing issues like crosstalk and logic degradation.

</details>

<details>
<summary>Power planning and pin placements </summary>


**Power Planning: Managing Voltage Stability**

In chip design, macros (reusable blocks of logic) often demand specific current when reused. To illustrate, let's envision a design with various macros, each thoughtfully surrounded by decoupling capacitors to maintain voltage stability.

![272649623-2c0c62a7-aeda-4fea-886e-c00cf8a5caac](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/158bdcd2-743a-4e68-a819-02badfeaac94)

Now, consider two adjacent macros, one acting as the driver and the other as the load, with a signal transitioning from logic 0 to logic 1. Adding decoupling capacitors to every cell within the logic isn't always feasible. Instead, critical blocks receive these capacitors.

Imagine a 16-bit bus with logic that charges and discharges as needed. The logic output connects to an inverter. As the capacitors that were charged to 'V' volts need to discharge to '0' volts through a single ground tap point, this can lead to a bump in ground voltage. If this bump exceeds the noise margin, the output becomes unpredictable.

Conversely, when capacitors at 0 volts need to charge to 'V' volts through a single Vdd tap point, a voltage droop may occur. If it goes beyond the noise margin, predictability is again compromised. Multiple power supply points, as shown in Powermesh, allow capacitors to charge and discharge from their nearest points, mitigating these issues effectively.

**Pin Placement: Ensuring Efficient Connectivity**

In chip design, the connectivity between gates is specified in VHDL/Verilog as a netlist. Picture a scenario with different timing paths, driven by various clocks, interclocks (alternate flops), and preplaced cells interconnected.

The strategic placement of pins plays a crucial role. These pins are typically located in the region between the die and the core, specifically reserved for pin placement. Logical cell placement blockages are employed to prevent the tool from inserting cells in this reserved region.

Consider the input ports situated on the left-hand side and output ports on the right-hand side. The specific ordering of ports depends on the planned placement of cells. Notably, flipflops should not be positioned on preplaced cells due to their fixed location. The clock port's continuous driving necessitates the shortest path with the least resistance.

![272651070-831dfec7-b607-43b3-88a6-c866e6d3a2cf](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/bf0d879e-f05f-4156-836e-7aa6c7645214)


In summary, Power Planning ensures voltage stability through strategic capacitor placement, while Pin Placement optimizes connectivity by carefully positioning pins in designated regions, enhancing chip functionality and predictability.
</details>

<details> 
<summary> Cell design and characterisation </summary>


**Binding Netlist with Physical Cells**:

1. **Library of Cells**:
   - Each cell, representing specific functionality in the synthesis phase, has defined width and height.
   - This information is organized in a library file, which includes timing data, cell size and shape details, and conditional information.
   - The library offers various flavors of cells that can be selected based on timing and available area on the floorplan.

2. **Placement on Floorplan**:
   - The floorplan provides a physical layout with well-defined ports and pins.
   - The netlist contains the physical view of logic gates.
   - During placement, the objective is to avoid affecting pre-placed cells and to position cells in proximity to the connected ports.
   - Signal integrity, ensuring faithful signal transmission, is maintained through repeaters (buffers) that recondition and replicate signals for the next stage.

3. **Placement Optimization**:
   - In this stage, wire length and capacitance are estimated to keep signal transitions within permissible limits.
   - The transition time (slew) depends on capacitance; higher capacitance requires more time to charge and results in slower slew rates.
   - Buffers are inserted to mitigate signal deterioration, especially when cells are placed farther apart, reducing the overall length of the signal path.

4. **Buffer Insertion for High-Frequency Signals**:
   - For high-frequency signals, minimizing delay becomes crucial.
   - Cells are placed closely to reduce significant delay.
   - Buffers are inserted into the design, assuming an ideal clock, to maintain signal integrity.
   - Data paths are evaluated, and buffers are inserted if signal length exceeds permissible values based on transition and slew rates.

5. **Timing Considerations**:
   - Meeting timing constraints is essential during placement, as timing tends to worsen in subsequent stages, especially routing.
   - Placement optimizations must ensure that signals transition within acceptable time limits.

**Importance of Characterization in IC Flow**:

1. **Logic Synthesis**:
   - Logic synthesis involves converting behavioral code into a hardware description using gate arrangements that replicate the desired functionality.

2. **Floorplanning and Placement**:
   - In the IC flow, netlists from logic synthesis are imported, and core and die dimensions are defined in floorplanning.
   - Placement ensures that cells are positioned to meet timing constraints, critical for overall performance.

3. **Clock Tree Synthesis (CTS)**:
   - CTS generates clocks with minimal skew, ensuring synchronous operation of all design elements.
   - Clock buffers help maintain uniform signal rise and fall times.

4. **Routing and Static Timing Analysis (STA)**:
   - Routing connects cells based on constraints.
   - STA verifies timing integrity, ensuring that design specifications are met.

5. **Cell Models and Tool Understanding**:
   - Cell models are crucial at each stage, allowing the tool to select the appropriate cells for optimization.
   - These models guide the tool in making informed choices during the design process.

In summary, the IC flow involves a series of stages where cell information, floorplanning, and placement optimizations are vital for achieving desired performance and signal integrity in the final integrated circuit. Characterization of cells plays a pivotal role in facilitating these stages.
</details>

<details>
<summary> Placement Optimization </summary>

**Optimizing Placement in VLSI Chip Design**

*Wire Length Optimization:*

**Definition:** Wire length optimization is the process of minimizing the total length of interconnect wires used to link standard cells in the chip layout. This optimization strategy prioritizes shorter wire lengths to reduce signal propagation delays, lower power consumption, and enhance signal integrity.

**Importance:**
- Shorter interconnects lead to lower resistance, diminishing RC (Resistance-Capacitance) delays, which is vital for high-speed designs.
- Reduced wire lengths result in less power dissipation, as less energy is converted into heat in the wires.
- Minimizing wire lengths optimizes chip area usage, potentially resulting in more compact and cost-effective designs.

**Techniques for Wire Length Optimization:**
- **Clustering:** Grouping related cells together minimizes wire lengths by reducing the distance signals need to traverse.
- **Global Routing Algorithms:** These algorithms plan high-level signal routing and aim to minimize overall wire lengths.
- **Timing-Driven Placement:** Placement tools can be guided by timing constraints to minimize wire lengths, especially for critical paths.

*Capacitance Optimization:*

**Definition:** Capacitance optimization focuses on reducing parasitic capacitance associated with interconnect wires and cell-to-cell connections. High parasitic capacitance can slow down signal transitions and increase power consumption.

**Importance:**
- Elevated parasitic capacitance can result in longer signal delays, particularly when combined with wire resistance (RC delay).
- Lowering capacitance enhances the power efficiency of the chip.

**Techniques for Capacitance Optimization:**
- **Wire Sizing:** Increasing the width of interconnect wires reduces parasitic capacitance but may increase wire resistance.
- **Spacing and Layer Assignment:** Optimization of wire spacing and assignment of signal lines to different metal layers decreases capacitance.
- **Shielding:** The addition of metal or shield layers mitigates capacitive coupling between adjacent wires.

*Integrated Optimization:*

**Trade-offs:** Wire length and capacitance optimization may involve trade-offs. For example, reducing wire length might necessitate using wider wires, which can elevate capacitance.

**Tools and Algorithms:** Electronic Design Automation (EDA) tools employ diverse algorithms and optimization techniques to simultaneously consider wire length and capacitance when performing placement.

*Timing-Driven Placement:*

**Timing Constraints:** Often, placement is guided by timing constraints. This entails positioning cells to meet required setup and hold times while also minimizing wire lengths and capacitance.

*Iterative Process:*

Optimization using wire length and capacitance typically involves an iterative approach. Placement tools may execute several iterations to enhance placement quality based on feedback from routing and other phases of the design flow.

In essence, optimizing placement in VLSI chip design is a multifaceted process that harmonizes wire length and capacitance considerations to attain high-performance, energy-efficient, and cost-effective integrated circuits.
</details>
<details>
<summary>Final placement </summary>
Absolutely, let's explore the significance of final placement optimization and abutment in the realm of VLSI chip design:

**Final Placement Optimization:**

*Definition:*
Final placement optimization, often referred to simply as "placement," is the meticulous process of precisely positioning standard cells within the chip layout. It follows the initial placement stage and plays a pivotal role in achieving design objectives.

*Objectives:*
1. **Minimize Wire Length:** A primary goal is to minimize the overall wire length of interconnections, as shorter wires translate to reduced signal delays and lower power consumption.
2. **Address Timing Constraints:** Final placement ensures that critical paths meet setup and hold time requirements.
3. **Optimize Area:** Efficient utilization of chip area is essential as it directly impacts chip size, cost, and manufacturability.
4. **Manage Power:** Proper placement can facilitate efficient power distribution and minimize voltage droop.
5. **Enhance Signal Integrity:** Careful placement helps mitigate crosstalk and other signal integrity concerns.

*Optimization Techniques:*
Placement algorithms are employed to iteratively adjust cell positions, enhancing overall placement quality while adhering to constraints.
Techniques include simulated annealing, genetic algorithms, and analytical placers.
EDA tools offer diverse placement optimization options, allowing designers to prioritize different objectives.

*Timing-Driven Placement:*
Timing constraints play a significant role in final placement optimization. Critical paths are identified, and cells are strategically placed to minimize delay.
Slack is often employed as a measure to ascertain if timing constraints are met.

*Tools:*
Commercial EDA tools offer advanced placement engines that employ various algorithms and techniques to optimize placement, considering multiple objectives.

**Abutment:**

*Definition:*
Abutment, within VLSI design, involves aligning the edges of adjacent standard cells to minimize the space between them. It proves particularly beneficial for cells with vertical or horizontal symmetry and contributes to reduced chip area usage.

*Importance:*
- Abutment optimizes chip area utilization by minimizing the gaps between cells.
- Simplifies interconnection routing by reducing the length of wires needed to connect adjacent cells.

*Types of Abutment:*
1. **Vertical Abutment:** Aligning the top and bottom edges of cells in adjacent rows.
2. **Horizontal Abutment:** Aligning the left and right edges of cells in adjacent columns.
3. **Corner Abutment:** Involves aligning the corners of adjacent cells in certain scenarios.

*Design Considerations:*
Abutment is most effective when cells have compatible heights or widths.
It may not always be feasible or desirable, especially for irregularly shaped cells or when it conflicts with other design objectives.

*Abutment Tools:*
EDA tools often provide automated abutment options during the placement phase.

In summary, final placement optimization and abutment are indispensable stages in the physical design flow of VLSI chip design. These stages refine the positions of standard cells, addressing wire length, timing, area, power, and signal integrity objectives. Abutment, in particular, streamlines chip area usage by aligning the edges of adjacent cells, reducing unused space, and simplifying interconnection routing. Together, these processes contribute to high-performance and efficient chip layouts.
</details>
<details>
<summary> Cell Design Flow </summary>


**Cell Design Flow: Inputs, Steps, and Outputs**

*Inputs:*

1. **Process Design Kits (PDKs)**:
   - PDKs provide essential information about the chip manufacturing process, including rules and specifications.

2. **LVS & DRC Rules**:
   - Layout vs. Schematic (LVS) and Design Rule Checking (DRC) rules ensure that the design adheres to specific layout and connectivity requirements.

3. **SPICE Models**:
   - SPICE models supply parameters defined by the foundry, facilitating accurate simulations of the circuit.

4. **Library and User-defined Specifications**:
   - These specifications encompass factors like cell height, cell width, power rail separation, ground rail separation, and more.
   - The library cell's design and noise margins are based on top-level supply voltage specifications.

5. **Metal Layers and Pin Locations**:
   - Some cells require specific metal layers and pin locations, which are typically defined by the top-level design.

*Design Steps:*

1. **Library Cell Selection**:
   - A library cell that meets all design specifications defined in the inputs is chosen.

2. **Circuit Design**:
   - Circuit design involves implementing the desired logic function and modeling NMOS and PMOS transistors to meet library requirements.
   - The output of this phase is a circuit description language (CDL) file.

3. **Layout Design**:
   - Layout design employs NMOS and PMOS transistors to create a network graph.
   - Euler's path and stick diagram techniques are used to generate an efficient layout that adheres to design rules.

4. **Characterization**:
   - Characterization gathers timing, noise, and power information.
   - In an extracted SPICE netlist, resistance and capacitance values for various cells are defined.
   - SPICE models for NMOS and PMOS are read, and the extracted SPICE netlist is processed.
   - Behavior of the cell (e.g., buffer) is recognized, and sub-circuits like inverters are read.
   - Characterization setups are applied, including stimuli, output capacitance, and simulation commands.
   - Simulations are executed using a tool like GUNA, generating output files that characterize timing, power, and noise.

*Outputs:*

1. **CDL File**:
   - This is the output of the circuit design step, containing the modeled circuit with NMOS and PMOS transistors.

2. **GDSII File**:
   - The output of the layout design step, which represents the layout using stick diagrams.

3. **LEF File**:
   - The Layout Exchange Format file defines the cell's height and width.

4. **CIR File**:
   - An extracted parasitic SPICE netlist that captures the behavior of each cell, used for characterization.


In conclusion, the cell design flow is a comprehensive process that involves a series of steps, starting with inputs, proceeding through design phases, and yielding essential outputs. Characterization parameters are essential for accurately characterizing cell behavior in terms of timing, power, and noise.
 
</details>

<details> 
<summary> General timing Characteristics </summary>
	
**General Timing Characterization Parameters:**

- **slew_low_rise_thr**: This threshold is determined by considering points near the lower side of the power supply (typically 0 volts) during a rising signal. The typical value is around 20%.

- **slew_high_rise_thr**: Conversely, this threshold is determined by examining points near the rising side of the power supply during a rising signal. It typically represents around 80% of the signal's rise.

- **slew_low_fall_thr**: For a falling signal, this threshold is calculated by analyzing points near the lower side of the power supply (0 volts). A common value is approximately 20%.

- **slew_high_fall_thr**: For falling signals, this threshold is determined based on points near the rising side of the power supply. Typically, it represents about 80% of the fall duration.

- **in_rise_thr**: This parameter represents the slew during the input transition of the applied stimulus for a rising input. It is typically set to 50%.

- **in_fall_thr**: Similarly, for a falling input, in_fall_thr signifies the slew during the input transition and is often set to 50%.

- **out_rise_thr**: Refers to the slew in the output waveform obtained when the cell's output rises. It's typically set to 50%.

- **out_fall_thr**: This parameter signifies the slew in the output waveform when the cell's output falls and is typically set to 50%.

**Significance and Use:**

- These threshold definitions are crucial for accurately characterizing the timing behavior of cells in the context of signal transitions.

- They are used to calculate various important parameters such as slew, propagation delay, and currents within a cell.

- Properly choosing these threshold points is vital, as incorrectly selected thresholds can lead to issues like negative cell delays, where the output becomes an input.

- Propagation delay, a fundamental timing characteristic, is calculated as the difference between output and input threshold points.

- Transition time, another critical aspect, is determined as the difference between high and low threshold points. It helps in understanding how a signal transitions between logic levels.

- When a circuit is not designed optimally, with an input having more transitions than the slew (50% point), the input's signal transition may occur much later than the output's signal transition. This discrepancy can lead to timing violations.

In summary, these timing threshold definitions play a vital role in characterizing the behavior of digital cells and ensuring that the timing specifications of integrated circuits are met accurately during the design process. Choosing appropriate thresholds is essential for reliable and predictable circuit operation.

</details>

<details>
<summary> Labs </summary>

The Images shown below give a clear understanding of how the different stages of design flow are done in Openlane and how the directories look before and after the run,

 README.md file which will say what all parameters need to be set for each stage,
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/READ_ME_1.png">

 For Synthesis stage:
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/README_synth_2.png">

 For floorplan stage :
 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/README_floorplan.png">

 For placement stage :
 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/README_placement.png">

 For CTS and routing stage :
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/README_cts_routing.png">

The values chosen are chosen based on set of priorities, the least priority is for floorplan.tcl then config.tcl in designs and the highest priority is for sky130A_sky130_fd_sc_hd.tcl
 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/config_tcl.png">
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/floorplan_tcl.png">

 run _floorplan command being executed:

 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/run_floorplan.png">


  def : design exchange formate file that is created after running the floorplan:
 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/floorplan_def.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/run_floorplan.png">

The floorplan in magic is as follows
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/ENTIRE_PLACEMENT.png">

We can select and check any components metal layer details , by typing 'what' on the command window of tkkon2.3
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/275bd0ef19c1b2fe9b785c82947c67216648a18d/Day16/tkcon_what_selection.png">

**Placement Labs**
 To run the placement we use the command run_placement:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/placement_1.png">

The placement of different cells cann be seen in the below snap:


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/placement_2.png">

The def file generated after placement is shown below, which also shows the total area.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/f2a3b326ef04d823cd97a68eebc5df05350a603a/Day16/placement_def.png">

 
</details>

# Day 17 Standard Cell Characterisation 

<details>
<summary> CMOS Inverter </summary>

**Viewing the Floorplan with Magic:**

- OpenLANE provides flexibility to adjust variable options on-the-fly.
- To change the congestion of IO pins alignment, you can use the "magic" command to view the floorplan DEF file.
- Here's how you can do it:
  ```
  magic -T /Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
  ```
- The floorplan shows the placement of pins, often arranged equidistantly.

**Adjusting IO Pin Congestion:**

- The IO placer tool is used to place IO pins based on specific requirements.
- To increase the congestion, you can change the variable to a higher value, for example, to 2.

**SPICE Simulations:**

- Before performing SPICE simulations, you need to create a SPICE deck.
- The SPICE deck contains connectivity information about the netlist, input configurations, and tap points for viewing outputs.
- It's essential to define the substrate, which influences the threshold of NMOS and PMOS transistors.
- Components' values, including W/L (width/length) ratios, need to be specified, for example, 0.375u/0.25u for both NMOS and PMOS (typically, PMOS is twice the size of NMOS).
- The output load capacitance, often denoted as Cload, is determined through complex computational analysis.
- Applied gate voltage is typically chosen as a multiple of the channel length, e.g., 2.5V.
- Node definitions are crucial to establishing connections between components.
- The netlist typically follows a format of drain, gate, source, and substrate.
- Here's how you can define  components in the SPICE deck:

~~~ruby
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u W=0.25u
cload out 0 10f
Vdd vdd 0 2.5
Vin in 0 2.5
~~~
  

  Where "M1" represents the transistor, "output_node" and "input_node" are the nodes, "substrate_node" is the substrate connection, and "W=0.375u L=0.25u" specifies the width and length of the transistor.

**Component Definition:**

In the SPICE deck, components are precisely defined with specific attributes:

- Component Name: Each component, such as a transistor, is given a unique name, like "M1."
- Component Type: Components are categorized by type, for instance, "PMOS."
- Width and Length (W/L): The width and length of the component, expressed as "W=0.375u L=0.25u" for PMOS, define its physical dimensions.

**Node Connections:**

Components are interconnected through nodes, indicating how signals flow:

- Drain and Gate Connections: For example, "out" is connected to the drain, and "in" is connected to the gate.
- Substrate and Source: In PMOS, the substrate and source connect to the supply voltage. In NMOS, these connections link to the ground.

**Load Capacitance:**

- The load capacitance, often denoted as "Cload," is an essential component in the SPICE deck.
- It's connected between the "out" port and the ground node.
- Its value is specified as 10fF, representing the capacitive load the circuit must drive.

**Supply Voltages:**

- Supply voltages are connected between ground and the respective nodes.
- In this case, a voltage of 2.5V is applied, ensuring proper operation of the components.

~~~ruby
.op
.dc Vin 0 2.5 0.05
~~~

In this command, a systematic variation of the gate voltage is executed, ranging from 0V to 2.5V. This voltage sweep is performed meticulously in 0.05V increments. The primary purpose is to capture a detailed snapshot of how the output behaves concerning different input voltages.


In summary, the SPICE deck defines components, their attributes, and interconnections through nodes. It ensures that signals propagate correctly through the circuit while taking into account load capacitance and the necessary supply voltages. This comprehensive approach to component and node definition is vital for accurate SPICE simulations in VLSI chip design.

</details>
<details>
<summary> Inverter Layout</summary>

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/INV_schematic_1.png">


**Poly Crosses N-Diffusion: NMOS**
- When a polysilicon (poly) layer crosses an N-diffusion region, it signifies the formation of an NMOS (N-type Metal-Oxide-Semiconductor) transistor.

**In Magic**:
- In Magic, if this specific configuration of poly crossing N-diffusion is selected, the corresponding command or action in the Tkcon window would typically be to highlight or select this region.

**Poly Crosses P-Diffusion: PMOS**
- Conversely, when the poly layer crosses a P-diffusion region, it indicates the creation of a PMOS (P-type Metal-Oxide-Semiconductor) transistor.

**In Magic**:
- In Magic, selecting the poly crossing P-diffusion would also involve a corresponding command or action in the Tkcon window to highlight or select this configuration.

**Connection of Y with Drain of PMOS and NMOS**:
- In the schematic or layout, there is a connection represented as "Y" that is shared between the drain terminals of both PMOS and NMOS transistors. This connection typically represents a common output node or signal line in the circuit.

**Other Connections**:
- The source terminals of the PMOS and NMOS transistors are connected as follows:
  - The source of the PMOS transistor is connected to one point in the circuit.
  - The source of the NMOS transistor is connected to a different point in the circuit.

These connections play a crucial role in determining how signals propagate through the transistors and the overall circuit.

In summary, when designing integrated circuits, the placement and connections of transistors play a vital role in defining the functionality and behavior of the circuit. Identifying whether a poly layer crosses N-diffusion or P-diffusion helps differentiate between NMOS and PMOS transistors, which are fundamental building blocks in VLSI design.
 
</details>

<details>
<summary> Fabrication </summary>

**CMOS Fabrication Process**

**1. Selecting a Substrate**
- The foundation of chip fabrication begins with selecting a substrate.
- The most common substrate is P-type silicon, known for its high resistivity, specific doping levels, and (100) orientation.
- Substrate doping is typically lower than well doping, as wells are used to separate NMOS and PMOS components.

**2. Creating an Active Region for Transistors**
- Active regions are pockets on the P-substrate where PMOS and NMOS cells will be placed.
- Isolation must be established between these active regions.
- This isolation process involves:
  - Growing a silicon dioxide layer as an insulator (approximately 40nm thick).
  - Depositing a layer of silicon nitride (approximately 80nm of Si3N4).
  - Applying a photoresist layer as a mask for creating wells.
  - Etching and stripping to expose silicon nitride.
  - Growing a second layer of oxide through a process known as LOCOS (Local Oxidation of Silicon).
  - Removing silicon nitride using hot phosphoric acid, ensuring electrical isolation.

**3. N-Well and P-Well Formation**
- N-wells are used for PMOS fabrication, while P-wells are for NMOS fabrication.
- Formation involves:
  - Deposition of a photoresist layer.
  - Creating masked areas exposed to UV light for implantation.
  - Diffusing boron for P-well and phosphorous for N-well using ion implantation.
  - Ensuring the wells occupy half of the substrate area.
  - Using a high-temperature furnace to finalize well formation (twin-tub process).

**4. Formation of Gate Terminal**
- The gate is crucial for controlling the threshold voltage, which determines when the transistor turns on.
- To achieve the desired threshold voltage, the gate formation process involves:
  - Depositing a polysilicon layer (approximately 0.4μm) and doping it with impurities like phosphorous or arsenic.
  - Applying a photoresist and gate mask, followed by etching and removal to form the gate terminal.
  - Precise control of dimensions and impurity concentration ensures the required threshold voltage is attained.

**5. Lightly Doped Drain (LDD) Formation**
- LDD structures are essential to mitigate issues like hot electron effect and short-channel effects.
- Formation process includes:
  - Using masks and photoresist layers to selectively expose regions.
  - Implanting phosphorous and boron with specific energies to create N+ and P+ regions while preserving lightly doped areas.
  - Utilizing side-wall spacers to protect the lightly doped regions.

**6. Source and Drain Formation**
- Creating the source and drain regions involves:
  - Adding a thin screen oxide layer to randomize ion directions.
  - Masking and exposing specific regions.
  - Implanting boron and arsenic to form P+ and N+ areas beneath the P-well and N-well regions, respectively.

**7. Contacts and Local Interconnects**
- Preparing for interconnects:
  - Removing the thin screen oxide.
  - Depositing titanium via sputtering and heating to form TiSi2 for local interconnects.
  - Applying masks to define interconnect gaps.
  - Etching away excess TiN using an RCA cleaning solution.
  
**8. Higher-Level Metal Formation**
- Achieving a planar surface:
  - Depositing a thick SiO2 layer doped with phosphorous or boron.
  - Utilizing chemical-mechanical polishing (CMP) for planarization.
- Creating contact holes, depositing TiN, tungsten, and aluminum layers, and forming metal contacts using masks and photolithography.
- Deposition, masking, and layering processes are repeated to achieve multi-level metal interconnections.

This meticulously executed process results in the fabrication of CMOS devices with precise dimensions, controlled doping, and well-defined components, essential for modern VLSI chip design.
</details>

<details>
<summary> Labs </summary>

The drc error in metal is seen.
As the 3.4 rule is not visible, it is visualised by selecting the location and filling it with metal3 layer

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/Mask.png">
 
 
The spice file generated is shown below:
	
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/spice_file.png">
 
The snap of the schematic of the same  is shown below:
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/INV_schematic_1.png">

 Loading the met_3_mag into magic :
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/met_3_mag.png">

 Loading the sky130.tech file
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/load_tech_file.png">

 Snap depicting different types of DRC:
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/DRC_fast_full.png">

 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/DRC_fast_full.png">

 Loading another design, and snapping its n well:
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/nwell_mag.png">

 
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/nwell_6.png">

 
<img width="1085" alt="yosys" src=" https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/poly_create_1.png">


 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/poly_create_1.png">

 Fixing the Poly drc :
 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/21ad36dd631f6178c55c7fc3bac92c85da14da84/Day17/polyfix.png">


 

 
</details>

# Day 18 Pre Layout timing analysis and importance of good clock tree

<details>
<summary> Delay Tables and setup analysis </summary>
	
**Introduction to Delay Tables:**


**The Problem**:
Clock tree design in Very Large Scale Integration (VLSI) chips faces challenges due to variations in capacitance and load at output nodes. These variations result in changing input transitions and, consequently, clock skew issues.

**The Solution**:
To address these challenges, engineers employ 2D delay tables. These tables serve as a critical component of the design process, providing a way to characterize delays based on input transitions and output load variations. By doing so, these tables help mitigate clock skew problems effectively.

**Key Elements**:

1. **Characterizing Delays**: Delay tables are a vital part of the "liberty" file used in the VLSI design process. They provide a structured way to summarize timing models.

2. **Output Slew as a Factor**: Output slew, or the rate of change in the output signal, plays a significant role in these tables. It is a parameter that significantly influences the overall timing behavior of a circuit.

3. **Influence of Input Transition**: Input transitions, or how fast the input signal changes, directly impact the delays experienced in the circuit.

4. **Effect of Output Load**: The load placed at the output nodes of the circuit can significantly affect the output slew, which, in turn, influences overall timing.

5. **Input Slew Dependency**: It's important to note that input slew is influenced by the previous buffer's output load and input slew. This interplay adds complexity to the design process.

In summary, 2D delay tables are a powerful tool used to address clock skew problems in VLSI design. They provide a structured way to characterize delays, considering various factors like input transitions, output slew, and the impact of output loads. Understanding these tables is crucial for achieving precise and efficient clock tree design.

  


![delay table usage](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/810187dd-c2fa-464f-a1d5-42afa5f549d7)

</details>
<details>
<summary> Setup Time analysis</summary>

**Understanding Setup Time Analysis**:

**Handling Clock Edges**:
In digital circuits, we have flip-flops that rely on clock edges. The setup time analysis deals with the timing of these clock edges in the context of launching and capturing data.

**Combinational Delay Check**:
For proper functioning, the combinational logic in a circuit should operate within specific time constraints. This analysis ensures that the combinational delay, the time it takes for these logic gates to process data, is shorter than the clock period.

**Internal Delays Matter**:
The setup time isn't just about combinational logic; it also considers the internal delays within flip-flops. Elements like multiplexers and other internal components can influence the overall delay within a flip-flop.

**Defining Setup Time**:
Setup time is a fundamental concept in this analysis. It's the amount of time necessary for a capture flip-flop to stabilize and produce a reliable output signal. It's crucial to ensure that this settling period aligns with the requirements of the circuit.

In summary, setup time analysis is all about ensuring that the clock edges, combinational logic, and internal delays work harmoniously to meet the setup time requirements, allowing for correct and synchronized data processing in digital circuits.


  ![setup ](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/c2b1357f-3f8a-468b-aa24-bffca9e735d4)

</details>

<details>

 <summary> Click jitter and uncertainty </summary>
 
**Introduction to Clock Jitter and Uncertainty**:


**Understanding Clock Jitter in Timing Analysis**:

**Clock Jitter Unveiled**:
Clock signals, responsible for synchronizing actions in digital circuits, are ideally expected to arrive at consistent intervals. However, due to various factors such as signal delays and variations, they don't always maintain this perfect regularity. These temporary variations in clock signals are what we refer to as "clock jitter."

**Dealing with Jitter**:
In timing analysis, accounting for clock jitter is essential to ensure the reliable operation of digital circuits. To accommodate clock jitter, we must ensure that the time period provided for each clock cycle is not just greater than the setup time of the flip-flops but also takes into account a certain "uncertainty time."

**Uncertainty Time and Jitter**:
Uncertainty time refers to the potential variations and irregularities in clock signals due to jitter. By allowing for this uncertainty time, we create a buffer period that can absorb the temporary fluctuations in clock intervals, ultimately ensuring that the circuit's operations remain synchronized and free from timing errors.

In summary, understanding and accommodating clock jitter in timing analysis is critical for maintaining the stability and accuracy of digital circuits, ensuring that they function reliably even in the presence of temporary variations in clock signals.

![setup with jitter](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/e294dd94-5026-4a49-ab0e-0c937fa91e4b)

</details>

<details>
<summary>Clock Tree Synthesis </summary>
**Clock Tree Synthesis**:

**Achieving Synchronization through Skew Minimization**:

**Skew Reduction**:
1. **Skew Minimization**: In the realm of clock tree design, a pivotal objective is to minimize skew. Skew represents the variation in arrival times of clock signals at different points in a circuit. By reducing skew, designers aim to achieve synchronous operation.

**The Role of H Trees**:
2. **H Tree Calculation**: To tackle skew head-on, a significant tool in the designer's arsenal is the H tree. This geometric structure calculates distances to various flip-flops within the circuit. These distance calculations are crucial in reducing the time differences between different parts of the circuit, contributing to enhanced synchronization.

**Addressing Wire Resistance**: 
3. **Repeater Deployment**: As signals traverse lengthy wires within a chip, they can face resistance that degrades signal integrity. To counter this, repeaters are judiciously added to the design. These repeaters act as signal boosters, ensuring that the clock signals maintain their quality and integrity over long distances.

In summary, the quest for synchronization in clock tree design involves minimizing skew, utilizing geometric structures like H trees, and deploying repeaters to address signal degradation. These strategies collectively contribute to reliable and coordinated circuit operation.



![cts with buffer](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/a58e02f2-62de-4bb9-9f9f-3947323af3e4)

</details>

<details>
<summary> Cross Talk and its mitigation </summary>
	
**Preserving Clock Net Integrity Through Crosstalk Mitigation**:

1. **Crosstalk Challenges**: Clock nets are vulnerable to external interference, leading to challenges like glitches and delta delays in signal transmission.

2. **Shielding Strategies**: To counter these challenges, shielding techniques come into play. These methods effectively safeguard clock nets from external interference, creating a protective barrier.

3. **Glitch and Delta Delay Reduction**: By creating this protective barrier, shielding minimizes the impact of crosstalk and other external disturbances. This reduction leads to fewer glitches and delta delays in signal transmission.

In summary, shielding techniques serve as a robust defense mechanism for clock nets, ensuring their integrity and contributing to the reliable operation of the circuit.

  ![cross talk](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/a1481a35-2d05-4844-b61f-f4bf91629dd8)
</details>

<details>
<summary> Timing analysis with real clocks</summary>
**Real Clock Timing Analysis**:

1. **Buffer and Wire Delays**: Accounting for buffer delays and wire effects within the clock tree design extends the overall clock period. These delays influence the time constraints for circuit operation.

2. **Data Timing**: To maintain proper circuit operation, the time required for data to propagate must be less than the time it takes for data to arrive at its destination.

3. **Slack as Synchronization Parameter**: Slack, which represents the time difference between data arrival and data required time, plays a pivotal role in ensuring synchronization within the circuit. Proper slack management is essential for reliable performance.

In summary, real clock timing analysis considers buffer delays, wire effects, and data timing to optimize synchronization, with slack acting as a key parameter in this process.
  

![cts with buffer](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/4582c359-701a-4498-97ec-db18d21e956b)
 </details>

 <details>
 <summary> Hold time analysis </summary>

**Hold Time Analysis**:

1. **Hold Time Necessity**: Hold time is a critical aspect of maintaining the reliability of data sampling following the clock edge. It ensures that data is correctly and consistently captured.

2. **Mux2 Delay**: The Mux2 delay represents the time required for Mux2 to generate its output based on the input received from the previous MUX. This delay is crucial for achieving stable and accurate data capture.

Understanding hold time is essential for guaranteeing data integrity and accurate sampling in digital circuits. It involves evaluating the timing requirements for Mux2 and ensuring that data remains stable during the capture process.

  ![hold](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/b0f2eacb-2f2c-4abb-97e9-72a37bea2947)

</details>

<details >
<summary> Labs </summary>

 To convert grid information to track information for VLSI design and integrate it into a project flow, follow these steps:

1. **Exclude Power and Ground Information**: Start by excluding power and ground grid information in your placement and routing process. These are not needed for track planning and standard cell placement.

2. **Focus on Inner Library and I/O Ports**: Concentrate on the inner library components, standard cells, and input/output (I/O) ports for your design. These elements are crucial for the functionality of your chip.

3. **Utilize .lef Files**: .lef files (Library Exchange Format) contain essential information about your library components and I/O ports. They serve as a protection mechanism for your intellectual property and microarchitecture.

4. **Extract .lef Files from .mag Files**: To obtain .lef files, extract them from .mag (Magic layout) files. .mag files often contain both the layout and library components. Extracting .lef files helps segregate library information for easier integration into your design flow.

5. **Incorporate .lef Files into Your Project**: Once you have .lef files extracted, incorporate them into your project flow. These files hold vital information about the standard cells and I/O ports that your design relies on.

6. **Align Input and Output Ports with Tracks**: Ensure that input and output ports are positioned to intersect both vertical and horizontal tracks. This alignment is critical for signal routing and connectivity.

7. **Maintain Proper Cell Width**: The width of standard cells should align with the track pitch. Standard cell widths must be odd multiples of the track pitch to ensure proper placement and routing.

8. **Refer to the Tracks.info**: Navigate to the "tracks.info" file within your Process Design Kit (PDK) folder. This file provides detailed information about the available tracks and their properties, helping you align your design elements correctly.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/track_info.png">

Creation and assigning ports:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day18%26%26/ports_creation.png">

Inverter LEF file:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day18%26%26/inverter_LEF_file.png">

Snap showing Grid spacing :

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/Grid_spaced_1.png">

Run synthesis:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day18%26%26/Run_syntyhesis.png">

Fixed Worst negative slack(wns) :

Some parameters to be considered:

    SYNTH_STRATEGY: control the area and timing
    SYNTH_BUFFERING: control if we want to buffer high fanout net
    SYNTH_SIZING: control in cell sizing instead of buffering
    SYNTH_DRIVING_CELL: ensure more drive strength cell to drive input


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day18%26%26/fixed_wns_synthesis_2.png">

Merging our custom inverter into the flow :

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day18%26%26/merging_new_inv_w_synthesis.png">

sky_invsakshith incorporated into the design:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/placement_sky_invsakshith.png">

Running floorplan:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/run_floorplan.png">

Running placement:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/run_placement.png">

Snap showing the our custom cell after placement:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/entire_placement.png">

Checks through openroad:

~~~ ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
echo $::env(SYNTH_MAX_FANOUT)
set ::env(SYNTH_MAX_FANOUT) 4
~~~

And then optimize the design using the following commands

~~~ ruby

cd ~/Desktop/work/tools/openlane_working_dir/openlane
echo $::env(SYNTH_MAX_FANOUT)
set ::env(SYNTH_MAX_FANOUT) 4
~~~



 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/openroad_checks.png">

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/open_road_checks2.png">

Snap showing changed clock buffer and improved slack:

 <img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/changed_clock_bufferfrom1to2_improved_slack.png">

Snap showing final setup and hold skew:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/c74c87c897345f35f69f056a7cd98493d017861c/day18/day%2018%3E%3E/hold_setup_skew.png">

</details>

# Day 19 Final steps for RTL2GDS

<details>

 <summary> Maze Routing using Lee's algorithm </summary>
 **Routing Stage: Lee's Algorithm**

1. **Maze Routing - Lee's Algorithm (Lee, 1961)**: Lee's Algorithm is a routing algorithm designed to determine the shortest path between two nodes in a grid, a fundamental process in routing physical connections within a chip design.

2. **Routing Process**: Routing is the procedure that establishes the physical wire connections within the chip design, with the aim of finding the optimal path between a source and a target. This optimal path should have the shortest distance and involve the fewest zig-zag turns.

3. **Blockage Consideration**: During the routing process, the algorithm must account for any blockages that have been defined in the design. Blockages are areas where routing is restricted or prohibited.

**Lee's Algorithm Steps**:

1. **Creation of Routing Grid**: The algorithm starts by generating a routing grid that matches the floorplan of the design. This grid provides a framework for the routing process.

2. **Source and Target Nodes**: The two essential points to be connected are identified within the grid – the source and the target.

3. **Route Determination**: Lee's Algorithm then searches for the optimal route to connect the source and target points using the routing grid as a guide.

4. **Grid Labeling**: The algorithm labels the grid, marking it as "ground," particularly in areas adjacent to horizontal and vertical grids. This labeling aids in guiding the routing process.

5. **Obstacle Recognition**: It's important to note that the algorithm does not label the grid areas that are underneath blockages, as well as those located at the boundary of the design.
![215032150-34401e02-d2db-4d5c-a437-3ca369b4cdec](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/971f0eae-8e9e-43d1-8aa9-83eb893532e0)

Lee's Algorithm is a critical tool in the routing stage that enables designers to navigate the chip's layout, avoiding obstacles and seeking the shortest and most efficient path to connect source and target nodes.
![215030291-ceea2ccd-d922-4883-8370-97a39a423721](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/75f96403-b6e4-4386-8740-edd50998452a)


</details>

<details>

 <summary> Theory about Lee's algorithm </summary>

 **Optimal Routing Path Selection**:

- **Choosing the Optimal Path**: In the context of routing, it's often preferable to select the Left-Hand Side (LHS) option when presented with multiple routing choices as illustrated in the figure below.

- **Selection Rationale**: The decision to choose the LHS route is primarily based on its alignment with the "best" routing criteria. In this case, the LHS route offers advantages due to its reduced bending, forming an L-shaped path, as compared to the Right-Hand Side (RHS) alternative.

- **Benefit for Global Routing**: Consequently, the LHS figure is favored for further global routing processes due to its potential for forming efficient routes with fewer bends.

- **Challenges in Routing**: While routing a single path is a relatively straightforward task, the complexity increases significantly when dealing with numerous start and endpoint pairs. This extensive routing task demands substantial time and memory resources.

- **Resource Consumption in Maze Routing**: The method of maze routing, while effective in finding optimal paths, can be resource-intensive, particularly in large and complex designs.

- **Mitigating Resource Consumption**: To address the challenges posed by extensive routing requirements, alternative algorithms come into play. For example, line-search algorithms and stanner-tree algorithms are employed to reduce the time and memory resources consumed during routing.
  
![215033857-8446f957-7d5d-4378-accf-81f824cfbdd9](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/7d2caaa8-c8c8-42ec-b822-b7718a9fc5bf)

In summary, choosing the optimal routing path, reducing bends, and managing resource consumption are crucial considerations in the routing process, especially when dealing with complex and large-scale chip designs. Different routing algorithms, such as line-search and stanner-tree algorithms, are deployed to enhance efficiency and conserve resources.

</details>

<details>
<summary> DRC and Rule Sets </summary>

 **Design Rule Check (DRC) in Routing**:

- **Design Rule Enforcement**: DRC refers to the essential set of rules that must be adhered to during the routing phase to ensure that the design complies with manufacturing and performance standards.

- **Wire Width Rule**: One fundamental DRC rule pertains to wire width, specifying the minimum allowable width of wires based on the fabrication process's limitations.

- **Wire Pitch Rule**: Another rule tied to the lithographic process is wire pitch, dictating the minimum center-to-center distance between two wires on the same layer.

- **Wire Spacing Rule**: A third critical DRC rule involves wire spacing, establishing the minimum separation distance required between two wires.

- **Complex Rule Set**: The routing tool must consider and enforce a multitude of DRC rules, each addressing specific aspects of design quality, manufacturability, and functionality.

- **Signal Short DRC Violation**: One common DRC violation is a "signal short," where unintended wire contact occurs on the same layer, posing a risk of functional failure.


  
![215036320-f0517b39-378a-4a40-9f0f-eb735c2001b4-2](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/53551b15-b7af-46be-9b40-427f251d1a1c)



- **Mitigation Strategy**: To rectify a signal short, the solution is to relocate one of the wires onto a different metal layer, preventing unintended connections.

- ![215036993-58407624-384b-4965-a9b1-0519dc5a5670](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/57c49dcf-77ef-4ac1-9104-258be2c282b0)



- **Evolving DRC Rules**: It's important to note that DRC rules evolve over time to align with technological advancements and manufacturing capabilities.

- **New DRC Rules**: After addressing and resolving DRC violations, new rules emerge, including considerations for via width (minimum via size) and via spacing (minimum separation between vias).

- **Origin of DRC Rules**: Most DRC rules are rooted in the intricacies of the lithographic process and are designed to accommodate the constraints of the technology.

- **Parasitic Extraction**: In addition to DRC, the routing process often involves parasitic extraction, a critical step where the resistances and capacitances of the wires are quantified. These parameters are subsequently used in downstream design processes.
- 
![215037259-747e6a52-c7cd-4a01-ab20-209179aef4fe](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/34fd780a-d030-4564-b941-9a1b7b0ae11b)

In summary, DRC rules in routing encompass a wide range of regulations that ensure the design's manufacturability, quality, and performance. Adhering to DRC guidelines is essential to avoid violations like signal shorts, and it's important to adapt to evolving rules and consider parasitic extraction as part of the routing process.
</details>

<details>
<summary> Labs </summary>



With the .def file created after cts we run the pdn and then the routing through the 'run_routing' command.
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9ee5459af7d9394f58baa657034f8d1406f718eb/day19/after_run_routing.png">



The snap clicked after routing.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9ee5459af7d9394f58baa657034f8d1406f718eb/day19/routed_pic.png">




Spec file generated after Routing:

spec files in the design process are crucial for documenting, guiding, and ensuring the integrity and quality of integrated circuit designs, from initial concept to final manufacturing and beyond.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9ee5459af7d9394f58baa657034f8d1406f718eb/day19/spec_after_routing.png">




On doing run_magic openlane generates the GDSII file




<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9ee5459af7d9394f58baa657034f8d1406f718eb/day19/after_run_magic.png">



Snap showing the final GDS

GDS is the standard format for representing and exchanging layout and mask information in the VLSI industry. GDSII files contain detailed information about the physical layout of integrated circuits, including the positions and shapes of transistors, interconnects, and other components.

VLSI designers use GDSII files to describe the physical design of integrated circuits, which are then sent to semiconductor fabrication facilities for manufacturing. GDSII files are essential for ensuring that the design is accurately translated into the physical mask sets used to create the actual silicon wafers.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9ee5459af7d9394f58baa657034f8d1406f718eb/day19/gds_png.png">
 
</details>

# Day 20 Floorplan and Powerplanning of VSDBabySoC

<details>
<summary> Theory </summary>

**1. Create a gate-level netlist (after synthesis)**
   - Netlist is the foundation for physical design.
   - It results from synthesizing RTL designs in VHDL or Verilog HDL.
   - Contains cell information, interconnections, area usage, and other design parameters.

**2. Floorplanning**
   - Determine block dimensions and their placement on the chip.
   - Aim to position highly connected blocks in proximity for efficient routing.

**3. Partitioning**
   - Divide the chip into functional blocks or modules.
   - Eases placement and routing by separating distinct parts of the design.

**4. Placement**
   - Optimal placement of standard cells within the core boundary.
   - Minimize congestion and optimize timing.
   - May include physical-only cells and buffers/inverters to meet timing and foundry requirements.
   - User preferences and tool commands can enhance quality of results (QoR).

**5. Static Timing Analysis (STA)**
   - Validates design's timing performance.
   - Checks all possible paths for timing violations.
   - Calculates signal propagation delay and enforces timing constraints.
   - Faster than dynamic simulation, as it doesn't simulate the circuit's logical operation.
   - Thoroughly examines all timing paths.
   - Focuses on timing, not functional correctness.

**6. Clock Tree Synthesis (CTS)**
   - Critical for reducing clock skew and insertion delay.
   - Distributes the clock signal evenly across sequential elements.
   
**7. Routing**
   - Establishes connections between cells and blocks.
   - Involves global routing (allocating routing resources and tracking network assignments) and detailed routing (making actual connections).
   
**8. Physical Verification**
   - Ensures the layout design is valid.
   - Checks for correctness, technological prerequisites, density verification, and other requirements.

     ![215411723-547f98c2-d8ac-446c-92b2-19e020ed9f1c](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/38a952bd-2a1b-4322-8d6e-88d2dc09ca13)


The Physical Design Flow is a comprehensive process that transforms a synthesized netlist into a chip layout while optimizing for factors like wire length, area, and power. Each step plays a crucial role in achieving a functional and efficient integrated circuit design.

</details>

<details>
<summary> Labs </summary>

After sourcing vsdbabysoc.tcl in dc_shell, generating all the reports of area, power and constraints.


Report Area:


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/report_area.png">

Report Power:


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/report_power.png">


Report Constraints
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/report_constraints.png">

Opening icc2_shell by invoking the shell and sourcing top.tcl in icc2 shell.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/after_source_top.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/schematic.png">

The schematics observed are snapped as follows:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/rvmyth_schematic.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/rvmyth_schematic2.png">

Report timing after generating propagater clocks:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/report_timing_after_prop_clock.png">

Snap after estimate_timing:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/after_estimate_timing.png">

Starting Gui and observing the output layout :

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/after_start_gui.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/after_start_gui1.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/ac117f14b46b2cf26f6d9eef61301cc249f0ff48/day19/day20/after_start_gui2.png">

Changing Utilization factor and observing the layout:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9e4268eafaa247c2673ff47206a4e7b2f0c08542/day21/core_utilization_40.png">

The clear difference between the above two layouts can be obseved in terms of how the corrnarea is sorrad across in the design.
 
</details>

# Day 21 

<details>
	
<summary> Theory> </summary>

**Placement in Physical Design**

Placement is a pivotal phase in physical design, consisting of several key aspects and stages aimed at optimizing various objectives.

**1. Pre-placement Sanity Check:**
   - Identify issues like floating pins, unconstrained pins, timing discrepancies, and pin direction mismatches in the netlist.

**2. Standard Cell Placement:**
   Placement involves dividing the chip into regions and positioning standard cells and macros for optimal chip performance.

**Placement Stages:**

**a. Global Placement:**
   - Initial placement to roughly position cells.
   - Balancing objectives such as congestion, timing, and routability.
   
**b. Legalization:**
   - Ensure standard cells are legally placed.
   - Prevent overlaps and meet design rules.
   
**c. Detailed Placement:**
   - Fine-tune cell positions for optimal performance.
   - Focus on congestion, timing, and runtime.

**Placement Objectives:**

**a. Congestion:**
   - Minimize congestion to enhance routing feasibility.
   - Prevent congested areas where routing becomes challenging.

**b. Performance:**
   - Optimize the physical placement for chip performance.
   - Minimize signal propagation delays.

**c. Timing:**
   - Ensure that the placement meets critical timing requirements.
   - Align paths to achieve synchronous operation.

**d. Routability:**
   - Facilitate easy routing by organizing cells efficiently.
   - Avoid obstacles and congestion.

**e. Runtime:**
   - Consider the time it takes to complete placement.
   - Efficiency in placement impacts overall design time.

**3. Clock Tree Synthesis (CTS):**

CTS is the process of creating an efficient clock distribution network, ensuring synchronous operation of circuit elements.

**Inputs of CTS:**
   - Placement Database (Placement DB)
   - CTS Specification File (CTS Spec file)

**CTS Steps:**

**a. Clustering:**
   - Group clock sinks into clusters to simplify clock tree generation.

**b. DRV Fixing (Drive Strength Fixing):**
   - Adjust drive strengths to balance loads and meet timing.

**c. Insertion Delay Reduction:**
   - Optimize delay elements to ensure consistent clock arrival times.

**d. Power Reduction:**
   - Minimize power consumption by optimizing the clock tree.

**e. Balancing:**
   - Balance clock skew across the chip to maintain synchronization.

**f. Post-conditioning:**
   - Fine-tune the clock tree structure after initial synthesis.

**CTS Quality Checks:**

**a. Skew:**
   - Verify that clock skew meets design constraints.
   
**b. Pulse Width:**
   - Ensure clock pulse width adheres to requirements.
   
**c. Duty Cycle:**
   - Confirm that the duty cycle is within acceptable bounds.
   
**d. Latency:**
   - Check and control clock latency.
   
**e. Clock Tree Power:**
   - Examine and optimize power distribution in the clock tree.
   
**f. Signal Integrity and Crosstalk:**
   - Address issues related to signal integrity and crosstalk in the clock network.
   
**g. Timing Analysis and Fixing:**
   - Perform timing analysis to identify and rectify any violations in the clock tree.

These processes collectively contribute to a well-optimized physical design, ensuring that the chip meets performance, power, and timing requirements.

</details>

<details>
	
<summary> Labs </summary>

Core utilization was previously set to 0.07.


The snap below represents the run when core utilization was set to 0.4 or 40%.

The vsdbabysoc.tcl is rerun in dc shell aand then top.tcl is run on icc2_shell
The change in the design placements and route can be observed in the below snap:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9e4268eafaa247c2673ff47206a4e7b2f0c08542/day21/core_utilization_40.png">

In the below snap the Dac and pll can be clearly observed which are part of the VSDbabysoc.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9e4268eafaa247c2673ff47206a4e7b2f0c08542/day21/dac_pll_seen.png">

The below snap shows the violators report:

some commands to ve fed into icc2 shell:


~~~ruby
set_propagated_clock [all_clocks]             (Converting clock object from ideal clock to propagated clock)
report_constraints -all_violators
~~~

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/9e4268eafaa247c2673ff47206a4e7b2f0c08542/day21/violators_report.png">

</details>

# Day 22 CTS Analysis Labs

<details>
<summary> Theory </summary>


**1. Purpose of Clock Tree Synthesis (CTS):**
   - The primary objective of Clock Tree Synthesis is to efficiently distribute the clock signal throughout a VLSI chip.
   - This ensures uniform and minimal skew delivery to all sequential elements (e.g., flip-flops and registers) within the chip.
   - The goal is to maintain synchronous operation and precise timing in digital circuits.

     *Some algorithms used in CTS:*
![276619307-028ffc89-4f70-43a6-a1d4-5418c3e5cbb3](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/331d983d-7c96-4494-8231-16956dd84545)

     

**2. Algorithms for CTS - The H-tree Algorithm:**
   - Identify all the flip-flops present in the design.
   - Calculate the center point of these flip-flops.
   - Begin tracing the clock port to the central point.
   - Divide the chip's core into two parts and trace to each center.
   - Repeatedly divide the area into halves and trace until reaching the clock pin of the flip-flop.
   - This process creates an H-tree structure for efficient clock distribution.
   - 
![276620129-5a4081a0-e390-4e3e-a845-3b26477b9f90](https://github.com/SakshithVarambally/Samsung_PD_Training/assets/142480548/e5ae738e-1fdd-4337-b4dc-7785f1c51ffe)


**3. Key Steps in Clock Tree Synthesis:**
   - **Clock Tree Generation:** Create a hierarchical tree structure branching from the primary clock source to minimize skew and optimize signal distribution.
   - **Buffer Insertion:** Introduce buffers along the clock tree to maintain signal integrity and minimize skew, especially for long clock lines.
   - **Clock Skew Optimization:** Minimize clock skew to ensure synchronous operation across the chip and avoid setup and hold time violations.
   - **Clock Gating:** Insert clock gating elements to disable the clock signal in inactive areas, reducing dynamic power consumption.
   - **Verification:** Rigorously verify that the clock signal is correctly distributed and meets timing requirements.

**4. Significance of CTS in VLSI:**
   - **Timing Closure:** CTS is critical for achieving timing closure, ensuring the design operates within specified clock frequencies without timing violations.
   - **Reducing Clock Skew:** It minimizes clock skew, ensuring synchronous operation and preventing metastability issues.
   - **Power Optimization:** CTS employs clock gating techniques to reduce dynamic power consumption.
   - **Enhancing Chip Performance:** Properly synthesized clock trees reduce clock distribution delays, enhancing chip performance.

**5. Challenges in CTS:**
   - **Skew Minimization:** Minimizing clock skew is challenging in complex designs with numerous clock domains.
   - **Trade-offs:** Balancing power consumption and clock distribution delay requires careful consideration.
   - **Hierarchical Design:** CTS complexity increases in hierarchical VLSI designs as it involves synthesizing clock trees at various levels.

**6. Commands for CTS:**
   - **check_clock_tree:** Identifies and reports issues that could impact Quality of Results (QoR) in clock tree synthesis.
   - **Clock tree structure constraints:** Specifies constraints and exceptions for the clock tree.
   - **check_legality:** Checks if the design is legal, using default constraints such as transition time, maximum capacitance, and maximum fanout.
   - **compile_clock_tree:** Optimizes the clock tree, including power optimization, re-synthesis, and timing adjustments.
   - **optimize_clock_tree:** Further optimization of clock trees, RC extraction, placement, and timing enhancements.
   - **remove_clock_tree:** Used to handle unrouted clock trees.

In summary, Clock Tree Synthesis plays a vital role in ensuring the efficient and reliable distribution of clock signals in VLSI designs, contributing to timing closure, power efficiency, and overall chip performance. It is accompanied by a set of commands to evaluate, optimize, and maintain clock trees, addressing the challenges associated with clock skew and complex design structures.
</details>


<details>
<summary> Labs </summary>


Multi-voltage Violations: This section checks for any instances where different voltage levels might lead to issues. Fortunately, there are no such violations detected.

Skew Balancing: It examines the balance in signal arrival times, and in this case, the system seems to be well-balanced.

Capacitance & Transition in Clock Network: This part evaluates the behavior of the clock network concerning capacitance and signal transitions. The results indicate that these aspects are well within the acceptable range.

Reference Cells (Don't Use/Don't Touch Cells): It identifies cells designated as "don't use" or "don't touch." The command output indicates that none of these cells have been violated or tampered with.

*check_clock_tree*
===
 
 The "check_clock_tree" command is employed to inspect potential problems that may negatively affect the Quality of Results (QoR) in a design, focusing on issues related to the structure of the clock tree, constraints, and exceptions. Its purpose is to detect issues that could hinder the successful execution of Clock Tree Synthesis (CTS).
 
Snap after check_clock_tree:
	
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/check_clock_tree1.png">


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/check_clock_tree2.png">

Checking some clock tree related desinitions and issues by 'man <CTS no.>'

CTS : 002 
Ensures and checks if all active CTS have atleast 1 clock defined in the design. New clocks are created through SDC comstaraints and status of created clock is checked through set_scenario_status.

CTS - 013

Ensures that the CTS process does not resize, optimize or replace the cells which are set under dont touch condition.

CTS -907

A clock signal cannot propagate through disabled arcs. This message indicates that there are timing arcs in the clock network that have been disabled.

*check_legality*
===

This command conducts a comprehensive assessment of design rules, looking for potential problems like design overlaps and improper routing on metal layers. The outcome reveals that there are no instances of these issues; all counts are at zero, signifying a successful confirmation of design legality.

Snap after check_legality:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/check_legality1.png">


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/check_legality2.png">

Some important terms menthoned in the above check_legality snap are:

- Movable: These are cells or instances that can be freely moved by the placement and optimization algorithms during the physical design process. They are not constrained to specific positions and can be rearranged to achieve better overall design quality, such as improved performance or reduced area.

 - Appfixed: "Appfixed" cells, short for "application fixed," are those that are fixed in position based on application-specific constraints. These constraints might be set to meet specific requirements of the design, and the placement and optimization tools will not move these cells. The designer specifies these constraints to ensure that certain parts of the design remain in fixed positions.

- User Fixed: "User fixed" cells are similar to "appfixed" cells but are typically set by the user explicitly. Users can designate specific cells or instances that must remain fixed in position, regardless of the automated placement and optimization. This is often done to enforce critical design requirements or to maintain compatibility with other parts of the design.


*report_clock_timing -type summary*
===

The "report_clock_timing -type summary" command produces a concise report focusing on clock timing aspects. This summary report offers a high-level perspective on critical timing details and performance metrics pertaining to the clock network.



Snap after report_clock_timing -type summary :



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/report_clock_timing.png">


- "rp-+" signifies a specific timing analysis scenario in digital circuits. It stands for "rising transition (r)" of a signal, "propagated clock (p)" at the clock input pin, and it evaluates the time it takes for a signal to propagate from the launch to the capture point.

- Clock skew refers to the variation in arrival times of the same edge of a clock signal at the clock input pins of different flip-flops in a digital circuit. This variation occurs because signals take time to travel from one point to another. Clock skew is essentially the difference between the time it takes for the clock signal to reach the clock input of the capture flip-flop (capture flop latency) and the time it takes to reach the clock input of the launch flip-flop (launch flop latency). It's a measure of how synchronized or misaligned the clock edges are between different parts of the circuit. Reducing clock skew is crucial for maintaining proper synchronization in VLSI designs.

- func1 is the corner whole flow PD flow was ran on and it represent corner sky130_fd_sc_hd__tt_025C_1v80.

  

*report_clock_timing -type skew*
=====


The "report_clock_timing -type skew" command is designed to create a report that is specifically centered on clock skew. This report delivers in-depth information regarding timing related to skew, which is crucial for maintaining synchronized clock signals.


Snap after report_clock_timing -type skew :



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/repoert_clocjk_timing_skew.png">


Skew" represents the time difference between the arrival of the clock signal at these two pins

Here the skew value of 0.24 indicates that there is a timing delay between when the clock signal arrives at the two pins, with a4_reg pin lagging behind a3_reg pin by 0.24 units of time.

*report_clock_timing -type latency*
====

The "report_clock_timing -type latency" command generates a report with a specific emphasis on clock latency. This report offers insights into the elements of the clock network related to latency, which can have implications for the overall performance of the design.


Snap after report_clock_timing -type latency :


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/repoert_clocjk_timing_latency.png">

 This represents the delay introduced by the network logic between the source (where the clock signal originates) and the destination (where it's received): This is shown as 0.32 as mentioned under network column.

*report_clock_timing -type transition*
====

The "report_clock_timing -type transition" command produces a report that centers on the transitions of clock signals. It provides information about how clock signals shift between various components within the design, giving insights into these transition behaviors.


Snap clicked after report_clock_timing -type transition :


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/d3b5e3b7c5d9662f51348f8a8f340fbb880de6b8/day22/repoert_clocjk_timing_transition.png">


*CTS*
==

The entire Clock tree(excluding the design) can be seen in the below snap which is synthesised in the design now.
 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e236905c57de39539c5461bbf43c407a3c480304/Day%2023/cts.png">


Some default constraints used by CTS:
~~~ruby
max_trans  - 0.5ns
max_cap    - 0.6pF
max_fanout - 2000
~~~

Using ICC2 with Debug Mode:

To enable debug mode in ICC2, you can use the following command:
set cts_use_debug_mode true

Enabling debug mode allows for more detailed insights into the Clock Tree Synthesis (CTS) process, making it easier to analyze and troubleshoot any issues that may arise during CTS. This can be particularly useful when you need to fine-tune your clock tree and debug any clock-related problems in the design.

</details>


# Day 23 Clock Gating Techniques

<details> 
<summary> Theory </summary>
**Clock Tree Synthesis (Advanced H-Tree)**

**Clock Distribution Challenges in Digital Circuits**
In digital circuits with numerous clock domains, designing a single, large clock tree can be overwhelming. To address this, a chip can be divided into smaller sections, each of which has its own clock tree. Ultimately, these individual clock trees are interconnected to create a complete routed clock tree.

**Clock Gating for Power Efficiency**
Apart from area and timing considerations, power efficiency is a critical factor in chip design. Clock gating is a technique used to reduce the dynamic power consumption of clocked elements in a design. The principle behind clock gating is to halt the clock signal to sequential elements when their data isn't changing, effectively saving power. Clock gating can be implemented using AND, OR, or universal NAND gates and is inserted during synthesis and optimized during the physical design stage.

**Power Savings through Clock Gating**
Clock gating is essential to reduce dynamic power consumption because it has been observed that approximately 50% of dynamic power originates from clock-related circuits. This technique is particularly valuable in scenarios where a block requires a clock signal for only a brief period, preventing unnecessary power dissipation due to continuous clock operation.

**Routing in Physical Design Flow**

**The Final Stage of Physical Design**
Routing is the last step in the physical design flow of integrated circuits. It involves creating physical connections between signal pins using metal layers. There are three main types of routing:

1. **P/G Routing:** This involves connecting power and ground (P/G) signals to all the components in the design, ensuring a stable power supply and signal reference.

2. **Clock Routing:** Clock signals need to be distributed efficiently throughout the chip, so clock routing focuses on connecting clock domains to the respective components.

3. **Signal Routing:** Signal routing encompasses the interconnection of various functional blocks within the design to ensure that data can flow as intended.

**Global and Detailed Routing**
Routing can be further divided into global routing and detailed routing. Global routing establishes the initial connections on a high-level, defining the general path for signals and power. Detailed routing refines these connections at a more granular level, ensuring proper timing and signal integrity.

**The route_opt Command**
The routing process is typically executed using a command such as "route_opt" This command optimizes the placement of routing tracks and connections to achieve the best possible performance and signal integrity in the final physical layout of the chip.
</details>


<details> 
<summary> Labs </summary>
 Voltage is first changed from 1.1 V to 1.8 V.
	
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/06ad151ed528d61e8aaa3854267c5af424160795/Day%2023/changed_voltage.png">

In order to add clock buffers in the design, the following lines are added in between place.opt and clock.opt in the script top.tcl as highlighted below in the snap.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/06ad151ed528d61e8aaa3854267c5af424160795/Day%2023/add_line_top_tcl.png">

The below snap shows the report_timing after adding the clock buffers  into the design.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/06ad151ed528d61e8aaa3854267c5af424160795/Day%2023/report_timing.png">

The layout obtained after adding clock buffers is shown below:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/06ad151ed528d61e8aaa3854267c5af424160795/Day%2023/schematic_w_gcg.png">



**CLOCK GATING**


1. **Stage**: Synthesis
   - **Command Used**: `compile_ultra -incremental -gate_clock`
   - **Purpose**: This command is used during the synthesis stage.
   - **Function**: It initiates the synthesis process, which converts a high-level RTL (Register-Transfer Level) description of the design into a gate-level representation. The `-incremental` option indicates that it is an incremental synthesis, which means that it only updates the parts of the design that have changed since the last synthesis run. The `-gate_clock` option suggests that it is related to optimizing clock gating.

2. **Input Data**:
   - **Input Files**: The DEF (Design Exchange Format) and gate-level netlist generated after synthesis are provided as input.
   - **Purpose**: These input files serve as the basis for the synthesis process.

3. **ICGs (Integrated Clock Gating) Insertion**:
   - **Action**: During the synthesis process, Integrated Clock Gating cells (ICGs) are inserted into the design.
   - **Purpose**: ICGs are added to optimize power consumption by gating the clock signals to specific parts of the design when they are not actively processing data. This helps reduce dynamic power consumption in the circuit.

In this manner, the `compile_ultra -incremental -gate_clock` command is used in the synthesis stage, with input from DEF and gate-level netlist files, to insert ICGs into the design and optimize power efficiency by controlling clock signals.

Inorder to see all the Clock gated cells added by the tool, we click on the logical hierarchy drop down box and the tool shows all the clock gated cells that are added.

With 544 gated registers, among 901 total registers: The percentage is observed to be 60.38%.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e236905c57de39539c5461bbf43c407a3c480304/Day%2023/clock_gating.png">

When we select a particular gated cell:

Inorder to obtain its reference name in the design

~~~ruby
get_attribute [get_selection] ref_name
~~~

In snapshot here is the ICG cell, whose ref_name is SNPS_CLOCK_GATE_HIGH_rvmyth_16, it contains latch from sky130 lib as shown below

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e236905c57de39539c5461bbf43c407a3c480304/Day%2023/gated_cell.png">

Observing the schematic of this cell, which shows the Enable signal controlling the clk signal passing to to the output signal:


<img width="1085" alt="yosys" src="https://githhttps://github.com/SakshithVarambally/Samsung_PD_Training/blob/e236905c57de39539c5461bbf43c407a3c480304/Day%2023/gated_cell2.png">

In order to show the worst slack in the design gui, we redirect the report_timing file to a txt file and then load that into gui. The tool then shows this worst path in the design as shown below.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e236905c57de39539c5461bbf43c407a3c480304/Day%2023/worst_slack.png">

</details>

# Day 24 

<details>
<summary> Theory </summary>
An Engineering Change Order (ECO) is a process used to incorporate last-minute design changes into a project. It typically involves modifying the gate-level netlist and ensuring these changes are also reflected in the RTL (Register-Transfer Level) representation of the design. The key steps in performing an ECO are as follows:

1. **Investigate the Problem**: Begin by analyzing the issue or changes required using the most recent database and design documentation.

2. **ECO Generation**: Create an ECO document that outlines the necessary changes, specifying which components need to be modified and how.

3. **ECO Implementation**: Carry out the actual changes in the design, both at the gate-level netlist and the RTL, ensuring consistency between them.

4. **Verification**: Rigorously verify the modified design to ensure that it passes both formal and functional verification. This step is crucial to guarantee the design's correctness and performance.

5. **Fix Violations**: Address any violations or issues that may arise during the verification process. Ensure that the design complies with all relevant specifications and constraints.

6. **Sign-off Checks**: Perform any sign-off checks that were not conducted during the previous stages of the design process. These checks are necessary to ensure that the design is ready for the layout phase.

7. **Database Update**: Save the modified design in the database for future reference. This helps maintain a clear record of all design changes and their implementations.

The ECO process is a critical aspect of the design and development of complex engineering projects, ensuring that last-minute changes are incorporated correctly and do not introduce errors or issues. It requires careful planning, verification, and documentation to maintain the integrity of the design.

</details>

<details> 
<summary> Labs </summary>

 The post_estimated_timing_report is shown below, and the highlighted part clearly shows the absense of any clock network delay, as the clock is ideal.

 The projected timeframe for the report's completion prior to entering the Clock Tree Synthesis (CTS) phase appears to be proceeding as planned. . This is indicative of a positive and healthy slack margin, emphasizing that the design or system is well within the desired timing constraints. These findings provide confidence in the current state of the project, suggesting that it is on course to meet its timing objectives without the need for significant adjustments or optimizations in the clock network. This information is reassuring as it indicates that the timing aspects of the design are currently robust and meeting the required specifications.

 
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/post_estimated_timing.png">



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/report_timing1.png">


The below snap shows the entire timing report on which we will start doing ECO in the next part.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/report_timing_mmm.png">

We can see many cells which have variable delays and are adding up to the final slack that is observed at the end that is observed to be -0.29ps, which clearly shows a violation. 

In order to correct this we begin ghe process of Sizing up the cell.
        

*Cell Sizing*




In order to enhance timing performance, it's advisable to consider upsizing the cell. This strategic adjustment involves boosting up the cell's drive strength, a pivotal factor in minimizing delay.

By elevating the drive strength of these cells, we can significantly contribute to the overall improvement of timing parameters, aligning our actions with the specific analysis detailed in the timing report. 

This approach focuses on the fundamental importance of drive strength as a key lever for optimizing timing within the design.

*Some examples of sizing shown below:*


Here we are sizing the cell U_347 as shown:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/sized_u347.png">


The next sizing is performed on the cell U343 :

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/sized_u343.png">

The next sizing is performed on the cell U86 from drive strength 1 to 2.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/sized_U86_1_2.png">

Now we begin to analize the qor reports.



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/before_timing.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/after_timing.png">

The critical path slack has improved from -0.13 to 0.12 which is a very good improvement observed. Along with this there is also a slight change observed in the length of the critical path.

The number of violating paths has reduced to 0, which were 12 initially.


Analyzing the Power report:

When upsizing is performed or when we increase the drive strength of cells in a digital design, various aspects of power consumption can be affected. Here's an explanation for each of the reported changes in power:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/report_power_before.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/report_power_after.png">

- Net Switching Power:
  Increased from 1.46e+06nW to 4.65e+06nW

   Increasing cell sizes or drive strengths allows cells to drive larger loads and switch more current during logic transitions. This results in an increased dynamic power component due to higher switching activity. As the cells become more capable of driving larger loads, the capacitance on the nets driven by these cells also increases. This, in turn, leads to higher net switching power due to increased switching activity, especially in the presence of larger capacitances.

- Total Dynamic Power:
  Increased from 4.26e+06 nW to 7.35e+06 nW

Total Dynamic Power is the sum of Cell Internal Power and Net Switching Power. When the cell internal power remains the same, but the Net Switching Power increases as explained above, it results in an overall increase in Total Dynamic Power due to the higher switching activity.


- Leakage Power:

Imcreaed from 1.25e+01 nW to 2.12e+02 nW

As mentioned earlier, increasing the cell sizes or drive strengths typically leads to an increase in leakage power. This is because larger transistors have a higher leakage current, which contributes to the total power consumed by the design. The increase in leakage power is generally more pronounced when cells are upsized because larger transistors inherently exhibit greater leakage.

In summary, when you upsize or increase the drive strength of cells in a design, you can expect an increase in both dynamic power components (Net Switching Power and Total Dynamic Power) due to increased switching activity and higher capacitance on the nets driven by these cells. At the same time, the leakage power increases because larger transistors exhibit higher leakage currents, contributing to the overall power consumption of the design. This explains the observed changes in the power report.


Analyzing Area Report:


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/before_area%26cellcount.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/after_cell_count%24area.png">

Total area has increased from 1735477 to 1735490.

Due to upsizing the cell, the Cell area has increased which is shown by increase in Combinational area, thereby affecting the total area.


Insertion of Decaps:

The below snap shows the insertion if decaps intk the design.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/29daf868e3186dd0894d8dce9273be2067b98674/Day%2024/after_inserting_decap_cells.png">


</details>

# Day 25 RISC V Core; RTL to GDS flow

<details>
<summary> RTL to GDS Flow </summary>

 **RTL to GDS Flow for IC Design**

*This comprehensive flow guides the transformation of a Register-Transfer Level (RTL) description into a physical layout ready for semiconductor fabrication.*

**1. RTL Design**
- **Description**: Create the logical design using hardware description languages (e.g., VHDL or Verilog).
- **Objective**: Define registers, combinational logic, and data paths.

**2. Functional Verification**
- **Description**: Validate the RTL design's functionality through simulations and testing.
- **Objective**: Identify and rectify logical errors or functional issues.

**3. Synthesis**
- **Description**: Convert RTL into a gate-level netlist using synthesis tools like Design Compiler or Genus.
- **Objective**: Optimize for area, power, and timing by mapping to standard cells.

**4. Design Constraints**
- **Description**: Set performance criteria, such as clock frequency, power consumption, and area.
- **Objective**: Guide subsequent steps in the flow.

**5. Technology Libraries**
- **Description**: Select the appropriate technology library with information on standard cells, flip-flops, etc.
- **Objective**: Choose components available in the manufacturing process.

**6. Placement**
- **Description**: Place synthesized gates on the chip using tools like Innovus or ICC.
- **Objective**: Minimize wirelength, optimize for constraints, and meet performance targets.

**7. Clock Tree Synthesis (CTS)**
- **Description**: Generate clock distribution network and optimize it for clocking requirements.
- **Objective**: Ensure minimal skew and jitter in clock signals.

**8. Routing**
- **Description**: Use routing tools to connect placed gates with wires, adhering to design constraints.
- **Objective**: Create physical interconnections and minimize signal delay.

**9. Design Rule Check (DRC)**
- **Description**: Perform checks to ensure the layout complies with fabrication rules.
- **Objective**: Verify minimum feature sizes, spacing, and other manufacturing constraints.

**10. Layout vs. Schematic (LVS) Check**
- **Description**: Compare physical layout with the schematic netlist to ensure consistency.
- **Objective**: Flag and resolve any discrepancies.

**11. Timing Analysis**
- **Description**: Analyze the design to confirm it meets performance goals, including clock frequency and setup/hold times.

**12. Sign-off**
- **Description**: After successful checks, declare the design ready for fabrication.

**13. GDSII Generation**
- **Description**: Generate the GDSII file containing geometric layout data for semiconductor foundry manufacturing.

This flow seamlessly transforms a high-level RTL description into a physical chip layout, ensuring the design meets stringent performance and fabrication requirements.

</details>

# Day 26 Introduction to Mixed Signal Flow

<details>
<summary> 
Mixed Signal Flow Integration:
</summary>

*Understanding the Fusion of Analog and Digital Signals*

**Analog Signals**:
- **Continuous Nature**: Analog signals represent information through a smooth, uninterrupted waveform, exemplified by characteristics like voltage, current, and temperature.
- **Infinite Values**: Analog signals can exhibit an infinite range of values within their specified range, making them suitable for capturing fine-grained variations.
- **Applications**: Analog signals find applications in various domains, especially where fine precision and real-world data representation are essential.

**Digital Signals**:
- **Discrete Representation**: Digital signals contrast with analog by representing data in a discrete, binary format typically as 0s and 1s, lending themselves to digital computing.
- **Distinct Levels**: Digital signals operate with well-defined levels, such as on/off or high/low, facilitating storage, processing, and transmission in digital systems.
- **Robust Handling**: Digital signals excel in robust handling of data, making them a cornerstone in modern information processing.
  
</details>

<details>
<summary> AMS Design Unveiled: Bridging Analog and Digital Realms </summary>

**Defining AMS**:
- **AMS**: "AMS" abbreviates "Analog and Mixed-Signal" design, the unification of analog and digital circuitry on a single chip. This amalgamation empowers systems to handle both continuous (analog) and discrete (digital) data, as vividly seen in the VSDBabySoC, harmoniously integrating analog modules like PLL and DAC with the digital entity RVMYTHCore.

**Circuit Categories**:
- **Analog Circuits**: These circuits are tailored for the manipulation of continuous voltage or current signals. They process real-world data such as audio, video, temperature, and sensor inputs. Common examples encompass amplifiers, filters, voltage regulators, and analog sensors.
- **Digital Circuits**: In stark contrast, digital circuits are designed to work with discrete binary data, deploying logic gates and memory elements. Their domain revolves around data processing, control, arithmetic operations, and the likes. Notable constituents include processors, memory components, and digital communication elements.
- **Mixed-Signal Circuits**: These circuits blend the analog and digital universes within a single chip. Their role often involves acting as intermediaries, translating analog signals into digital and vice versa. Prominent members include analog-to-digital converters (ADCs) and digital-to-analog converters (DACs).

**Applications**:
- **Versatile Applications**: AMS design holds a pivotal role wherever the amalgamation of analog and digital signals is essential. It finds applications in audio processing, data conversion, sensor interfaces, wireless communication, and power management, to name a few.
- **Data Conversion**: Integral to AMS design, Analog-to-Digital Converters (ADCs) facilitate the conversion of analog signals into a digital format for subsequent processing in digital circuits. Conversely, Digital-to-Analog Converters (DACs) transform digital data into analog signals for output.

**Signal Integrity and Co-Design**:
- **Signal Integrity Concerns**: In AMS design, safeguarding signal integrity is paramount. Factors like noise, jitter, crosstalk, and interference can impact both analog and digital circuits. Thus, meticulous measures are needed to mitigate these challenges.
- **Collaborative Design**: AMS design often necessitates close cooperation between analog and digital designers. A harmonious blend of both realms is required to ensure the seamless coexistence of analog and digital elements on the chip.
- **Testing and Verification**: Rigorous testing and verification procedures are indispensable in validating the performance of AMS designs. This ensures that they meet their specifications across various operational scenarios, guaranteeing reliability and functionality.

In summary, AMS design serves as the bridge between analog and digital domains, offering the ability to tackle real-world continuous signals and discrete data simultaneously, with broad applications and a need for meticulous design and verification.


**Analog-to-Digital and Digital-to-Analog Converters (ADCs/DACs)**:
- **Critical Bridge**: ADCs and DACs act as essential bridges between the analog and digital realms. ADCs transform analog signals into digital data, while DACs perform the reverse operation.
- **Communication Facilitators**: ADCs and DACs play a pivotal role in ensuring seamless communication between analog and digital components in a system.

**Mixed-Signal in Practice**:
- **Example: vsdbabysoc Design**: Real-world mixed-signal designs like "vsdbabysoc" combine analog blocks like PLL and DAC with digital components like the RVMYTH processor.
- **Interplay of Components**: These mixed-signal systems illustrate the interplay of analog and digital elements, harmonizing to deliver comprehensive functionalities.
</details>

<details>
<summary> Required Files in Mixed Signal Design**: </summary>

- **LEF (Library Exchange Format)**: LEF files carry essential physical information about standard cells, encompassing cell and technology-specific details, manufacturing grids, design rules, layer characteristics, and more.
- **LIB (Liberty File)**: LIB files present vital timing and power parameters associated with cells within the standard cell library, offering essential insights into cell performance.
- **GDSII File**: The GDSII format serves as a standard representation for integrated circuit layout data, encapsulating geometrical shapes, layered information, hierarchical data, text labels, and more.
- **OASIS File**: OASIS files have emerged as an efficient alternative to GDSII, addressing the limitations of complex modern designs, offering features like variable-sized elements and advanced serialization.
- **PnR Tools**: Physical design and implementation require Place-and-Route (PnR) tools, such as Innovus, IC Compiler II, and Olympus SOC, to generate the final layout (GDSII) from inputs like gate-level netlists, constraint files, libraries, and more.

**IP Cores: Building Blocks of Design**:
- **Definition**: IP cores are pre-designed blocks of logic or data that serve as essential components within semiconductor chips.
- **Ownership and Reuse**: IP cores are often intellectual property owned by specific entities and can be reused across various chip designs.
- **Categories**: IP cores come in two primary categories - "Hard IP Cores" with fixed physical implementations and "Soft IP Cores" that offer customization opportunities during physical design phases.
- **Applications**: IP cores are integral to creating field programmable gate arrays (FPGAs) and application-specific integrated circuits (ASICs), enhancing design efficiency and flexibility.

In summary, the integration of analog and digital signals in mixed-signal design leverages the strengths of both domains. It involves critical components like ADCs and DACs to bridge the gap between analog and digital systems, while the utilization of essential file formats and IP cores ensures efficient design processes and reuse opportunities.
</details>

# Day 27 Introduction to Signal integrity and cross talk

<details>
<summary> Understanding Signal Integrity and Crosstalk</summary>


**Signal Integrity and Crosstalk: Quality Checks for Clock Routes**


- **Signal Integrity (SI)** and **Crosstalk (XTK)** are crucial quality checks in clock route design. They play a pivotal role in ensuring the reliable operation of digital circuits.

**Signal Integrity (SI): Ensuring Reliable Data Transmission**
- **Signal Integrity Defined**: SI is the measure of an electrical signal's ability to transmit information consistently and withstand the disruptive effects of high-frequency electromagnetic interference originating from nearby signals.
- **Reliable Data Transfer**: SI is all about ensuring that electrical signals can carry data reliably without being adversely affected by external interference, noise, or degradation.

**Crosstalk (XTK): The Unwanted Electrical Interaction**


- **Crosstalk Explained**: Crosstalk is the undesirable electrical interaction that occurs between two or more physically adjacent signal traces or nets. This interaction results from capacitive cross-coupling and can corrupt the original signal during transmission.
- **Corrupting Noise**: Crosstalk manifests as a type of noise that intrudes upon the actual signal as it traverses the communication medium. This noise can disrupt the intended signal, potentially leading to erroneous data or logic states.

**The Influence of Design Geometry and Parasitic Capacitance**


- **Design Geometry Impact**: As semiconductor designs evolve and cell dimensions shrink, the physical distance between interconnects decreases. Consequently, cross-coupling capacitance between nets increases.
- **Effects of Narrower Interconnects**: Narrower interconnections result in reduced parasitic capacitance, but they also lead to faster cell delays due to the smaller transistor size.

**Factors Contributing to Crosstalk**


- **Multiple Metal Layers**: Increased usage of multiple metal layers in a design amplifies the potential for crosstalk.
- **Congestion and Routing Complexity**: Higher congestion levels, especially in terms of routing, exacerbate the risk of crosstalk.
- **Low Voltage Design**: Low-voltage design choices can elevate the susceptibility to crosstalk.
- **Thin and Long Metal Layers**: The routing of thin and lengthy metal layers can amplify crosstalk issues.

**Addressing Crosstalk Challenges**


- **Effective Strategies**: Several strategies can mitigate crosstalk problems. These include employing guard rings, down-sizing the aggressors or introducing shielding, layer promotion of nets, and segmenting lengthy nets into more manageable sections.
- **A Complex Web of Interactions**: In the realm of crosstalk, there are victim nets, which suffer undesired cross-coupling effects, and aggressor nets, which generate these disruptive effects. Aggressor nets can sometimes become victims, and vice versa.
- **Varied Timing Effects**: The timing effects of an aggressor net on a victim net are influenced by multiple factors. These include the switching direction (rise or fall), relative signal transition times, slew rates, cross-coupled capacitance, and the combinational impact of multiple aggressor nets on a single victim net.
</details>

<details>
<summary> Glitches: The Consequences of Crosstalk </summary>


- **Unwanted Spikes and Glitches**: Crosstalk leads to glitches, characterized by unexpected voltage spikes that can distort the signal. This occurs when one net is actively switching while another remains constant.
- **Types of Glitches**: Glitches come in different flavors, including rise glitches, fall glitches, overshoot glitches, and undershoot glitches. These glitches can have a substantial impact on the fan-out cells of the victim nets, potentially leading to misinterpretation of logic values.

**Exploring Glitches**:
- **Rise Glitch**: A rising aggressor net induces a rise glitch in a steady low signal.
- **Fall Glitch**: A falling aggressor net induces a fall glitch in a steady high signal.
- **Overshoot Glitch**: A rising aggressor net causes an overshoot glitch in a steady high signal, pushing the voltage above its normal high level.
- **Undershoot Glitch**: A falling aggressor net results in an undershoot glitch in a steady low signal, lowering the voltage below its usual low level.

In summary, Signal Integrity and Crosstalk evaluations in clock route design are essential for maintaining the robust and reliable performance of digital circuits. They help identify and mitigate unwanted interactions, safeguarding data transmission integrity and reducing the risk of glitches that could compromise circuit functionality.
</details>

<details>
<summary> Lab </summary>
After entering into pt_shell, the following commands are fed into the shell to set the library and load the design into the shell:
~~~ruby
 set target_library "<location of avsddac.db> <location of avsdpll.db> <location of sky130_fd_sc_hd__tt_025C_1v80.db>"
set link_library [list  <location of avsddac.db> <location of avsdpll.db> <location of sky130_fd_sc_hd__tt_025C_1v80.db>]
read_verilog <location of the synthesized netlist>
link_design
current_design
~~~

The below snap shows after the tool reads the sdc file:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/after_read_sdc.png">

The below snal shows after reading the spef file; Spef file is the parasitic extraction file and contians all the necessary details about it:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/after_spef_read.png">

The below snap is taken after reading the parasitics:


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/read_parasitics.png">

The bellw snap shows the check timing command being run:



<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/after_check_timing.png">

The below snap shows the report_timing command being run in the tool:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/report_timing.png">

Different checks are done on the design which are shown below:

~~~ruby
report_si_bottleneck              
~~~
This This command generates a report on setup and hold time bottlenecks in your design. Bottlenecks are points in the design where the setup or hold time requirements are most critical and might be violated.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/after_report_si_bottleneck.png">

~~~ruby
report_bottleneck                
~~~

This command is used to generate a comprehensive report on bottlenecks in the design, including information about setup, hold, and recovery time violations.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/report_bottleneck.png">


~~~ruby
report_si_delay_analysis
~~~


This command generates a report on setup and hold time analysis for your design. It includes detailed information about the timing paths, such as the worst-case paths and their corresponding delays.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/report_si_delay_analysis.png">

~~~ruby
report_si_aggressor_exclusion
~~~

This command generates a report that identifies aggressor nets, which are signal nets that might affect the timing of victim nets. The report includes information about aggressor exclusion rules to mitigate these effects.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/report_si_aggressor_exclusion.png">

~~~ruby
report_si_noise_analysis
~~~
This command generates a report on noise analysis in your design. It includes information about noise contributions from different sources, such as power grid and crosstalk.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e14ab7ada90aeb5a43aea74a0296de646015f83d/day_27/report_si_noise_analysis.png">

</details>

# Day 28 Introduction to DRC/LVS

<details>
<summary>Skywater 130nm Process Design Kit (PDK)
</summary>

 

Overview
===

The Skywater 130nm PDK is a robust open-source toolkit for chip designers, offering comprehensive design rules, layer definitions, device specs, and models. It empowers individuals to create circuits using open-source design tools, fostering innovation.

Caravel Chip
==

The Caravel chip, a prime example, integrates a RISC-V processor and allows users to define their design space. This chip showcases the versatility enabled by the Sky130 PDK.

Understanding the "130"
===

The "130" signifies the process's feature size, indicating the smallest transistors achievable—130nm. This measurement is crucial for chip designers working within this framework.

Components of Sky130 PDK
===

Documentation
===

Primarily sourced from the Skywater PDK, the documentation provides essential guidance for chip designers navigating the intricacies of the process foundry.

Library Files
===

Accessible on GitHub, the library files complement the PDK, offering a repository of resources for designers.

Community Engagement
===

The Slack group serves as a vibrant community hub, fostering collaboration and knowledge-sharing among designers using the Sky130 PDK.

Open Source EDA Tools
===

Introduction
===

Open_pdks, hosted on opencircuitdesign.com, functions as an installer based on makefiles. It streamlines the Skywater PDK files, ensuring compatibility with various open-source Electronic Design Automation (EDA) tools.

#### Installation Steps
1. **Clone Repository**
   ```
   git clone https://github.com/RTimothyEdwards/open_pdks
   ```

2. **Navigate to Directory**
   ```
   cd open_pdks
   ```

3. **Configure for Sky130 PDK**
   ```
   configure --enable-sky130-pdk
   ```

4. **Compile**
   ```
   make
   ```

5. **Install**
   ```
   sudo make install
   ```

 Compatibility Considerations
 ===
 

Open-source PDKs align seamlessly with open-source EDA tools, ensuring a harmonious design environment. However, caution is advised when integrating them with commercialized EDA tools due to potential file format disparities.
</details>

<details>
	
<summary> Tools </summary>

 ### Magic:

- **Overview**
  - Magic stands as a renowned Electronic Design Automation (EDA) tool pivotal in Very Large Scale Integration (VLSI) design.
  - Primarily caters to the layout and physical design aspects of integrated circuits.

- **Functionality**
  - Empowers designers in creating and refining the layout of integrated circuits.
  - Offers an array of tools for drawing, modifying, and visualizing physical components like transistors, wires, and interconnections.

### OpenLANE: 

- **Concept**
  - OpenLANE emerges as an open-source framework and toolchain, revolutionizing digital integrated circuit design.
  - Primarily tailored for ASIC (Application-Specific Integrated Circuit) design.

- **Key Features**
  - Provides a comprehensive and automated RTL-to-GDSII flow for chip design.
  - Leverages open-source EDA tools and methodologies.

### XSCHEM: 

- **Role in EDA**
  - XSCHEM, an open-source EDA tool, focuses on schematic capture and simulation.
  - Integral part of the XESS project, often synergizing with other EDA tools for seamless circuit design.

- **Interface Features**
  - Presents a graphical interface facilitating the capture of electronic circuit schematics.
  - Enables designers to draw and connect various electronic components like transistors, resistors, and capacitors.

### Netgen: 

- **Synthesis and Verification**
  - Netgen holds prominence in digital logic synthesis and formal verification for digital circuits.
  - Takes high-level hardware descriptions (VHDL or Verilog) to generate gate-level representations.

- **Context of Use**
  - Commonly employed in ASIC and FPGA design landscapes.

### NGSpice: Simulating Excellence in Mixed-Signal Analysis

- **Electronic Circuit Simulator**
  - NGSpice, an open-source simulator, plays a vital role in EDA for analog and mixed-signal circuit analysis.
  - Offers a platform to simulate a diverse range of electronic circuits.

- **Versatility**
  - Supports analog, digital, and mixed-signal circuit simulations, catering to a broad spectrum of engineering needs.

### Additional Tools in the EDA Toolbox

- **qflow, IRSIM, and xcircuit**
  - Diverse set of tools complementing the EDA landscape.
  - qflow facilitates a complete design flow, IRSIM serves as a switch-level simulator and power analyzer, while xcircuit adds versatility to the toolkit.

### Harmony Through Open_PDks

- **Common Ground for Libraries**
  - Open_PDks, in conjunction with open-source EDA tools, establishes a shared foundation.
  - Installation amalgamates foundry and third-party libraries, creating a unified directory across the source.

### Tailored Libraries for Optimal Performance

- **Digital Libraries**
  - Tailored to meet diverse requirements based on the speed and power of operation.
  - Each library serves a specific purpose, enhancing the efficiency of the design process.

### In Conclusion

In the symphony of Electronic Design Automation, each tool plays a unique melody, contributing to the harmonious creation of integrated circuits. From layout precision with Magic to the open horizons of OpenLANE, and the creative canvas provided by XSCHEM, the EDA realm is a rich tapestry of innovation and functionality. Together with NGSpice and additional tools, designers can orchestrate the perfect circuit, while Open_PDks ensures a unified foundation for their creative endeavors.
</details>

<details>
<summary> Skywater Libraries</summary>
	
- The sky130_fd_pr is the standard library for analog components.The most analog components such as transistors are handled by extraction, and do not need libraries. The components such as RF layouts, bipolar devices and parallel plate capacitors have an approved layout that can be used as an IP format in the library.

-   The devices operate from 1.8V to 20V, with common voltages being 1.8V and 3.3V. The sky130_fd_io is the library for IO pads and pad frame cells. It contains power, ground pads, general purpose IO pads. The sky130_ml_xx_hd is the third-party library contains alpha-numeric text layouts, for putting text in the layout.

- The sky130A contains libs.tech and libs.ref directories. The libs.tech contains all opensource EDA tools setup and libs.ref contains reference libraries. The sky130 process is described as a hybrid 130nm-180nm standard CMOS fabrication process. There are 5 layers of aluminium metal and titanium nitride (used for short routes due to high resisitivity), called local interconnect li.
  
-  The local interconnect is used for power and ground rails in skywater standard layouts. The poly contacts require a nitride polycut around the contacts. The metal layers are in progressive thickness. Usually higher order metal is used for routing purposes.

There are three types of libraries available in skwater pdks.

- Digital standard cells: These come with layout and GDS and formats used in synthesis flow. There are various flavours of cells covering high speed, high density, high voltage and low leakage. All the libraries follow a naming convention.

- I/O cells The I/O cell libraries contain entire power and ground pads which have entire disconnected blocks with them. The overlay connects the clamps/pads to power rails.

- Primitive devices and models The primitive designs include bipolar transistors, varactors, ESD devices
</details>

<details> 
<summary> DRC and LVS </summary>

 **DRC (Design Rule Checks)**

Design Rule Checks (DRC) play a vital role in VLSI design and manufacturing, ensuring the physical layout of an integrated circuit aligns with the design rules set by the semiconductor fabrication process. These automated checks are essential for preventing layout errors that might lead to manufacturing defects such as shorts, opens, or excessive metal density. By confirming design compliance with technology-specific rules, DRC contributes to the reliability and manufacturability of semiconductor devices.

DRC checks are executed using specialized software tools provided by semiconductor foundries or third-party Electronic Design Automation (EDA) tools. These tools utilize design layout data in formats like GDSII or OASIS, along with technology-specific rules, to perform automatic checks. Compatibility with the specific semiconductor manufacturing process, like 28nm or 14nm, is crucial. Designers iteratively run DRC checks, making adjustments until achieving a DRC-clean design.

Adhering to DRC rules is imperative for producing semiconductor devices that meet manufacturing requirements and ensuring their reliability in real-world applications.

---

**LVS (Layout Versus Schematic)**

Layout Versus Schematic (LVS) stands as a critical step in VLSI design, verifying that the geometric layout of a chip accurately corresponds to its intended electrical schematic. In simpler terms, LVS checks whether the physical representation (layout) aligns with the functional design specified in the schematic.

LVS tools compare layout data (typically in GDSII or OASIS format) with schematic data, analyzing geometric shapes, connectivity, and other properties against logical connectivity defined in the schematic. The software identifies issues like missing connections, shorts, and opens, ensuring consistency between the layout and functionality.

LVS is an iterative process where designers adjust the layout based on LVS results, running checks multiple times until achieving an LVS-clean design. Debugging and resolving LVS issues become integral parts of the IC design process.

Layout Versus Schematic is crucial for maintaining the functionality and performance of integrated circuits while minimizing errors during the manufacturing process.
</details>

<details>
<summary> Labs   </summary>

- To activate Xschem, enter "xschem" in the command prompt.

- Unlike applications with a separate console window, Xschem operates with the terminal serving as its console, lacking a quick command interface.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/xchem.png">

- Command magic in the command prompt to invoke magic interface.
- Magic opens two windows namely layout window and console window as shown below.

The below snap shows the window after placing a nmos from sky130A technology.

By selecting a part of the nmos and ttping 'what' , the selcted item can be viewed as shown below.

Here the mask layer was selected and correspondingly it is shown in the tkcon window.
  
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/what_selection_magic.png">

The below snap shows the process of editing the cell properties.

Here the length is changed to 0.5um, width to 2um and fingers is changed to 3 as shown adjacent to the layout.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/nmos_g5_magic.png">

 **Creating an Inverter Layout in Xschem:**

1. **Accessing "Choose Symbol" Window:**
   - Press the "Insert" key to bring up the menu.
   - Navigate to the SkyWater library by specifying the directory path.
   - Choose the "fd_pr" library.

2. **Selecting nfet and pfet Devices:**
   - Pick the fundamental nfet and pfet devices from the insertion menu.
   - Position them freely within the schematic.

3. **Symbol Selection:**
   - Specifically, choose "nfet_1v80.sym" and "pfet3_1v80" from the list of symbols.

4. **Adding Pins:**
   - Access the "xschem" library in the insert window to find non-PDK-specific pins.
   - Include "ipin.sym," "opin.sym," and "iopin.sym" as necessary.

5. **Arranging Components:**
   - Use the "M" key to move components to desired locations.
   - Utilize the "C" key to duplicate components.
   - Employ the "Del" key to remove unwanted components.

6. **Establishing Connections:**
   - Use the "W" key to insert wires between components, forming connections.

7. **Naming Pins:**
   - Give meaningful names to each pin:
     - Use the "Q" key to access the parameter window.
     - Modify labels as needed.

8. **Component Configuration:**
   - Select components by clicking on them.
   - Press the "Q" key to open the parameter window for configuration.

9. **nfet Configuration:**
   - Adjust the nfet component settings:
     - Set length to 0.18.
     - Specify 3 fingers with a width of 1.5 each.
     - Ensure total width in the parameter window is 4.5.

10. **pfet Configuration:**
    - Configure the pfet component:
      - Set 3 fingers with a width of 1 each.
      - Length is 0.18.
      - Connect the body to the Vdd pin (3-pin pfet).

11. **Final Adjustments:**
    - Refine the layout by making any additional adjustments.
    - Ensure all connections are accurately represented.

12. **Review and Save:**
    - Double-check the schematic for accuracy.
    - Save the work as inverter.sch

By following these steps, you can successfully create an inverter layout in Xschem with precision and clarity.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/inverter_schematic.png">

**Creating inverter Symbol**

1. **Symbol Creation:**
   - Navigate to the Symbol menu.
   - Choose "Make symbol from schematic" to generate a symbol for the schematic.
   - This symbol will represent the schematic in the testbench.

2. **Testbench Schematic Setup:**
   - Create a new testbench schematic using the "new schematic" option.
   - To integrate the schematic into the testbench, use the "Insert" key.

3. **Inserting Symbol:**
   - Locate the generated symbol in the local directory.
   - Insert the symbol into the testbench schematic using the "Insert" key.

4. **Functional Validation:**
   - Ensure that the schematic is accurately represented by the symbol.
   - Validate the functionality of the schematic within the testbench environment.

By following these steps, you establish a clear linkage between the schematic and the testbench, allowing for effective functional validation. The creation of a symbol serves as a representation of the schematic in the testbench, facilitating comprehensive testing and verification.

The below snap shows the command setting up the 1st voltage source.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/voltage-source.png">


### **Creating a Testbench in Xschem: Observation of Inverter Response**

1. **Open Schematic:**
   - Launch a new schematic from the "File" tab.
   - Import the "inverter.sch" file located in the home directory by pasting it onto the schematic window.

2. **Testbench Setup:**
   - Insert two voltage sources from the default "xschem" library—one for the input and one for the power supply.
   - Establish connections between these voltage sources and add a ground (GND) node to the supply connections.

3. **Signal Definition:**
   - Create "ipins" and "opins" to designate input and output signals for observation in Ngspice.
   - Set the supply voltage to 1.8 V.

4. **Input Voltage Specification:**
   - Define the input voltage using a piece-wise linear function (PWL) to generate a ramp.
   - Specify voltage and time values for the PWL function, such as:
     - Supply starting at 0 V.
     - Voltage ramping up from 20 ns to 1.8 V by 900 ns.

5. **Ngspice Integration:**
   - Integrate two additional statements for Ngspice using text boxes.
   - Use the "code_shown.sym" component from the "xschem" library to create text boxes.

6. **Text Box Content:**
   - In the first text box, specify the location of device models in the device schematic.
   - Include a ".lib" statement to select a top-level file, e.g., ".lib /usr/share/pdk/sky130A/libs.tech/ngspice/sky130.lib.spice tt" for the typical corner with value "tt."
   - In the second text box, include specific instructions or information, e.g.:
     ```plaintext
     .control
     tran 1n 1u
     plot V(in) V(out)
     .endc
     ```

By following these steps, we can establish a comprehensive testbench for the inverter, allowing the observation of its response to a ramp input in Ngspice.


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/blabla1.png">


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/blabla2_tran.png">

The final oitput is shown below:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/inverter_schematic.png">

The below waveforms show that the circuit behaves like an inverter.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/waveform.png">


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/symbol_transient_solution.png">

The extraction process for .ext file is shown below 

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/extraction_snaop.png">


### **Importing Schematic to Layout in Magic**

1. **Accessing Magic:**
   - Navigate to the "mag" directory and launch Magic.

2. **Import Schematic:**
   - In Magic, go to File -> Import SPICE.
   - Choose the "inverter.spice" file from the xschem directory.
   - Once executed correctly, the layout corresponding to the schematic opens in Magic.

3. **Manual Placement and Routing:**
   - Since schematic import lacks knowledge of analog placing and routing complexities, manual intervention is essential.
   - Place the pfet device above the nfet and adjust the positions of input, output, and supply pins as needed.

4. **Parameter Adjustment:**
   - To streamline the wiring process, open the parameter editing section using the 'S' key.
   - Select an object ('I' key) and use CTRL+P to access parameter options for the chosen device.
   - Set "Top guard ring via coverage" to 100 for both pfet and nfet.
   - Adjust "Source via coverage" and "Drain via coverage" to +40 and -40, respectively, for both pfet and nfet.

5. **Wiring the Layout:**
   - Utilize metal1 layers to paint wires.
   - Connect the source of the pfet to Vdd, source of the nfet to Vss.
   - Link drains of both mosfets to the output.
   - Connect the input to all poly contacts of the gate.

By following these steps, you effectively import the schematic into Magic, manually place and route the components, and optimize the layout for efficient wiring.

There were almost 18 DRC errors. By going to the DRC manager and solving them one by one the final DRC result was 0. At times solving 1 error fixed many DRC's all at once.

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/after_drc.png">


<img width="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/7d8dac594742ea94478bd32f2b81268a256e8fc9/day28/lvs_and_magic.png">

LVS matching is shown in the below snap:

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/LVS_match.png">

The testbench snap is shown below:
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/tb_new.png">


Now by running the modified testbench file, the obtained result is almost the same as previous simulation in xschem

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/e29c0bfeda84ddee0e9969a46acb63bfe9a8704f/day28/waveform.png">

</details>

# TCL Workshop

<details>
<summary> Day 1 </summary>

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/1_1.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/1_2.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/1_3.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/1_4.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/1_5.png">

<details>
<symmary> Day 2</symmary>
https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/2_1.png
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/2_4.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/2_6.png">
</details>

<details>
<summary> Day 3 </summary>


<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_1.png

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_2.png

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_4_sdc.png

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_6_after_hierarchy_check_pass.png

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_7_hier_outputs.png

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/3_8.png
</details>

<details> 
<summary> Day 5</summary>

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_1.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_2.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_4_after_synthesis.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_7_synthesis_log.png">
<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_8_after_procs.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_8_after_procs.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_9_after_procs.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/5_9_after_procs.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/6_1.png">

<img width="1085" alt="yosys" src="https://github.com/SakshithVarambally/Samsung_PD_Training/blob/dbe6775b2bd1fd716da9486bbf650a52cfe677b8/TCL_workshop/final_qor.png">


</details>


