# T_FLIPFLOP
AIM:

To implement T flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

T Flip-Flop

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

<img width="438" height="287" alt="image" src="https://github.com/user-attachments/assets/363eb608-3172-4c52-b3dc-443855499d85" />

This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

<img width="338" height="255" alt="image" src="https://github.com/user-attachments/assets/8364172b-4923-4192-a91b-22784d33ce82" />

From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

#Procedure

Procedure to design T Flip-Flop (5 lines):

Identify the input T (Toggle), Clock, and outputs Q, Q̅.

Start from a JK flip-flop and connect J = K = T.

Define the truth table showing no change when T = 0 and toggle when T = 1.

Ensure the output changes only on the active edge of the clock.

Verify the toggle operation for successive clock pulses using simulation.

#PROGRAM
```
// T Flip-Flop (with async reset)
module t_ff (
    input  wire clk, rst, T,
    output reg Q 	  
);

  initial begin
     Q<=1'b0;
	 end
  
  
	 always @(posedge clk or posedge rst) begin
	
        if (rst)
            Q <= 1'b0;       // Reset
        else if (T)
            Q <= ~Q;         // Toggle if T=1
        else
            Q <= Q;          // Hold if T=0
    end
endmodule
```


Developed by: VANATHI T
RegisterNumber: 25013590

RTL LOGIC FOR FLIPFLOPS:
<img width="1920" height="1020" alt="Screenshot 2025-12-15 191939" src="https://github.com/user-attachments/assets/2b327ac2-69d5-4df6-9212-fdcbe7455fc9" />


TIMING DIGRAMS FOR FLIP FLOPS

RESULT:
 Implemented T flipflop using verilog and validating their functionality using their functional tables
