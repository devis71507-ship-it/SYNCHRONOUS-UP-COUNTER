### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
1. Type the program in Quartus software.
2. Compile and run the program.
3. Generate the RTL schematic and save the logic diagram.
4. Create nodes for inputs and outputs to generate the timing diagram.
5. For different input combinations generate the timing diagram.

**PROGRAM**

```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:s.devi RegisterNumber:25004804
*/
```
**RTL LOGIC UP COUNTER**

up counter

<img width="1920" height="1080" alt="Screenshot 2025-12-15 140020" src="https://github.com/user-attachments/assets/50ad37c9-16e2-44b6-ab20-0f9b47a0d282" />

down counter

<img width="1920" height="1080" alt="Screenshot 2025-12-15 141117" src="https://github.com/user-attachments/assets/df6302a4-9335-4312-af20-613499771c35" />

**TIMING DIAGRAM FOR IP COUNTER**

up counter

<img width="1920" height="1080" alt="Screenshot 2025-12-15 135857" src="https://github.com/user-attachments/assets/c33c99e9-5e25-4c7b-a827-caa55b491bce" />

down counter

<img width="1920" height="1080" alt="Screenshot 2025-12-15 141056" src="https://github.com/user-attachments/assets/307d23d9-a926-4f48-b99e-16537bbb019b" />

**TRUTH TABLE**

![table-5-6-2](https://github.com/user-attachments/assets/79ff305f-90b1-47c9-a89c-31ff6a59271f)

**RESULTS**

Thus a 4 bit synchronous up counter and down counter is implelmented and its functionality is validated.
