# mpmc-skill-assignment-1


## AIM
Write an assembly language program in 8051 to calculate the sum of 5 numbers stored sequentially in memory and store the result in a another memory location.

## APPARATUS REQUIRED
Personal computer with Keil software

## ALGORITHM

1.Initialize pointer register (R0) to the starting address of the 5 numbers (e.g., 30H).

2.Clear accumulator A to 00H (will hold running sum).

3.Load counter (R1) with 05 (number of data elements).

4.Loop:

5.Save the current sum into B (MOV B,A).

6.load the current data byte from memory pointed by R0 into A (MOV A,@R0).

7.Add previous sum (in B) to current number (ADD A,B) → new running sum in A.

8.Increment pointer R0 to next data byte.

9.Decrement counter R1 and repeat loop until zero.

10.Store final sum from A into a chosen internal RAM location (e.g., 35H).

11.End / infinite loop or RET.



## PROGRAME
```
ORG 0000H

MOV R0, #30H      ; Pointer to first number
MOV R1, #5        ; Number count
CLR A             ; Clear accumulator for sum

SUM_LOOP:
    MOV B, A      ; Save sum temporarily in B
    MOV A, @R0    ; Load current number
    ADD A, B      ; Add previous sum from B
    INC R0        ; Next number
    DJNZ R1, SUM_LOOP

MOV 35H, A        ; Store result

END
```

## OUTPUT
<img width="1600" height="680" alt="image" src="https://github.com/user-attachments/assets/3e148558-d80f-428f-98a2-c670df798191" />
<img width="1600" height="700" alt="image" src="https://github.com/user-attachments/assets/ed972f65-ded9-4b4c-9d59-90bcfbe1ffeb" />

## RESULT
Thus, the sum of five numbers stored sequentially in memory was calculated and executed successfully using 8051 microcontroller.

