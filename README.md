
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
WAIT:JNB TI, WAIT
CLR TI 
END
```
### (ii) Serial Port to Transfer a Message

```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ B,AGAIN
END
```

### OUTPUT:

<img width="640" height="854" alt="image" src="https://github.com/user-attachments/assets/84e4a516-247f-4134-af2a-1fc6c7ec085f" />
<img width="640" height="894" alt="image" src="https://github.com/user-attachments/assets/bc63ef9d-939a-4441-afdc-470238dd4c9c" />

<img width="640" height="858" alt="image" src="https://github.com/user-attachments/assets/e6433a2d-6b61-4fe9-a0be-fa8825dfc420" />
<img width="640" height="963" alt="image" src="https://github.com/user-attachments/assets/6a8dc7b0-554d-4242-acb5-823bcf0059c6" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
