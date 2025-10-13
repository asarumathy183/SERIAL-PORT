
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character
```
#include<reg51.h>
void main(void)
{
TMOD=0X20; //TIMER 1, MODE 2
TH1=0XFA;
SCON=0X50;
TR1=1;
while(1)
{
SBUF='B';
while(TI==0);
T1=0;
}
}
```
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
#include<reg51.h>
void main(void)
{
unsigned char msg[]="Sarumathy A";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```
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

<img width="640" height="894" alt="image" src="https://github.com/user-attachments/assets/bc63ef9d-939a-4441-afdc-470238dd4c9c" />

<img width="640" height="963" alt="image" src="https://github.com/user-attachments/assets/6a8dc7b0-554d-4242-acb5-823bcf0059c6" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
