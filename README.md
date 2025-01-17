# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedur
```
Step 1:
Open Quartus II and select new project and choose the file location.

Step 2:
Module Declaration. Module should have the file name.

Step 3:
Input-Output Delecaration.

Step 4:
Use assign to define the functionality of logic circuits.

Step 5:
At the end give endmodule.

Step 6:
Run the program and choose RTL viewer to get RTL realization.
```


### PROGRAM 

Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: LOKESH KUMAR P
RegisterNumber: 212222240054

### ENCODER:
```
module Encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```

### DECODER:
```
module Decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule

```
### OUTPUT:
### ENCODER:









### RTL LOGIC  

![Screenshot 2023-05-11 144551](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/9f98e2ef-bb38-4590-ae5f-e6535f5d68c0)







### TIMING DIGRAMS  

![Screenshot 2023-05-11 144605](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/86045106-af91-41b4-aca1-6b8eae5b500c)




### TRUTH TABLE
![image](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/fdba2afc-c598-4349-88fa-5e29d9bdfeca)



### DECODER:


### RTL LOGIC  

![image](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/94353dc9-3037-4806-93ee-a1510254be73)




### TIMING DIGRAMS

![image](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/9d7c074f-2d0d-4197-8d82-4643999a5de6)


### TRUTH TABLE
![image](https://github.com/LOKESHKUMARPANCHATCHARAM/Experiment-08-Encoders-and-decoders-/assets/119644432/bacd3157-4827-4e9f-b7fa-e7d02a2e8b11)


### RESULT:
Thus the program for encoder and decoder using verilog code is verified.



