# CSCI2461_Project3


ALU: Use currentALU, it is the most recent update



Control Flow - What write signals do we need:

Once we find what select lines we absolutely need, we can 
Designate them bits 0-7 for each 8 bit space in Rom to control
The flow of the processor. There might be extra needed, but I
Think right now we need less than 8, but we can work with some 
Logic gates and finishing this later today.


Registers:
Decoder Write enable R0-R3
0 = disabled
1 = enabled

ALU:
Select Add/And
0 = ADD
1 = AND

Maybe don’t need:
Write enable for ALU decoder, should be able to always be on


Control Unit:
RAM - Write Enable
RAM - Output Enable
Maybe combine into one select line with inverter?
0 = Output enabled, write disabled
1 = write enabled, output disabled


ROM - Output Enable? Does this ever need to be disabled?

PC - Clock/load selector
By turning off pc’s clock pin, and turning the load selector on, you increment the pc once during a cycle
0 = Clock on / Load off
1 = Clock off / Load on


MAR - Load selector
Can’t be load enabled when pc is incrementing
0 = Load enabled
1 = load disabled


Maybe don’t need (combine with other selector or just don’t need it):
MDR - Load selector
IR - load selector
