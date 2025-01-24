# DEVELOP-A-SIMPLE-SYNCHRONOUS-RAM-MODULE-WITH-READ-AND-WRITE-OPERATIONS.

**COMPANY**: CODITECH IT SOLUTIONS

**NAME**: NISHTHA SHRIRANG PARANDE

**INTERN ID**: CT08FOI

**DOMAIN**: VLSI

**BATCH DURATION**: December 25th, 2024 to January 25th, 2025.

**MENTOR NAME**: NEELA SANTHOSH

**SIMPLE SYNCHRONOUS RAM MODULE WITH READ AND WRITE OPERATIONS:**
This repository contains the implementation of a simple synchronous RAM (Random Access Memory) module in Verilog. The module supports both read and write operations, adhering to a clocked synchronization mechanism for predictable performance in digital circuits.

**FEATURES:**
Clock Synchronous Design All operations are performed in synchronous with a clock signal.

**READ AND WRITE OPERATIONS:**
Write: 
Stores data at a specified address. Read: Retrieves data from a specified address. Parameterized Data and Address Widths (if applicable): Flexibility in configuring the data size and memory depth

**RAM Operations**
The RAM performs the following operations:

Write: Stores data into the specified memory address when the write enable (we) signal is high.

Read: Outputs data from the specified memory address on every clock cycle.
FILE LIST:FILE LIST include

**Source code for the RAM module.**
Testbench code to validate the module functionality.
Supporting scripts for simulation and synthesis (if any).
HOW TO USE: Clone this repository: bash Copy code git clone [repository-url] Navigate to the project directory and run the simulation using preferred EDA tool . Modify parameters like DATA_WIDTH or ADDR_WIDTH to fit design needs. Example Code Snippet: verilog Copy code module sync_ram ( input wire clk, input wire we, // Write Enable input wire [ADDR_WIDTH-1:0] addr, input wire [DATA_WIDTH-1:0] data_in, output reg [DATA_WIDTH-1:0] data_out ); // Implementation here endmodule

TESTING: It Correct write and read operations.
**Testbench**
The testbench  provides a set of test cases to verify the RAM's functionality. It monitors the signals and prints the results of read and write operations.

**Simulation Report**
The simulation report contains the output of the RAM for different test cases, demonstrating the correctness of the desig
