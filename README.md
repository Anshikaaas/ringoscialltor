3-Phase Ring Oscillator Physical Design and Verification Flow
This README describes the process followed for the design, physical implementation, and full sign-off flow of a 3-phase ring oscillator, highlighting practical skills in digital and analog IC design, verification, and signoff using industry-standard tools.

Overview
Design: 3-phase ring oscillator (RTL to GDSII)

Simulators: Spectre for analog and post-layout simulation

LVS/DRC: Quantus for signoff verification

Post-Layout Simulation: Assura

1. RTL to Netlist
Write RTL code for the ring oscillator using Verilog.

Functional verification using simulation tools to ensure correct oscillation and phase lock.

Synthesize RTL into a gate-level netlist targeting the process library.

2. Floorplanning & Power Planning
Load netlist into P&R tool.

Define die/core size, IO pad ring, and keep-out regions.

Implement power and ground grid for core and IOs.

3. Placement & Clock Distribution
Place standard cells, optimize for minimal wire length and legal layout.

Perform clock tree synthesis for consistent phase delivery.

Run static timing analysis to close all timing paths.

4. Routing
Route the design automatically with global/detailed routers.

Ensure DRC-compliant wire widths, spacing, and minimal crosstalk.

Insert necessary vias for multi-level routing.

5. Physical Verification: DRC & LVS (Quantus)
DRC: Run Design Rule Check (DRC) using Quantus to ensure the layout meets all foundry rules.

LVS: Use Quantus for Layout Versus Schematic checks, confirming the layout matches the schematic/netlist.

Review and resolve any violations.

Rerun DRC and LVS until the design is clean.

6. Extraction & Parasitic-Aware Simulation
Extract layout parasitics (RC extraction) using Quantus.

Generate SPICE netlist including extracted parasitics for full-chip post-layout simulation.

7. Post-Layout Simulation (Spectre & Assura)
Import extracted netlist into Spectre for accurate analog simulation, measuring oscillation frequency, amplitude, startup time, and phase noise.

Perform additional post-layout simulation using Assura to validate dynamic performance with extracted parasitics.

Adjust design if needed and iterate.

8. GDSII Generation
Once layout is verified (DRC/LVS clean, post-layout specs met), generate GDSII for tapeout using the P&R tool

<img width="594" height="298" alt="image" src="https://github.com/user-attachments/assets/4c72bfed-5917-456e-b518-a358fb64179a" />
Key Skills Demonstrated
RTL and analog design methodology for ring oscillators

Experience with Spectre for schematic and post-layout analog simulation

Physical verification expertise: Quantus for DRC and LVS

Extraction and signoff validation with industry tools

Assura for extracting layout parasitics and running post-layout simulations

Full-flow tapeout preparation and deliverable generation
