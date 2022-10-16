# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

1.Use module projname(input,output) to start the Verilog programmming. 
2.Assign inputs and outputs using the word input and output respectively.
3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression. 
4.Use each output to represnt onre for differnce and the other for borrow. 
5.End the verilog program using keyword endmodule. 

## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: G Jayanth.
RegisterNumber: 212221230030. 
```
```
HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

FULL SUBTRACTOR

module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```

## Output:

## Half Subtractor:
### Logic Symbol:
![2a](https://user-images.githubusercontent.com/93427345/196042561-c9addcbc-26d1-4af8-925a-3314516890af.png)

### Truthtable
![2b](https://user-images.githubusercontent.com/93427345/196042570-67f4ed18-b640-4d91-8132-168d81ae874e.png)

### RTL realization
![2c](https://user-images.githubusercontent.com/93427345/196042583-5cd8b6d7-a9e4-49be-ad66-64c7bcf6450c.png)

### Timing diagram 
![2d](https://user-images.githubusercontent.com/93427345/196042615-59ac8735-8d0a-443c-973d-12385073728e.png)

## Full Subtractor:
### Logic Symbol:
![2e](https://user-images.githubusercontent.com/93427345/196042705-f65a9eb8-9ca9-40ee-b5b2-517a76c1194e.png)

### Truth Table:
![2f](https://user-images.githubusercontent.com/93427345/196042719-050d7ebf-cab1-42de-96ce-616e3ffee611.png)

### RTL realization:
![2g](https://user-images.githubusercontent.com/93427345/196042769-76dbfc23-a136-4509-bed6-0dc6e8aa0da3.png)

### Timing diagram:
![2h](https://user-images.githubusercontent.com/93427345/196042781-d9d8787a-3183-44cc-86de-a702e12b3651.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
