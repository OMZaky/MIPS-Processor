# Custom MIPS Processor Design in VHDL

## Overview
This repository contains a complete, custom MIPS processor design implemented in VHDL. Developed for the CSE221: Computer Architecture course at Ain Shams University, this processor simulates both the data and control paths of a computer system. The design goes beyond standard architecture by incorporating a custom-extended instruction set, including advanced memory access and complex branching logic.

The implementation was structured progressively, building from basic arithmetic operations to a fully functioning processor capable of handling memory access, branching, and advanced custom instructions.

## Architecture and Core Components



The processor architecture is designed to handle a comprehensive set of instructions through a robust datapath and control unit system.

### 1. Datapath & ALU
* **Register File**: A custom module designed to read simultaneously from two registers and write into a third. The register file was specifically modified to support simultaneous auto-increment load operations (`lw_incr`).
* **ALU (Arithmetic Logic Unit)**: A modified 32-bit full ALU capable of performing standard operations including `AND`, `OR`, `ADD`, `SUB`, `NOR`, and `SLT`.

### 2. Control & Memory Integration
* **Control Unit**: A central control module responsible for generating all necessary control signals across the datapath to orchestrate instruction execution.
* **Memory Modules**: Seamless connection of the MIPS datapath and control modules with distinct instruction and data memory modules.

## Advanced Architectural Features
This processor features several advanced architectural modifications to enhance functionality and control flow:
* **Advanced Memory Access**: Implemented the `lwr` (Load Word Right) instruction, alongside `lw_incr`, which simultaneously loads data and auto-increments the target address within the Register File.
* **Extended Branching Logic**: Added support for complex conditional branches beyond standard equality, including `ble` (Branch on Less Than or Equal), `bgt` (Branch on Greater Than), `blt` (Branch on Less Than), and `bte`.
* **Advanced Jump Instructions**: Integrated `jm`, `jalm`, and `jalr` (Jump and Link Register) for extended control flow and dynamic subroutine handling.

## Supported Instruction Set Architecture (ISA)
The processor has been tested and verified to support the following assembly instructions:
* **Arithmetic & Logic**: `add`, `sub`, `and`, `or`, `slt`
* **Immediate**: `addi`
* **Memory Access**: `lw`, `sw`, `lwr`, `lw_incr`
* **Control Flow**: `beq`, `ble`, `bgt`, `blt`, `bte`, `j`, `jm`, `jalm`, `jalr`

## Simulation and Testing
The processor's functionality is verified against a MIPS assembly test program loaded into the instruction memory.
* The test program initializes registers, performs a sequence of logical and arithmetic operations, and validates branching logic.
* A successful simulation run culminates in the processor writing the value `7` to memory address `84`.

**To run the simulation:**
Load the `.vhd` source files into your preferred simulation environment (such as Vivado). Compile the blocks, run the behavioral simulation, and verify that the test cases pass by observing the final memory state and register waveforms.

## Repository Structure
* `src/`: Contains all `.vhd` source files for the project, including the Register File, ALU, Control Unit, and the Top-Level MIPS module.
* `docs/`: Includes the comprehensive project report detailing the datapath extensions, implementation choices, sample simulation outputs, non-standard assumptions, and a breakdown of the team's contributions.
