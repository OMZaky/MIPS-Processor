# Custom MIPS Processor Design in VHDL

## Overview
[cite_start]This repository contains a complete MIPS processor design implemented in VHDL[cite: 6]. [cite_start]The project illustrates a basic computer system by simulating the data and control paths[cite: 11]. [cite_start]It was developed for the CSE221: Computer Architecture course at Ain Shams University[cite: 1, 6]. The design goes beyond standard architecture by incorporating a custom-extended instruction set, including advanced memory access and complex branching logic.

[cite_start]The implementation was structured progressively in two phases [cite: 12][cite_start], building from basic arithmetic operations to a fully functioning processor capable of handling memory access, branching, and advanced custom instructions[cite: 65].

## Architecture and Core Components



The processor architecture is designed to handle a comprehensive set of instructions through a robust datapath and control unit system.

### 1. Datapath & ALU
* [cite_start]**Register File**: A custom module designed to read simultaneously from two registers and write into another[cite: 26]. The register file was specifically modified to support simultaneous auto-increment load operations (`lw_incr`).
* [cite_start]**ALU (Arithmetic Logic Unit)**: A modified 32-bit full ALU [cite: 35] [cite_start]capable of performing standard operations including `AND`, `OR`, `ADD`, `SUB`, `NOR`, and `SLT`[cite: 37, 42].

### 2. Control & Memory Integration
* [cite_start]**Control Unit**: A central control module responsible for all of the control signals[cite: 67].
* [cite_start]**Memory Modules**: Seamless connection of the MIPS datapath and control modules with distinct instruction and data memory modules[cite: 69].

## Advanced Architectural Features
This processor features several advanced architectural modifications to enhance functionality and control flow:
* **Advanced Memory Access**: Implemented the `lwr` (Load Word Right) instruction, alongside `lw_incr`, which simultaneously loads data and auto-increments the target address within the Register File.
* **Extended Branching Logic**: Added support for complex conditional branches beyond standard equality, including `ble` (Branch on Less Than or Equal), `bgt` (Branch on Greater Than), `blt` (Branch on Less Than), and `bte`.
* **Advanced Jump Instructions**: Integrated `jm`, `jalm`, and `jalr` (Jump and Link Register) for extended control flow and dynamic subroutine handling.

## Supported Instruction Set Architecture (ISA)
The processor has been tested and verified to support the following assembly instructions:
* [cite_start]**Arithmetic & Logic**: `add`, `sub`, `and`, `or`, `slt`[cite: 155].
* [cite_start]**Immediate**: `addi`[cite: 155].
* [cite_start]**Memory Access**: `lw`, `sw`[cite: 65, 155], `lwr`, `lw_incr`.
* [cite_start]**Control Flow**: `beq`, `j`[cite: 65, 155], `ble`, `bgt`, `blt`, `bte`, `jm`, `jalm`, `jalr`.

## Simulation and Testing
[cite_start]The processor's functionality is verified against a MIPS assembly test program loaded into the instruction memory[cite: 108, 134].
* [cite_start]The test program initializes registers, performs a sequence of logical and arithmetic operations, and validates branching logic[cite: 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145].
* [cite_start]If successful, it should write the value 7 to address 84[cite: 156].

**To run the simulation:**
[cite_start]Load the `.vhd` source files [cite: 61] into your preferred simulation environment. [cite_start]Compile the blocks, run the simulation, and ensure you pass all test cases [cite: 159, 160] by verifying the final memory state.

## Repository Structure
* [cite_start]`src/`: Contains all `.vhd` source files for the project[cite: 22, 61].
* [cite_start]`docs/`: Includes the fully detailed and described project report[cite: 14]. [cite_start]This covers a brief description of the implementation and design choices [cite: 165][cite_start], datapath extensions [cite: 166][cite_start], sample output [cite: 167][cite_start], non-standard assumptions [cite: 168][cite_start], and a breakdown showing the contribution of each student[cite: 169].
