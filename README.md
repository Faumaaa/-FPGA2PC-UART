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

Functionality
This project allows the FPGA to communicate with a PC through the UART protocol. It can be used to send and receive data between the FPGA and PC, making it useful for various applications such as data logging, debugging, and control systems.

Viewing Data on Terminal
To view the numbers entered by the computer on the terminal, you can use TeraTerm software. TeraTerm is a free, open-source terminal emulator that supports serial communication. It provides an interface to monitor the data being sent and received through the UART connection.

Install TeraTerm: Download and install TeraTerm from https://ttssh2.osdn.jp/.

Connect to UART:

Open TeraTerm.
Select the serial port connected to the FPGA.
Configure the baud rate and other settings to match the FPGA's UART configuration.
Monitor Data: Enter numbers on the PC and see them displayed on the TeraTerm terminal, verifying successful communication between the FPGA and PC
Below I have attached block diagram, RTL diagrams and output pics to make to better understand the project.

Block Diagram

![block diagram](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/8422fcd5-4bf0-468e-acc2-77fd9cdd229c)

RTL Schematics

![RTL pic1](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/5687140d-3228-46f4-9282-84e68b7f7108)

![RTL pic2](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/edc5e170-5c2a-4bfb-915f-ec1094d73194)

![RTL pic 3](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/4788ea4f-114a-4bc2-8fb8-f0a051e54427)

Outputs:


![fpga](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/dee6773a-61fd-4253-8412-bbc90ecd1ed3)
![output](https://github.com/Faumaaa/-FPGA2PC-UART/assets/134162066/966c1b67-65de-4328-b5f1-2df5063fec17)

---
All Verilog module files are uploaded to this repository, and this project has been run on ISE Project Navigator. It is also compatible with ModelSim and online Verilog compilers.
