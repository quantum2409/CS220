# CSE Bubble

## Overview

This assignment required us to build a single-cycle MIPS processor. The processor's word size is 32 bits.<br/>

We have followed the following diagram extensively to design the processor.

![processor](https://github.com/quantum2409/CS220/assets/98262532/d9ae0fb8-945f-4d5e-b95b-81fc0970a042)

## How to run the code

Use the following commands inside the project file location.

```bash
cd 'FOLDER_PATH'
iverilog -o out.vvp tb.v
gtkwave out.vcd
```

Note the iverilog and gtkwave need to be set-up as a pre-requisite.

## Goals

A single-cycle MIPS processor (CSE BUBBLE) with the following features:
<ol>
  <li>32 bits word size</li>
  <li>VEDA memory architecture for: <ul>
    <li>Instruction Memory</li>
    <li>Data Memory</li>
  </ul></li>
  <li>A register file (RISC_BUBBLE): with 32 registers, where certain registers have the same role as in MIPS-32-ISA</li>
  <li>Design op-code formats for the processor to decide data paths</li>
</ol>

## Guide through the code 
<ul><li>
  The machine code instructions are stored in the instrMemory, which are fetched at each clock
cycle and stored in the instr_data.
</li> <li>
  The main processor CSE_BUBBLE has 3 module instantiations: instrMemory, dataMemory and
manipulate.
</li><li>
  Manipulate takes the connections to instrMemory and datamemory and manipulates (decides) the
actions to be done.
</li><li>
  Inside the manipulate module the following modules are instantiated: Controller, Datapath.<ul>
    <li>Controller: takes the instruction >> decodes the command based on the opcode >> triggers on
specific control signals.</li>
    <li>Datapath: takes the control signals sent by the controller >> updates the program counter OR
decides destination register OR writes/loads from data memory, all based on the control signal.</li>
  </ul>
</li><li>
  The ALU module takes the control signal 'alucontrol' to decode what to do with the given inputs.
The ALU has multiple mux which decides the output coming from the alu. Alu output also has
branch condition that ANDs with the branch control signal to decide whether the program
counter actually branches or not.
</li><li>
  MIPS code for bubble sort is written and converted into machine code.
</li></ul>

## Proof of work

The data memory is first initiated with the input array for BUBBLE SORT in the following order:
size of array=9, size of array-1 = 8, 9 values stored in the array at zeroth index and first index of the data memory.<br/>
The data memory is filled with the following input array:<br/>
9, -56, -9, 17, 100, 2938, -1987, 2083, 1<br/><br/>
Instruction number 32 and onwards is used to load a register with the values in the data memory just to show that the data memory is now written with the sorted array.:

![gtkwave](https://github.com/quantum2409/CS220/assets/98262532/766f34d2-8121-4818-87ad-97d5bb7848c1)

