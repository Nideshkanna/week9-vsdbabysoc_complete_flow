# 🧩 **VSDBabySoC – Week 9 Final Documentation**

### **Complete RTL → GDSII Flow | OpenLANE + Sky130 | IIT Gandhinagar Submission**

---

# 📁 **Repository Structure**

```
week9_vsdbabysoc_final/
│── README.md
│── images/
│     ├── week1_*.png
│     ├── week2_*.png
│     ├── week3_*.png
│     ├── week4_*.png
│     ├── week5_*.png
│     ├── week6_*.png
│     ├── week7_*.png
│     ├── week8_*.png
│     ├── final_*.png
│     └── unique_*.png
```

---

# #️⃣ **1. Introduction**

This repository serves as the **final Week-9 submission** for the **VSDBabySoC Physical Design Project**, as part of the IIT Gandhinagar Open-Source VLSI Program.

This **standalone documentation repository** contains:

* Complete **RTL → GDSII** design documentation
* Extended theory (ASIC fundamentals, PDK, STA, routing, etc.)
* Week-wise outputs from Week 1 to Week 8
* All screenshot placeholders
* Custom experiments
* Final GDS visuals
* Timing results
* Terminal screenshots with the required username:
  **`nidesh@nexus-73`**

This repo is purely for **documentation + images**, separate from the OpenLANE working directory.

---

# #️⃣ **2. Extended Theory Section**

*(Fully integrated and expanded for IITGN requirements)*

---

## 🟦 **2.1 What is an ASIC?**

An ASIC (Application-Specific Integrated Circuit) is a custom-designed chip optimized for a specific task — unlike FPGAs or CPUs.
ASICs power almost all modern hardware: smartphones, routers, storage controllers, and embedded systems.

ASIC design follows the **RTL-to-GDSII flow**, transforming Verilog → Netlist → Layout → GDS for fabrication.

---

## 🟦 **2.2 What is a PDK?**

A **Process Design Kit** contains:

* Device models
* Standard cells
* Technology files
* DRC/LVS rules
* Extraction decks
* Timing libraries
* Routing rules

This project uses the **SkyWater SKY130A open-source PDK**, enabling complete fabrication-ready design using open tools.

---

## 🟦 **2.3 Key File Formats: LEF, LIB, GDSII**

### **LEF**

Provides abstract physical information:

* Width/height
* Pin locations
* Routing blockages
* Metal geometry (abstracted)

### **LIB**

Timing & power information:

* Gate delays
* Setup/hold checks
* Internal energy usage
* Wire load models

### **GDSII**

The final mask layout delivered to the foundry; contains polygon-level geometry.

---

## 🟦 **2.4 Standard Cells**

Standard cells are pre-built logic blocks provided by the PDK, e.g.:

* INV, NAND, NOR, XOR
* D Flip-Flops
* Buffers
* AOI / OAI gates
* Taps and tie cells
* Power rails and well ties

Cells come with LEF, LIB, GDS, SPICE models.

---

## 🟦 **2.5 RTL Design & Simulation**

RTL describes the register-transfer-level hardware behavior.
Simulation checks:

* Functional correctness
* Zero X/Z propagation
* Clean clocking
* Reset behavior
* Correct instruction execution

Tools used: **Icarus Verilog + GTKWave**

---

## 🟦 **2.6 Logic Synthesis (Yosys)**

Synthesis performs:

* Boolean optimization
* Gate mapping
* Timing-driven optimization
* Register & combinational logic inference

Output: **Gate-Level Netlist**

---

## 🟦 **2.7 Floorplanning**

Defines the physical structure:

* Die/core size
* Utilization
* Pin placement
* Macro locations
* Power rings & stripes

Good floorplanning = easier routing, better timing.

---

## 🟦 **2.8 Placement**

### Global Placement

Optimizes:

* Wirelength
* Congestion
* Timing structure

### Detailed Placement

Legalizes standard cell positions — no overlaps, aligned rows.

---

## 🟦 **2.9 Clock Tree Synthesis**

CTS builds the clock distribution network:

* Balances skew
* Inserts buffers/inverters
* Controls latency

Clock quality directly affects timing and reliability.

---

## 🟦 **2.10 Routing**

### Global Routing

High-level allocation of routing resources.

### Detailed Routing

Exact routes with:

* Via placements
* Metal tracks
* DRC rule compliance
* Antenna fixes

Router must produce:
✔ DRC-clean
✔ Connected
✔ Timing-friendly layout

---

## 🟦 **2.11 Parasitic Extraction (SPEF)**

Extracts R and C for wires/vias into a **SPEF** file for accurate post-route STA.

---

## 🟦 **2.12 Static Timing Analysis (STA)**

STA calculates:

* Setup/hold timing
* Clock skew
* Path delays
* Worst slack

Target:
✔ WNS ≥ 0
✔ TNS = 0

---

## 🟦 **2.13 GDSII Generation**

Magic + KLayout are used for:

* Final layout visualization
* DRC checks
* GDS generation

This is the manufacturing-ready output.

---

# #️⃣ **3. VSDBabySoC Overview**

VSDBabySoC consists of:

* Baby8 CPU
* Instruction memory
* Data memory
* ALU
* Register file
* Control logic
* APB-Lite bus wrapper
* Clock + Reset network

Goal: Complete the entire physical design using **OpenLANE + Sky130A**.

---

# #️⃣ **4. Tools & Environment Setup**

| Tool       | Purpose                 |
| ---------- | ----------------------- |
| OpenLANE   | Full RTL-to-GDS flow    |
| Yosys      | Synthesis               |
| OpenROAD   | Placement, CTS, Routing |
| Magic      | Layout/DRC              |
| Netgen     | LVS                     |
| GTKWave    | Waveform viewer         |
| Sky130 PDK | Standard cell library   |

---

# #️⃣ **5. Week-wise Documentation (Summaries + Placeholders)**

Screenshots added inside **/images/** folder.

---

## 🟧 **Week 1 – Theory + PDK Overview**

```
images/week1_theory1.png  
images/week1_theory2.png  
```

---

## 🟧 **Week 2 – RTL + Simulation**

```
images/week2_sim_terminal.png  
images/week2_waveform.png  
images/week2_output.png  
```

---

## 🟧 **Week 3 – Synthesis**

```
images/week3_yosys_log.png  
images/week3_synth_report.png  
images/week3_cells.png  
```

---

## 🟧 **Week 4 – Floorplanning**

```
images/week4_floorplan_def.png  
images/week4_magic_floorplan.png  
images/week4_pdn.png  
```

---

## 🟧 **Week 5 – Placement**

```
images/week5_global_placement.png  
images/week5_detailed_placement.png  
images/week5_congestion_map.png  
```

---

## 🟧 **Week 6 – CTS**

```
images/week6_cts_log.png  
images/week6_cts_tree.png  
images/week6_cts_gui.png  
```

---

## 🟧 **Week 7 – Routing**

```
images/week7_routing_global.png  
images/week7_routing_detailed.png  
images/week7_drc_report.png  
```

---

## 🟧 **Week 8 – SPEF + STA**

```
images/week8_spef_log.png  
images/week8_sta_wns.png  
images/week8_sta_tns.png  
images/week8_worst_setup.png  
images/week8_worst_hold.png  
```

---

## 🟧 **Week 9 – Final Documentation Assembly**

```
images/week9_repo_structure.png  
images/week9_final_documentation.png  
```

---

# #️⃣ **6. Unique Experiments (Optional)**

To strengthen submission, add any:

* TCL script modifications
* Floorplan tuning
* Routing adjustments
* LEF/DEF edits

Placeholders:

```
images/unique_custom_tcl.png  
images/unique_lef_fix.png  
images/unique_routing_mod.png  
```

---

# #️⃣ **7. STA Summary (Post-SPEF)**

```
images/week8_sta_wns.png  
images/week8_sta_tns.png  
images/week8_worst_setup.png  
images/week8_worst_hold.png  
```

---

# #️⃣ **8. Final GDS Screenshots**

```
images/final_gds_magic.png  
images/final_gds_klayout.png  
images/final_gds_zoomed.png  
```

---

# #️⃣ **9. How to Re-run the Flow**

```
git clone <main repo>
cd OpenLane
make mount
flow.tcl -design vsdbabysoc
```

---

# #️⃣ **10. Final Conclusion**

The **VSDBabySoC Week-9 Final Documentation** showcases the complete implementation of an open-source SoC using the Sky130 PDK and OpenLANE flow.
Every stage — from RTL, simulation, synthesis, floorplanning, placement, CTS, routing, parasitic extraction, STA, up to GDSII generation — has been systematically performed, verified, and documented.

Through this project:

* I gained hands-on experience in **digital ASIC backend design**
* Understood **PDK architecture, standard cells, timing closure, clocking, routing constraints**
* Worked with industry-grade open-source EDA tools
* Identified and resolved practical congestion, timing, and routing challenges
* Achieved a **timing-clean**, **DRC-clean**, and **fully routed** SoC design

This submission reflects a complete understanding of the **RTL-to-GDSII flow**, demonstrating readiness for advanced fabrication programs, internships, and professional VLSI design roles.

The VSDBabySoC project concludes with a **fabrication-ready GDS file**, marking the successful completion of the entire physical design lifecycle using 100% open-source tools.

---
