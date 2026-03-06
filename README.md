# MIPS Processor Design in VHDL

## Overview
This repository contains a complete MIPS processor design implemented in VHDL. The project simulates both the data and control paths of a basic computer system and was developed as the major task for the CSE221: Computer Architecture course at Ain Shams University. 

The implementation was divided into two main phases, progressively building from basic arithmetic operations to a fully functioning processor capable of handling memory access, branching, and custom bonus instructions.

## Architecture and Features



The processor architecture is designed to handle a comprehensive set of instructions through a robust datapath and control unit system. 

### Phase I: Core Components
* **Register File**: A custom module designed to read simultaneously from two registers and write into a third.
* **ALU (Arithmetic Logic Unit)**: A modified 32-bit full ALU capable of performing standard operations including `AND`, `OR`, `ADD`, `SUB`, `NOR`, and `SLT`.
* **R-Type Execution**: Integration of the register file and ALU to successfully execute fundamental R-type instructions.

### Phase II: Advanced Operations & Memory
* **Control Unit**: Implementation of a central control module responsible for generating all necessary control signals across the datapath.
* **Extended Instruction Support**: Modification of the MIPS CPU to perform I-type (`lw`, `sw`, `beq`) and J-type (`j`) instructions alongside the existing R-type instructions.
* **Memory Integration**: Seamless connection of the MIPS datapath and control modules with distinct instruction and data memory modules.

### Bonus Implementations
Going beyond the core project requirements, this processor features several advanced instructions and architectural modifications:
* **Advanced Memory Access**: Implemented the `lwr` (Load Word Right) instruction.
* **Extended Branching Logic**: Added support for complex conditional branches, including `ble` (branch on less than or equal), `bgt` (branch on greater than), `blt` (branch on less than), and `bte`.
* **Advanced Jump Instructions**: Integrated `jm`, `jalm`, and `jalr` (Jump and Link Register) for extended control flow and subroutine handling.
* **Auto-Increment Load**: Implemented `lw_incr`, which included custom modifications to the Register File to support simultaneous load and address increment operations.

## Supported Instruction Set
The processor has been tested and verified to support the following MIPS assembly instructions:
* **Arithmetic & Logic**: `add`, `sub`, `and`, `or`, `slt`
* **Immediate**: `addi`
* **Memory Access**: `lw`, `sw`, `lwr`, `lw_incr`
* **Control Flow**: `beq`, `ble`, `bgt`, `blt`, `bte`, `j`, `jm`, `jalm`, `jalr`

## Simulation and Debugging
The processor's functionality is verified against a comprehensive MIPS assembly test program loaded into the instruction memory. 
* The primary test case initializes registers, performs a sequence of logical and arithmetic operations, and tests branching logic.
* A successful simulation run culminates in the processor writing the value `7` to memory address `84`.

**To run the simulation:**
Load the VHDL source files and the included testbench into your preferred environment (e.g., Vivado). Compile the modules, run the behavioral simulation, and observe the waveform outputs to verify the register and memory states during execution.

## Repository Structure
* `src/`: Contains all `.vhd` source files for the project, including the Register File, ALU, Control Unit, and the Top-Level MIPS module.
* `docs/`: Includes the comprehensive project report detailing implementation choices, datapath extensions, sample simulation outputs, non-standard assumptions, and a breakdown of team contributions.
