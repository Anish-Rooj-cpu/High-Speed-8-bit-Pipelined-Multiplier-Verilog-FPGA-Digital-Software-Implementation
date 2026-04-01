# 🚀 8-bit Pipelined Multiplier (Verilog)

A **4-stage pipelined 8×8 multiplier** implemented in **Verilog HDL**, designed for **high throughput** operation.
The design is verified in **EDA Playground** and also implemented using **Digital Software by Helmut Hneemann**.

This multiplier uses a **shift-add architecture** split across pipeline stages to reduce critical path delay and improve clock frequency.

---

# 🔗 EDA Playground

You can directly run the design online:

👉 https://edaplayground.com/x/apPL

Includes:

* Verilog design
* Testbench
* Waveform
* Valid pipeline verification

---

# ✨ Features

* ✅ 8-bit × 8-bit multiplication
* ✅ 16-bit output
* ✅ 4-stage pipeline
* ✅ Valid signal propagation
* ✅ High-throughput architecture
* ✅ Synthesizable Verilog
* ✅ FPGA friendly design
* ✅ Digital Software compatible implementation
* ✅ No `*` operator used (pure hardware multiplier)

---

# 🧠 Pipeline Architecture

| Stage   | Operation                       |
| ------- | ------------------------------- |
| Stage 1 | Input register capture          |
| Stage 2 | Partial products (lower 4 bits) |
| Stage 3 | Partial products (upper 4 bits) |
| Stage 4 | Final output register           |

Pipeline latency = **4 clock cycles**
Throughput = **1 result per clock**

---

# 📐 Block Diagram

```
operand_a ─┐
           ├── Stage1 ── Stage2 ── Stage3 ── Stage4 ── result
operand_b ─┘

valid_in ───────────────────────────────────► valid_out
```

---

# ⚙️ Interface

```verilog
module pipelined_multiplier (
    input wire clk,
    input wire reset,
    input wire [7:0] operand_a,
    input wire [7:0] operand_b,
    input wire valid_in,
    output reg [15:0] result,
    output reg valid_out
);
```

---

# ⏱ Timing

Latency: **4 clock cycles**
Throughput: **1 multiplication per clock cycle**

---

# 🧮 Algorithm

Shift-and-Add multiplication split across pipeline:

Stage 2:

```
A[0..3] × B
```

Stage 3:

```
A[4..7] × B
```

Final:

```
Sum of all partial products
```

---

# 🧪 Simulation

Verified using:

* ✅ EDA Playground
* ✅ ModelSim compatible
* ✅ Vivado compatible
* ✅ Digital (Hneemann)

Example:

```
A = 15
B = 3

Output = 45
```

Pipeline output appears after 4 cycles.

---

# 🖥 Digital Software Implementation

The multiplier was also implemented in:

**Digital Logic Simulator — Helmut Hneemann**

Includes:

* Register stages
* Adders
* Shift logic
* Pipeline registers

---

# 📁 Repository Structure

```
├── RTL/
    └── pipelined_multiplier.dig
├── testbench.v
├── digital/
│   └── pipelined_multiplier.dig
└── README.md
```

---

# 🎯 Applications

* DSP pipelines
* FIR filters
* MAC units
* FPGA accelerators
* CPU ALU design
* Digital signal processing

---

# 🔧 Future Improvements

* [ ] 16-bit version
* [ ] Booth multiplier pipeline
* [ ] Wallace tree pipeline
* [ ] Signed multiplication
* [ ] Parameterized width
* [ ] MAC unit

---

# ⭐ If you like this project

Star ⭐ the repository
Fork 🍴 and improve
Open PRs 🚀
