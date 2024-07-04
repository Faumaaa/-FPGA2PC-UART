# -FPGA2PC-UART
This project demonstrates communication between an FPGA and a PC using the UART protocol. The FPGA code is written in Verilog and includes three main modules: transmitter, receiver, debouncing button check, and a top module. Additionally, it includes an FPGA constraint mapping file.

Modules
1. UART Transmitter
Function: Sends data from the FPGA to the PC.
Working: Serially transmits 8-bit data frames with start and stop bits. Data is loaded into a buffer and shifted out bit by bit at the specified baud rate.
2. UART Receiver
Function: Receives data from the PC to the FPGA.
Working: Listens for a start bit and then reads the incoming serial data, reconstructing the 8-bit data frames. It synchronizes with the baud rate and checks for framing errors.
3. Debouncing Button Check
Function: Eliminates noise from mechanical button presses.
Working: Samples the button state over some time to ensure a stable and clean signal is sent to the FPGA logic. It helps prevent the false triggering of button presses.
4. Top Module
Function: Integrates all submodules and manages overall system functionality.
Working: Connects the transmitter, receiver, and debouncing button check modules. Coordinates data flow and control signals, ensuring smooth communication between the FPGA and PC.
FPGA Constraint Mapping File
Function: Maps FPGA I/O pins to specific physical pins on the FPGA board.
Working: Defines the pin assignments for UART signals (TX, RX), buttons, and other I/O peripherals. Ensures proper electrical connections and functionality.

---
All Verilog module files are uploaded to this repository, and this project has been run on ISE Project Navigator. It is also compatible with ModelSim and online Verilog compilers.
