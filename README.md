
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

