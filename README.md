# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![Screenshot 2024-12-13 230246](https://github.com/user-attachments/assets/abc81fac-ccfd-476a-990d-db1fb96cc435)



This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![Screenshot 2024-12-13 230257](https://github.com/user-attachments/assets/4e8b96c9-afc3-40a1-95d2-de22d0353508)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![Screenshot 2024-12-13 230307](https://github.com/user-attachments/assets/874975ae-0f4e-4986-8109-197a59938a0b)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![Screenshot 2024-12-13 230317](https://github.com/user-attachments/assets/0aa05353-aeef-4653-ad4a-dd31e5b18832)


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
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
/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: KABILAN P RegisterNumber: 24900859
*/

**RTL LOGIC FOR FLIPFLOPS**
![Screenshot 2024-12-13 230328](https://github.com/user-attachments/assets/bc0309e5-f685-436e-b68b-418f4f6c8fdb)


**TIMING DIGRAMS FOR FLIP FLOPS**

![Screenshot 2024-12-13 230339](https://github.com/user-attachments/assets/03718ca7-c3bb-4d3b-8df2-ecc988a7ebf3)

**RESULTS**
Thus the flips flop designed and the truth tables is verified using quartus software.
