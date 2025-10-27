
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
SBUF='A';
while(TI==0);
T * 1 = 0
}
}
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
DJNZ  B,AGAIN
END
```
```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="VARUN KUMAR P A";
unsigned char i;
TMOD 1 = 0 * 20 //TIMER 1, MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i = 0;i < 17;i++)
{
SBUF= msg[i];
while(TI==0);
TI = 0
}
while(1);
}
```

## OUTPUT:
### (i) Serial Port Transfer a Single Character

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/bea3e9a8-75fc-494a-9fe0-dbfac1b84e2d" />

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/22339174-f2c7-4997-8307-b109fcf6c7f3" />

### (ii) Serial Port to Transfer a Message

<img width="1918" height="706" alt="image" src="https://github.com/user-attachments/assets/e20f8689-1047-475a-a819-00574b02348a" />
  
<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/f5eb7f6c-67f5-417d-bb89-a975d4368f8e" />

## RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
