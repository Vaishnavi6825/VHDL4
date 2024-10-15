# VHDL4
A Half Subtractor is a combinational logic circuit designed to perform the subtraction of two single-bit binary numbers. <br>
It has two inputs and two outputs: the difference and the borrow.  <br>
Outputs: Difference (Diff): Represents the result of A - B.  <br>
Borrow: Indicates whether a 1 has been borrowed from a higher bit in case A is smaller than B. <br>

`Aim`:
To design and implement a Half Subtractor using Verilog HDL, and verify its functionality through simulation.

`Apparatus Required:`

-Xilinx Vivado (or any Verilog simulator) <br>
-PC/Laptop with required software tools. <br>

`Code Implementation:`

#Dataflow Model:<br>
In this model, the circuit is described using logical expressions. The dataflow model relies on assign statements to represent the logical flow of data.<br>

module half_subtractor_dataflow(input a, input b, output diff, output borrow);<br>
  assign diff = a ^ b;<br>
  assign borrow = ~a & b;<br>
endmodule<br>


#Behavioral Model: <br>
The behavioral model uses an always block to describe the functionality of the Half Adder at an abstract level. It mimics how the circuit behaves without specifying exact hardware.

module half_subtractor_behavioral(input a, input b, output reg diff, output reg borrow);<br>
  always @(*) begin<br>
    diff = a ^ b;<br>
    borrow = ~a & b;<br>
  end<br>
endmodule<br>

#Structural Model:<br>
The structural model is a low-level description where the design is expressed using basic logic gates (AND, XOR). This is closest to actual hardware representation.<br>

module half_subtractor_structural(input a, input b, output diff, output borrow);<br>
  xor(diff, a, b);<br>
  and(borrow, ~a, b);<br>
endmodule<br>

![WhatsApp Image 2024-10-15 at 16 22 48_f5da00b5](https://github.com/user-attachments/assets/409d6adf-aa42-4fff-a769-6394bb4b95a2)

`Output Waveform:`

![WhatsApp Image 2024-10-15 at 16 20 01_c0b0a346](https://github.com/user-attachments/assets/06781a21-d051-4e1b-994c-14cfdfa9dd6a)

`Result:`

The half subtractor is a basic combinational logic circuit that efficiently subtracts two binary digits and provides the necessary outputs: difference and borrow. <br>

It is crucial for understanding how subtraction is implemented in digital systems and forms the foundation for more complex arithmetic circuits like the full subtractor, which deals with multi-bit numbers and borrowing between bits.








