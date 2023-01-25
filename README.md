 Experiment-08- Encoders-and-decoders 
AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
SOFTWARE REQUIRED:   Quartus prime
THEORY 

Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
Figure -02 3 to 8 Encoder implenentation 

 Decoders 
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
Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
Figure -04 8 to 3 Decoder implementation 

Procedure
/* write all the steps invloved */
Step-1: create module encoder and decoder.

Step-2: Get inputs and outputs for encoders and decoders.

Step-3: perform or operation for encoder and and logic for decoders.

Step-4: perform RTL LOGIC and get waveform.

Step-5: End the module



PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.

ENCODER
module EX7(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
end module

DECODER
module EX7(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c); assign d6 = (a&b&~c);
assign d7 = (a&b&c);
end module

Developed by: HARZHITA S P
RegisterNumber:  22006162

RIT LOGIC

ENCODER

![Screenshot (26)](https://user-images.githubusercontent.com/123094490/214579899-6d823376-8e01-4049-8999-1395d999e0c3.png)


DECODER

![Screenshot (27)](https://user-images.githubusercontent.com/123094490/214579527-c4dce177-7893-456c-8128-b6b9d983f8d8.png)


TIMING DIGRAMS  


ENCODER


![Screenshot (28)](https://user-images.githubusercontent.com/123094490/214584781-05e1c3e8-8bde-46e2-8c8e-279c014fdcc9.png)

DECODER

![Screenshot (29)](https://user-images.githubusercontent.com/123094490/214584912-b97415d5-15dc-448c-b0e1-92a4dead2512.png)


TRUTH TABLE 
ENCODER

![Screenshot (30)](https://user-images.githubusercontent.com/123094490/214585809-26e1ac51-eb86-4757-8993-e6bab6cbd12f.png)



DECODER

![Screenshot (31)](https://user-images.githubusercontent.com/123094490/214585561-9ca07e22-fd15-4bf4-9091-6efabb3de9f6.png)


RESULTS 
Thus the program to desing encoder and decoder is completed.
