# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates:
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D

F2=xy’z+x’y’z+w’xy+wx’y+wxy

## Equipments Required:
  1.Hardware – PCs, Cyclone II , USB flasher.
  
  2.Software – Quartus prime.
## Theory:
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates:
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Procedure:
1.Create a project with required entities.

2.Create a module along with respective file name.

3.Run the respective programs for the given boolean equations.

4.Run the module and get the respective RTL outputs.

5.Create university program(VWF) for getting timing diagram.

6.Give the respective inputs for timing diagram and obtain the results.

## Program:

Program to implement the given logic function and to verify its operations in quartus using Verilog programming.

Developed by: Leann Joby Mathew

RegisterNumber:  212222230074
python
module logic(a,b,c,d,w,x,y,z,f1,f2);
input a,b,c,d,w,x,y,z;
output f1,f2;
wire A1,A2,A3,A4,A5,B1,B2,B3,B4,B5;
assign A1=((~a)&(~b)&(~c)&(~d));
assign A2=(a&(~c)&(~d));
assign A3=((~b)&c&(~d));
assign A4=((~a)&b&c&d);
assign A5=(b&(~c)&d);
assign B1=(x&(~y)&z);
assign B2=((~x)&(~y)&z);
assign B3=((~w)&x&y);
assign B4=(w&(~x)&y);
assign B5=(w&x&y);
assign f1=A1|A2|A3|A4|A5;
assign f2=B1|B2|B3|B4|B5;
endmodule

## Output:
## RTL realization:
![WhatsApp Image 2023-04-26 at 14 07 52](https://user-images.githubusercontent.com/121222763/234522444-db5ef569-cbc4-42f9-bffe-2f5869a3ec5c.jpg)

## Timing Diagram:
![WhatsApp Image 2023-04-26 at 14 08 32](https://user-images.githubusercontent.com/121222763/234522518-16250082-e268-41dd-b0d1-2fdf9bd07f3a.jpg)
## Truth table:
![WhatsApp Image 2023-04-26 at 14 07 45](https://user-images.githubusercontent.com/121222763/234522624-56fff42e-df4f-4b2a-a1a3-e662f6c1f132.jpg)

## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.
