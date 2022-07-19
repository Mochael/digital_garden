---
title: How does a CPU Work
tree_state: 🌱
---


![](../search_pics/Brief_Look_into_Measure_Theory/risc_processor)

Let's say we want to execute some machine code with our processor
1. We have a program counter (PC) to keep track of where we are in our program
2. We have a clock that oscillates voltages between 0 and 1 very quickly.
3. Instruction cache stores our set of instructions for our code.
4. Instruction register stores the current instruction that we want to execute by fetching what the program counter points to
5. The A and B registers store values (like function argument values) that we want to use for our operation in the instruction register
6. The Arithmatic Logic Unit (ALU) contains the logic gates that allow the CPU to perform logical operations.
7. The ALU accesses data from the cache to perform its instructed operations
	- If we want to access data that lives on the disk, it must be propogated up to the highest level of the cache before we can interact with it 
8. We then write back the result of the operations to the registers to use for subsequent instructions

### Clock Speed
The speed of a computer processor, or CPU, is determined by the **Clock Cycle**, which is the amount of time between two pulses of an oscillator. Generally speaking, the higher number of pulses per second, the faster the computer processor will be able to process information. The clock speed is measured in Hz, typically either megahertz (MHz) or gigahertz (GHz). For example, a 4GHz processor performs 4,000,000,000 clock cycles per second. Computer processors can execute one or more instructions per clock cycle, depending on the type of processor. Early computer processors and slower processors can only execute one instruction per clock cycle, but faster, more advanced processors can execute multiple instructions per clock cycle, processing data more efficiently.

Ideally we want the highest clock speed possible, but the faster the clock the more power it consumes and the more heat it will generate. If the clock is too fast we can't dissipate all the heat and we will melt the circuit.


## CPU vs GPU
![](/Users/michaelkronovet/Desktop/digital_garden/search_pics/cpu_vs_gpu.jpeg)

CPU is for running a machine so it needs more complex instruction sets in its ALU. A GPU is only really meant to process graphics, so can use a very simple ALU, but just replicate a shit ton of them for parallel processing.