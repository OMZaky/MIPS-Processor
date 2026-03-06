# Custom MIPS Processor Design in VHDL

## Overview
[cite_start]This repository contains a complete, custom MIPS processor design implemented in VHDL[cite: 11]. [cite_start]Originally developed as a project for the CSE221: Computer Architecture course at Ain Shams University [cite: 1, 6][cite_start], this processor simulates both the data and control paths of a computer system[cite: 11]. The design goes beyond standard architecture by incorporating a custom-extended instruction set, including advanced memory access and complex branching logic.

[cite_start]The implementation was structured progressively, building from basic arithmetic operations to a fully functioning processor capable of handling memory access, branching, and advanced custom instructions[cite: 12].

## Architecture and Core Components



The processor architecture is designed to handle a comprehensive set of instructions through a robust datapath and control unit system.

### 1. Datapath & ALU
* [cite_start]**Register File**: A custom module designed to read simultaneously from two registers and write into a third[cite: 26]. The register file was specifically modified to support simultaneous auto-increment load operations (`lw_incr`).
* [cite_start]**ALU (Arithmetic Logic Unit)**: A modified 32-bit full ALU capable of performing standard operations including `AND`, `OR`, `ADD`, `SUB`, `NOR`, and `SLT`[cite: 35, 37, 42].

### 2. Control & Memory Integration
* [cite_start]**Control Unit**: A central control module responsible for generating all necessary control signals across the datapath to orchestrate instruction execution[cite: 67].
* [cite_start]**Memory Modules**: Seamless connection of the MIPS datapath and control modules with distinct instruction and data memory modules[cite: 69].

## Advanced Architectural Features
This processor features several advanced architectural modifications to enhance functionality and control flow:
* **Advanced Memory Access**: Implemented the `lwr` (Load Word Right) instruction, alongside `lw_incr`, which simultaneously loads data and auto-increments the target address within the Register File.
* **Extended Branching Logic**: Added support for complex conditional branches beyond standard equality, including `ble` (Branch on Less Than or Equal), `bgt` (Branch on Greater Than), `blt` (Branch on Less Than), and `bte`.
* **Advanced Jump Instructions**: Integrated `jm`, `jalm`, and `jalr` (Jump and Link Register) for extended control flow and dynamic subroutine handling.

## Supported Instruction Set Architecture (ISA)
The processor has been tested and verified to support the following assembly instructions:
* [cite_start]**Arithmetic & Logic**: `add`, `sub`, `and`, `or`, `slt` [cite: 42, 155]
* [cite_start]**Immediate**: `addi` [cite: 155]
* [cite_start]**Memory Access**: `lw`, `sw`[cite: 65, 155], `lwr`, `lw_incr`
* [cite_start]**Control Flow**: `beq` [cite: 65, 155][cite_start], `ble`, `bgt`, `blt`, `bte`, `j`[cite: 65, 155], `jm`, `jalm`, `jalr`

## Simulation and Testing
[cite_start]The processor's functionality is verified against a MIPS assembly test program loaded into the instruction memory[cite: 69, 134].
* [cite_start]The test program initializes registers, performs a sequence of logical and arithmetic operations, and validates branching logic[cite: 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153].
* [cite_start]A successful simulation run culminates in the processor writing the value `7` to memory address `84`[cite: 153, 156].

**To run the simulation:**
Load the VHDL source files into your preferred simulation environment (e.g., Vivado). [cite_start]Compile the blocks, run the simulation, and verify that the test cases pass by observing the final memory state and register waveforms[cite: 52, 53, 54, 70].

## Repository Structure
* [cite_start]`src/`: Contains all `.vhd` source files for the project, including the Register File, ALU, Control Unit, and the Top-Level MIPS module[cite: 22].
* [cite_start]`docs/`: Includes the comprehensive project report detailing the datapath extensions, implementation choices, sample simulation outputs, non-standard assumptions, and a breakdown of the team's contributions[cite: 14, 164, 165, 166, 167, 168, 169].
