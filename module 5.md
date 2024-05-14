  
Verilog is a hardware description language (HDL) used to model electronic systems. It is widely used in the design and verification of digital circuits and systems, particularly in the field of integrated circuit (IC) and field-programmable gate array (FPGA) design.

synthesizable module describes the hardware 
test bench checks weather the output is correct or not 

Types of modelling 

Abstraction level approach 
top down approach upar sa niche
Bottom up approach 

top down eg
ripple counter -> t flip flop -> d flip flop + inverter gate 


**behavioural or algo level**
highest level of abstraction provide by the verilog hdl
we are focused about fucntionality not concerned about circuit design 
it is similar to c,c++ but it very difficult to synthesize 

**Dataflow level**
module is designed by specifying data flow 
how data flow between hardware resistors and the data is processed in the design 
it is easly translated can be implemented easily 

Gate level modelling 
the module is implemented in terms of logic gate and interconnection between the gates 
it resembles schematic drawing 
change in value of physical signal activates the components 
it is more closer to physical implementation but 






1. Write a verilog code to implement full adder using hierarchical model.

module full_adder_join(fsum, fcarry_out, a, b, c);
    input a, b, c;
    output fsum, fcarry_out;
    wire half_sum_1, half_carry_1, half_carry_2;
    
    // Instantiate half adders
    half_adder HA1(half_sum_1, half_carry_1, a, b); // Instance 1 of Half Adder
    half_adder HA2(fsum, half_carry_2, half_sum_1, c); // Instance 2 of Half Adder
    
    // Implement OR gate to generate final carry out
    assign fcarry_out = half_carry_1 | half_carry_2;
endmodule



First page 

Hardware Description Language (HDL) is like the blueprint for digital systems but in a language computers can understand. It's a textual representation of how hardware components like circuits and chips work together. With HDL, you can design hardware at different levels, from basic components like logic gates to complex systems like processors.

One of the biggest advantages of HDL is simulation. Before actually making the hardware, you can simulate its behavior on a computer. This helps catch errors and make improvements without the cost and time of physically building prototypes.

The rise of Very Large Scale Integration (VLSI), where millions of tiny components are packed onto a single chip, made traditional methods of hardware design and testing impractical. It's just not feasible to verify a complex design with millions of gates by physically wiring them together on a breadboard. HDLs solve this problem by providing a way to verify the functionality of these intricate circuits through simulation, ensuring they work as intended before they're fabricated.


Second Page 

Verilog and VHDL are both Hardware Description Languages (HDLs) used for describing the behavior and structure of digital systems. They serve similar purposes but have some differences in their syntax, usage, and popularity in different regions and industries.

**Verilog:**
- **Usage:** Verilog HDL is widely used in the US industry, particularly by major digital design companies.
- **Applications:** It is primarily used in the design, verification, and implementation of digital logic chips.
- **Popularity:** Verilog is commonly chosen as the primary HDL for many companies due to its widespread adoption and extensive support within the industry.

**VHDL (VHSIC Hardware Description Language):**
- **Usage:** VHDL is more popular in Europe, although it is also used in other regions.
- **Applications:** It is commonly employed as a design-entry language for Field-Programmable Gate Arrays (FPGAs). FPGAs are a type of logic chip that can be programmed to perform various tasks.
- **Popularity:** VHDL is favored for its versatility and comprehensive features, making it well-suited for complex FPGA designs and other applications.

In summary, while both Verilog and VHDL are used for hardware description, their popularity and preferred applications may vary by region and industry. Verilog is prominent in the US and is commonly used for digital logic chip design, while VHDL is more popular in Europe and often used for FPGA design and other applications.