## 4-Bit ALU (Addition & Subtraction) with 7-Segment Display — CircuitVerse

## Introduction
This project simulates a simple 4-bit ALU that performs addition and subtraction operations on 4-bit inputs and displays the result on a 7-segment display using CircuitVerse.

## Features
Inputs:

- 4-bit operand A (using 4 switches)

- 4-bit operand B (using 4 switches)

Outputs:

- 7-segment display showing the result (in decimal)

- Carry-out indicator LED (for addition overflow)

- Borrow-out indicator LED (for subtraction underflow)

## Components Used

- 7-segment display driver circuit

- Basic logic gates: AND, OR, XOR, NOT

- Switches and LEDs

## Working of 4-bit ALU Adiition:

- Step 1: Input Selection
The ALU takes two 4-bit operands:

Operand A (A3 A2 A1 A0)

Operand B (B3 B2 B1 B0)

Each bit is provided via switches or input lines.

- Step 2: Bit-wise Addition
The ALU performs binary addition at each bit position:

it adds three inputs: A bit, B bit, and Carry-in from the previous bit position.

It produces:

Sum bit (S) = A ⊕ B ⊕ Cin

Carry-out (Cout) = (A ⋅ B) + (B ⋅ Cin) + (A ⋅ Cin), which is passed to the next higher bit.

- Step 3: Ripple Carry Mechanism
The carry-out from each stage ripples into the next stage:

LSB (bit 0) → bit 1 → bit 2 → MSB (bit 3)


- Step 4: Carry-out Detection
After the addition of the MSB (bit 3):

If there's a Carry-out, it indicates overflow (result exceeds 4 bits).

This carry can be shown using an LED or used for further calculations.

Step 5: Displaying the Result
The 4-bit sum output (S3 S2 S1 S0) is fed into a 7-segment display encoder:

It converts the 4-bit binary result into signals to light up the correct segments.

The display shows the decimal equivalent of the sum.

![Main](https://github.com/user-attachments/assets/c6177cf8-482c-4285-9e08-637bc33bcd12)

## Working of 4-bit ALU Subtraction:
- Step 1: Input Selection
Two 4-bit binary numbers are selected:

Operand A (Minuend): A3 A2 A1 A0

Operand B (Subtrahend): B3 B2 B1 B0

- Step 2: Bit-wise Subtraction with Borrow
Subtraction is performed starting from the Least Significant Bit (LSB):

If A bit ≥ B bit → subtract directly

If A bit < B bit → borrow 1 from the next higher bit.

Difference (D) = A ⊕ B ⊕ Bin.

Borrow-out (Bout) = (NOT A ⋅ B) + (B ⋅ Bin) + (NOT A ⋅ Bin)


- Step 3: Borrow Propagation
If a borrow occurs at any bit, it is passed ("rippled") to the next higher bit position.

The process continues until the Most Significant Bit (MSB).

- Step 4: Borrow-out Detection
If there’s a borrow-out at MSB, it indicates that B > A and the result is negative.

In simple circuits, the output will show an incorrect result unless handled.

- Step 5: Displaying the Result
The 4-bit difference (D3 D2 D1 D0) is converted using a 7-segment display encoder:

It lights up the segments to show the decimal result.

If no borrow-out → result is positive

If borrow-out → result should be negative (but plain display won’t show sign without extra logic)



![Main (1)](https://github.com/user-attachments/assets/cb459341-dc6a-4bcd-8abe-6f18ad26c7bd)


## Applications
-Arithmetic operations in microprocessors

- Digital counters (up and down counters)

- Display systems (calculators, digital meters)
- BCD subtraction in digital calculators



## Conclusion
This project successfully demonstrates the design and implementation of a 4-bit Arithmetic Logic Unit (ALU) capable of performing addition and subtraction operations using only fundamental logic gates—AND, OR, XOR, and NOT.​

Addition: The addition operation was achieved by directly implementing the bit-wise sum and carry logic using XOR and AND gates, without relying on conventional adder circuits.​

Subtraction: Subtraction was performed by inverting the bits of the subtrahend and adding a borrow bit, effectively utilizing the borrow mechanism inherent in binary subtraction.​

This approach underscores the versatility of basic logic gates in constructing fundamental arithmetic operations, providing a deeper understanding of digital circuit design principles.

