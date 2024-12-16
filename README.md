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

/* write all the steps invloved */

**PROGRAM**

```
module up_c (
    input clk,        
    input rst,       
    output reg [3:0] count  
);

   
    always @(posedge clk or posedge rst) begin
        if (rst) begin
            
            count <= 4'b0000;
        end else begin
            
            count <= count + 1;
        end
    end

endmodule

```




Developed by:Rohith V ,RegisterNumber:24900447


**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-16 202240](https://github.com/user-attachments/assets/1fdf8861-dc8e-4ae0-ad11-67a159bdcc6a)


**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot (66)](https://github.com/user-attachments/assets/b901d44b-cd72-49a7-bf87-2ed1dc3a0bb6)


**TRUTH TABLE**

![Screenshot 2024-12-16 203012](https://github.com/user-attachments/assets/c5c7c4e8-a87f-4cb9-994b-d05b83999b0d)


**RESULTS**
implementation of 4 bit synchronous up counter and validate functionality.

