# 8-to-1-Multiplexer

## Overview
This repository contains the design, implementation, and Universal Verification Methodology (UVM) testbench for an 8-to-1 multiplexer. An 8-to-1 multiplexer selects one of the eight input signals and forwards the selected input to the output based on a 3-bit selector.

## Features
- 8 data inputs (`D0` to `D7`)
- 3 selector inputs (`S0`, `S1`, `S2`)
- Single output (`Y`)
- Fully verified using UVM
- Suitable for digital logic design and VLSI implementation

## Files
- `rtl/mux_8to1.v`: Verilog RTL code for the 8-to-1 multiplexer
- `testbench/testbench.v`: Basic testbench for initial functional simulation
- `uvm_env/top_env.sv`: UVM environment setup
- `uvm_env/seq.sv`: UVM sequences
- `uvm_env/driver.sv`: UVM driver
- `uvm_env/monitor.sv`: UVM monitor
- `uvm_env/scoreboard.sv`: UVM scoreboard
- `waveform.vcd`: Sample output waveform
- `README.md`: Documentation

## Truth Table
| S2 | S1 | S0 | Output (Y) |
|----|----|----|------------|
|  0 |  0 |  0 | D0         |
|  0 |  0 |  1 | D1         |
|  0 |  1 |  0 | D2         |
|  0 |  1 |  1 | D3         |
|  1 |  0 |  0 | D4         |
|  1 |  0 |  1 | D5         |
|  1 |  1 |  0 | D6         |
|  1 |  1 |  1 | D7         |

## How to Run

### Prerequisites
Ensure you have the following installed:
- Verilog simulator (e.g., Icarus Verilog, ModelSim)
- UVM library (SystemVerilog UVM package)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/8to1-mux.git
   cd 8to1-mux
   ```

2. Compile the Verilog code and testbench:
   ```bash
   iverilog -o mux_sim rtl/mux_8to1.v testbench/testbench.v
   ```

3. For UVM simulation:
   ```bash
   vlog -sv rtl/mux_8to1.v uvm_env/*.sv
   vsim -c top_env -do "run -all"
   ```

4. View the waveform (optional):
   ```bash
   gtkwave waveform.vcd
   ```

## Example Output
For selector inputs `S2 S1 S0 = 101`, the output `Y` will match `D5`.

## Future Improvements
- Add support for enable/disable functionality
- Implement power-efficient design
- Synthesize using OpenROAD for physical design
- Enhance UVM environment with coverage and assertions


Feel free to contribute or report issu
## Author's
# ARUN CHAVAN
