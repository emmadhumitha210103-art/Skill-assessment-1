# Skill-assessment-1
Question
Write an assembly language program in 8086 to exchange the contents of two memory blocks of equal length.

Aim
To write an 8086 assembly language program to exchange the contents of two memory blocks of equal length.

Algorithm
- Start the program.
- Initialize the Data Segment.
- Store the starting addresses of both memory blocks in two registers (e.g., SI and DI).
- Load the counter register (CX) with the number of bytes to be exchanged.
- Repeat the following steps until all bytes are swapped:
- Move the byte from the first block (pointed by SI) into AL.
- Move the byte from the second block (pointed by DI) into BL.
- Exchange the contents of AL and BL.
- Store AL in the second block and BL in the first block.
- Increment SI and DI.
- Decrement the counter CX.
- Stop when all bytes are exchanged.
- Terminate the program.

Program

DATA SEGMENT
BLOCK1 DB 10H, 20H, 30H, 40H, 50H     
BLOCK2 DB 60H, 70H, 80H, 90H, 0A0H     
COUNT  DB 05H                          
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA

START:
    MOV AX, DATA     
    MOV DS, AX
    MOV CL, COUNT     
    LEA SI, BLOCK1
    LEA DI, BLOCK2  

EXCHANGE:
    MOV AL, [SI]     
    MOV BL, [DI]      
    MOV [SI], BL      
    MOV [DI], AL      
    INC SI          
    INC DI
    DEC CL            
    JNZ EXCHANGE     
    MOV AH, 4CH       
    INT 21H
CODE ENDS
END START

Output







Result
The 8086 assembly program was successfully executed, and the contents of the two memory blocks were exchanged correctly.
