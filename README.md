# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 3 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, three-bit count:
![image](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/afc6d8dd-d43e-4605-86f9-384b956f4e9b)

Three-bit “Up” Counter



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 3-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/99d2b501-0734-4cbb-9122-a54ad754fa93)



3-bit Count Down Counter
### Procedure
Step 1:Create a new project in Quartus2 software .
Step 2:Name the project as uc for upcounter and dc for down counter.
Step 3:Create a new verilog hdl file in the project file.
Step 4:Name the module declare as dc and uc for down counter and upcounter.
Step 5:Within the module declare input and output variables.
Step 6:Create a loop using if-else with condition parameter as reset.
Step 7:End the loop.
Step 8:End the module



### PROGRAM 
```
### Up Counter:
Module upcounter(clk,a);
input clk;
output reg[3:0];
always @(posedge clk)
begin
a[2]=(a[1]&a[0])^a[2];
a[1]=(a[0]^a[1]);
a[0]= ^a[0];
end
endmodule

## Down Counter:
Module downcounter(clk,a);
input clk;
output reg[3:0]a;
always @(posedge clk)
begin
a[2]=(~a[1]&~a[0])^a[2];
a[1]=(~a[0]^a[1]);
a[0]=1^a[0];
end
endmodule
```

### RTL LOGIC UP COUNTER AND DOWN COUNTER  
## UP COUNTER 
![up rtl](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/95cdc48c-c29a-4097-9785-74bcb17e2a73)

## DOWN COUNTER 
![down rtl](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/6522a51a-d1d4-4592-ad19-217e365e3697)

### TIMING DIGRAMS FOR COUNTER  
## UP COUNTER 
![up timing](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/81054568-3bfe-4366-8c35-7d0252eea546)

## DOWN COUNTER 
![down timing](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/f88a88ae-1c60-4ebc-a52d-952b1f2ef7f2)


### TRUTH TABLE 
## UP COUNTER 
![up table](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/4121d34d-9e92-47d4-ba3b-61617b2c2a56)

## DOWN COUNTER 
![down table](https://github.com/jishnusankaran/Exp-7-Synchornous-counters-/assets/144979369/d9a93424-856a-4c52-b101-6c109fd087b7)


### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
