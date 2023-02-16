# UART Verilog
## UART (TX & RX) in Verilog
- UART Transmitter :  
This transmitter is able to transmit 8 bits of serial data, one start bit, one stop bit, and no parity bit.  When transmit is complete o_Tx_done will be driven high for one clock cycle.
- Set Parameter CLKS_PER_BIT as follows:
CLKS_PER_BIT = (Frequency of i_Clock)/(Frequency of UART)
Example: 25 MHz Clock, 115200 baud UART
(25000000)/(115200) = 217
- Testbench will exercise the UART RX.
It sends out byte 0x37, and ensures the RX receives it correctly.
- Testbench uses a 25 MHz clock
 Want to interface to 115200 baud UART
 25000000 / 115200 = 217 Clocks Per Bit.

- Simulations were done iverilog on Windows. You can download it form : https://bleyer.org/icarus/
For running the testbench and viewing waveforms in GTKWave, run these 3 commands below in terminal :

iverilog -o testbench.vvp testbench.v

vvp testbecnh.vvp

gtkwave
