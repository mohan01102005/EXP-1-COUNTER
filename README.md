

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

### **OUTPUT**

The counter design was successfully simulated.
The waveforms of **clk**, **rst**, **m (mode)**, and **count\[3:0]** were obtained as shown below.

**Simulation Results (Screenshots):**

📌 Attached Screenshots (from MobaXterm & SimVision):

* [Screenshot 1](sandbox:/mnt/data/Screenshot%202025-09-04%20084525.png)
* [Screenshot 2](sandbox:/mnt/data/Screenshot%202025-09-04%20084734.png)
* [Screenshot 3](sandbox:/mnt/data/Screenshot%202025-09-04%20084844.png)
* [Screenshot 4](sandbox:/mnt/data/Screenshot%202025-09-04%20085050.png)
* [Screenshot 5](sandbox:/mnt/data/Screenshot%202025-09-04%20085121.png)
* [Screenshot 6](sandbox:/mnt/data/Screenshot%202025-09-04%20085856.png)
* [Screenshot 7](sandbox:/mnt/data/Screenshot%202025-09-04%20085907.png)
* [Screenshot 8](sandbox:/mnt/data/Screenshot%202025-09-04%20091148.png)

---

### **RESULT**

The counter was successfully designed and simulated using Verilog HDL in Cadence (via MobaXterm). The waveform confirms the correct working of the **Up/Down counter** with reset and mode control.

---

👉 Do you want me to make this into a **Word file with all screenshots inserted properly** (like a lab record submission), or just keep it as text format?
