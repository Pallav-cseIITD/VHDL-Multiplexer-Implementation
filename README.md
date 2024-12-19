# VHDL-Multiplexer-Implementation
\# VHDL Multiplexer Implementation

\#\# Project Overview

This project implements multiplexer circuits using VHDL on a Basys 3 FPGA board. The implementation focuses on building multiplexers using basic logic gates (AND, OR, NOT) with a structural design approach, demonstrating fundamental digital design principles.

\#\# Circuit Designs

\#\#\# 2x1 Multiplexer

The 2x1 multiplexer is implemented using basic logic gates:

\- 2 AND gates

\- 1 OR gate

\- 1 NOT gate

Circuit Structure:

\`\`\`

Input Ports:

\- d1: First data input

\- d2: Second data input

\- s: Select line

Output Port:

\- o: Output signal

Internal Logic:

\- NOT gate inverts the select signal

\- AND1 gates combines d1 with inverted select

\- AND2 gates combines d2 with select

\- OR gate combines both AND outputs

\`\`\`

\#\#\# 4x1 Multiplexer

Built using three 2x1 multiplexers in a cascaded arrangement:

\- First layer: Two 2x1 MUXes for initial input selection

\- Second layer: One 2x1 MUX for final output selection

\- Requires 2 select lines for 4 input combinations

\#\# Implementation Details

\#\#\# VHDL Components

1\. Basic Gates:

\- \`and_gate.vhd\`: Two-input AND gate

\- \`or_gate.vhd\`: Two-input OR gate

\- \`not_gate.vhd\`: Single input NOT gate

2\. Multiplexers:

\- \`mux_2x1.vhd\`: 2x1 multiplexer using basic gates

\- \`mux_4x1.vhd\`: 4x1 multiplexer using 2x1 multiplexers

\#\#\# Structural Design

\- Pure structural VHDL implementation

\- No behavioral constructs (process, if-else, case statements)

\- Component instantiation and port mapping for all connections

\- Hierarchical design approach

\#\# Hardware Implementation

\#\#\# Basys 3 FPGA Board Setup

1\. 2x1 Multiplexer:

\- 2 switches for input data (d1, d2)

\- 1 switch for select line

\- 1 LED for output display

2\. 4x1 Multiplexer:

\- 4 switches for input data

\- 2 switches for select lines

\- 1 LED for output display

\#\#\# Resource Utilization

\- Minimal FPGA resources used

\- Implementation uses only basic LUTs

\- No flip-flops, BRAMs, or DSPs required

\#\# Testing and Verification

\#\#\# Simulation

\- Comprehensive testbenches for all components

\- Verification of:

\- Individual gates

\- 2x1 multiplexer functionality

\- 4x1 multiplexer operation

\- Complete system integration

\#\#\# Hardware Verification

\- Physical testing on Basys 3 board

\- Input combinations verified using switches

\- Output monitoring through LED indicators

\#\# File Structure

\`\`\`

├── src/

│ ├── basic_gates/

│ │ ├── and_gate.vhd

│ │ ├── or_gate.vhd

│ │ └── not_gate.vhd

│ ├── multiplexers/

│ │ ├── mux_2x1.vhd

│ │ └── mux_4x1.vhd

│ └── testbench/

│ ├── gates_tb.vhd

│ ├── mux_2x1_tb.vhd

│ └── mux_4x1_tb.vhd

├── constraints/

│ ├── mux_2x1.xdc

│ └── mux_4x1.xdc

└── bitstreams/

├── mux_2x1.bit

└── mux_4x1.bit

\`\`\`


4\. Programming the FPGA:

\- Connect Basys 3 board

\- Program device using generated bitstream

\- Test using onboard switches and LEDs

\#\# Design Decisions

1\. Pure structural implementation for better understanding of digital logic

2\. Hierarchical design approach for modularity and reusability

3\. Separate testbenches for each component for thorough verification

4\. Clear port mapping using named association for better readability
