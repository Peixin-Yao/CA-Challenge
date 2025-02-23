LAB2:

INTRO:
The design is improved by introducing a new function in MOVC1. 
It can perform both unsigned and signed multiplication.

Hardware Improvement:
1. In the dpdecode sheet, a new output called "MUL" will be 1 if ins(14:12)=000, ins(8)=0 and ins(2)=1.
2. The MUL is directing towards a new input of ALU called "MULEN".
3. Inside ALU, The "MULEN" acts as a selector of a new multiplexer to decide passing MOV or MOVC1.
4. A new sheet "MUL" is designed to perform 16-bit times 4-bit multiplication. It involves 48 full adders.
5. The "MUL" sheet is introduced in ALU and connected with one port of the new multiplexer.

Software Improvement:
1. MOVC1 can perform multiplication of 16-bit times 4-bit in one cycle.
2. There are CMP codes to check the values of factors (less than 4 bits? more than 4 bits? signed number?),
so can save unnecessary clock cycles.

Sample Machine-code Intro:
1. LE4bit.ram tests the multiplication of one of factors less than 4 bits.
2. GE4bit.ram tests the multiplication of factors greater than or equal to 4 bits.
3. signed.ram tests the multiplication of signed factors.
4. ram starting with norm is the reference multiply code introducing by the Lab 2

Exact data of improvement:
1. LE4bit:
   new design: 3 CLK (with 2 initialization CLKs included)
   old design: 36 CLK
   Improvement: 12x faster
2. GE4bit:
   new design: CLK
   old design:  CLK
   Improvement: x faster
3. signed:
   new design: CLK
   old design: 145 CLK
   Improvement:  faster   
