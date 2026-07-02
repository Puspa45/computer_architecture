**Lab No: 1**
**Lab Title: Introduction to VHDL Programming and Open-Source Simulation Environment**

## Objective

• To install and configure the VHDL development tools such as VS Code, GHDL, and GTKWave.

• To gain knowledge of the basic structure and components of a VHDL program.

• To create, simulate, and observe the behavior of a simple VHDL design.

## Theory

VHDL (Very High Speed Integrated Circuit Hardware Description Language) is a standardized hardware description language developed for modeling digital systems. It is used to describe and simulate electronic circuits at various abstraction levels, from high-level behavioral descriptions to detailed gate-level representations. Unlike conventional programming languages that execute instructions sequentially, VHDL operates concurrently, allowing multiple hardware operations to occur simultaneously, similar to actual digital circuits.

### VHDL Structure

A VHDL program generally consists of three main components:

**Libraries and Packages:**
Libraries provide predefined functions, constants, and data types. The IEEE library is the most commonly used because it supports standard logic types and arithmetic operations.

**Entity:**
The entity block defines the external interface of the circuit. It specifies the input and output ports through which the circuit communicates.

**Architecture:**
The architecture block describes the internal functionality or behavior of the entity and determines how outputs are generated from inputs.

### Libraries and Packages

Libraries act as storage locations containing compiled VHDL units such as entities, packages, and architectures.

The commonly used libraries are:

**Library STD:**
This library is automatically included and contains fundamental data types such as integer, bit, character, and boolean.

**Library IEEE:**
This library provides advanced data types such as `std_logic` and `std_logic_vector`, which are widely used in digital circuit design.

Example:

`library IEEE;`
`use IEEE.STD_LOGIC_1164.ALL;`
`use IEEE.NUMERIC_STD.ALL;`

### Entity

The entity represents the external description of a circuit. It defines signal names, their directions, and data types.

Port directions include:

• **in:** Input signal entering the circuit.
• **out:** Output signal leaving the circuit.
• **inout:** Bidirectional signal.

Example of a two-input AND gate:

`entity AND_GATE is`
`port(`
`A : in std_logic;`
`B : in std_logic;`
`Y : out std_logic`
`);`
`end entity AND_GATE;`

### Architecture

The architecture specifies the internal operation of the circuit. It determines the logic used to generate outputs from inputs.

Example:

`architecture Behavioral of AND_GATE is`
`begin`
`Y <= A and B;`
`end architecture Behavioral;`

The statement `Y <= A and B;` is known as a concurrent signal assignment because it continuously checks input changes and updates the output automatically.

### Types of Architectural Models

VHDL supports different architecture styles:

**Behavioral Model:**
This model explains the operation of a circuit using process statements and sequential logic.

**Dataflow Model:**
This model uses concurrent assignments to show how data moves through the system.

**Structural Model:**
This model describes a circuit by connecting lower-level components together, similar to hardware schematics.

For this experiment, the Dataflow approach is mainly used due to its simplicity.

### Basic Data Types and Signals

**std_logic:**
Represents a single-bit signal and supports multiple states such as `0`, `1`, `Z`, and `U`.

**std_logic_vector:**
Represents a collection of bits. For example, `std_logic_vector(7 downto 0)` defines an 8-bit signal.

**Signals:**
Signals represent internal connections within an architecture and are declared before the `begin` statement.

Example:

`signal internal_wire : std_logic;`

`signal data_bus : std_logic_vector(7 downto 0);`

### VHDL Design Cycle

The development process of a VHDL design follows several stages:

**Analysis (Compilation):**
Checks the source code for syntax and semantic errors.

**Elaboration:**
Combines entities and architectures and establishes internal connections.

**Simulation:**
Applies input signals to verify circuit functionality.

**Visual Verification:**
Uses waveform viewers such as GTKWave to analyze signal changes over time.

## Discussion

In this experiment, an open-source VHDL development environment was successfully configured using VS Code, GHDL, and GTKWave. A simple buffer circuit was implemented to understand the complete workflow of designing and testing VHDL programs.

**Key Findings:**

• The entity block defined the input and output signals of the circuit.

• The architecture used the dataflow modeling technique where the output continuously followed the input signal.

• A testbench was created to apply different input values (`0 → 1 → 0`) and verify the behavior of the design.

• GTKWave was used to display waveform outputs and confirm that the input and output signals changed correctly.

This experiment helped demonstrate the important stages involved in hardware verification, including compilation, elaboration, and simulation.

## Conclusion

This laboratory exercise provided practical knowledge of VHDL programming and the simulation process. The experiment successfully demonstrated how to:

• Install and configure GHDL and GTKWave tools.

• Develop VHDL source files and testbench modules.

• Simulate and analyze circuit behavior using waveform outputs.

The results verified that the buffer circuit operated correctly. This experiment serves as a foundation for understanding more advanced VHDL designs and complex digital systems in future laboratory activities.

