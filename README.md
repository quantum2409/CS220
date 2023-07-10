# CSE Bubble

## Overview

This assignment required us to build a single-cycle MIPS processor. The processor's word size is 32 bits.<br/><br/>

We have followed the following diagram extensively to design the processor.

![processor](https://github.com/quantum2409/CS220/assets/98262532/d9ae0fb8-945f-4d5e-b95b-81fc0970a042)

## How to run the code

Use the following commands inside the project file location.

```bash
cd 'FOLDER_PATH'
iverilog -o out.vvp tb.v
gtkwave out.vcd
```

Note the iverilog and gtkwave needs to be set-up as a pre-requisite.

## Goals

A single-cycle MIPS processor (CSE BUBBLE) with the following features:
<ol>
  <li>32 bits word size</li>
  <li>VEDA memory architecture for: <ul>
    <li>Instruction Memory</li>
    <li>Data Memory</li>
  </ul></li>
  <li>A register file: RISC_BUBBLE- with 32 registers, where certain registers have the same role as in MIPS-32-ISA</li>
  <li>Design op-code formats for the processor to decide data paths</li>
</ol>
