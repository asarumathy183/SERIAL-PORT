
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

<img width="640" height="883" alt="image" src="https://github.com/user-attachments/assets/5fad1d79-b658-4f81-8605-f332d78a12e4" />
<img width="640" height="802" alt="image" src="https://github.com/user-attachments/assets/e89091ff-21e3-41e7-95f1-4b8706ad17d7" />

<img width="631" height="813" alt="image" src="https://github.com/user-attachments/assets/1ba203b3-bd03-442f-b4a3-e5a083ce1298" />
<img width="640" height="837" alt="image" src="https://github.com/user-attachments/assets/1e1c5b92-ffdc-4cf8-816c-327de56069e4" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
