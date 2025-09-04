

# **Experiment: Counter Simulation using Cadence Tool (MobaXterm)**

### **AIM**

To design, simulate, and verify the functionality of a counter (Up/Down counter) using Verilog HDL in the Cadence tool suite (accessed via MobaXterm).

---

### **APPARATUS REQUIRED**

1. Personal Computer with Linux Environment / Windows (MobaXterm installed)
2. Cadence NCLaunch & SimVision tool suite
3. Verilog HDL source code files (`counter.v`, `counter_tb.v`)
4. Internet/Network access for remote server (if applicable)

---

### **PROCEDURE / STEPS**

1. Open **MobaXterm** and connect to the remote server using SSH.
2. Source the Cadence tool setup file using:

   ```
   source /cadence/install/cshrc
   ```
3. Launch NCLaunch GUI using the command:

   ```
   nclaunch -new
   ```
4. Import the Verilog source files (`counter.v`, `counter_tb.v`) into NCLaunch.
5. Compile the design and testbench files using NCLaunch (ncvlog).
6. Create the working library (`worklib`) and map the design.
7. Elaborate the design using **ncelab**.
8. Simulate the counter design with **ncsim**.
9. Open **SimVision** to visualize the waveform output.
10. Add signals (`clk`, `rst`, `count[3:0]`, etc.) to the waveform window.
11. Run the simulation and observe the counter operation.
12. Verify that the counter increments/decrements according to the design.

---
### **CODE**
`timescale 1ns / 1 ns
module counter(clk,m,rst,count);
input clk,m,rst;
output reg [3:0] count;
always@(posedge clk or negedge rst)
begin
if (!rst)
count=0;
else if(m)
count=count+1;
else
count=count-1;
end
endmodule
TEST BENCH
`timescale 1ns / 1ns
module counter_test;
reg clk,rst,m;
wire [3:0] count;
initial
begin 
clk=0;
rst=0;#5;
rst=1;
end
initial
begin
m=1;
#160 m=0;
end
counter counter1 (clk,m,rst, count);
always #5 clk=~clk;
initial $monitor("Time=%t rst=%b clk=%b count=%b" , $time,rst,clk,count);
initial
#320 $finish;
endmodule



### **OUTPUT**

The counter design was successfully simulated.
The waveforms of **clk**, **rst**, **m (mode)**, and **count\[3:0]** were obtained as shown below.

**Simulation Results (Screenshots):**

📌 Attached Screenshots (from MobaXterm & SimVision):

* [Screenshot 1]<img width="1920" height="1080" alt="Screenshot 2025-09-04 084525" src="https://github.com/user-attachments/assets/e13579ac-4676-4972-9ae1-b1b5d05af07b" />

* [Screenshot 2]<img width="1920" height="1080" alt="Screenshot 2025-09-04 084844" src="https://github.com/user-attachments/assets/98bd9ee6-49ec-44b7-9157-b94cf4fb6c03" />

* [Screenshot 3]<img width="1920" height="1080" alt="Screenshot 2025-09-04 085121" src="https://github.com/user-attachments/assets/878f8bac-96c5-4788-9539-3b785b6876d9" />

* [Screenshot 4]<img width="1920" height="1080" alt="Screenshot 2025-09-04 085826" src="https://github.com/user-attachments/assets/9c88fc35-80c5-424a-8bfa-b36e07e5e02f" />

* [Screenshot 5]<img width="1920" height="1080" alt="Screenshot 2025-09-04 085856" src="https://github.com/user-attachments/assets/48cf832c-9e72-4844-9076-ff6dcdedebe3" />

* [Screenshot 6]<img width="1920" height="1080" alt="Screenshot 2025-09-04 085907" src="https://github.com/user-attachments/assets/aa04f416-8011-48d0-9f85-1f888f55fd7a" />

* [Screenshot 7]<img width="1920" height="1080" alt="Screenshot 2025-09-04 091148" src="https://github.com/user-attachments/assets/b550d924-33b2-4b0b-8872-3770fec02304" />

---

### **RESULT**

The counter was successfully designed and simulated using Verilog HDL in Cadence (via MobaXterm). The waveform confirms the correct working of the **Up/Down counter** with reset and mode control.

---

