# NAME:PRADEEP V
# REG NO:212223240119
# EX-07 JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */
/* Define Module: Define a Verilog module for the JK flip-flop with inputs (J, K, CLK) and outputs (Q, Q_bar).

Declare Inputs and Outputs: Declare input and output ports for the module.

Implement Flip-Flop Logic: Write Verilog code to implement the JK flip-flop logic based on its functional table. Use a synchronous always @(posedge CLK) block to trigger the flip-flop on the positive edge of the clock signal.

Simulate Using Testbench: Write a Verilog testbench to simulate the behavior of the JK flip-flop under different input conditions.

Apply Input Stimuli: In the testbench, apply various combinations of input stimuli (J, K, CLK) to cover all possible input states.

Verify Output Behavior: Verify that the output behavior of the JK flip-flop matches the expected behavior defined by its functional table.

Check for Race Conditions: Ensure that there are no race conditions or undefined states in the design by analyzing the timing and sequence of input changes.
*/

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by:PRADEEP V
RegisterNumber:212223240119*/

```

module JKFLIPFLOP(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
   begin
	   if(j==0 && k==0)
		   begin
			q<=q;
			qb<=qb;
			end
		else if(j!=k)
		   begin
			q<=j;
			qb<=k;
			end
		else if(j==1 && k==1)
		    begin
			 q<=~q;
			 qb<=~qb;
			 end
	end
end	
endmodule


```

**RTL LOGIC FOR FLIPFLOPS**
![323293082-48cc0eb5-e90d-45bd-bb4e-000dcf05a796](https://github.com/velupradeep/JKFLIPFLOP-USING-IF-ELSE/assets/150329341/30425e99-6e9e-4142-9c6e-05338411e6cd)




**TIMING DIGRAMS FOR FLIP FLOPS**

![323293154-d4b06ea5-ea16-4979-8e0c-56e0bf0706b1](https://github.com/velupradeep/JKFLIPFLOP-USING-IF-ELSE/assets/150329341/8bec6ab3-072d-45f9-a245-d3e44dcc39db)


**RESULTS**

Thus a program to implement a JK flipflop using verilog and validating their functionality using their functional tables is successfully completed.
