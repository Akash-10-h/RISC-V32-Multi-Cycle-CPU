

```markdown
# 🧠 RISC-V32 Multi-Cycle CPU

A fully functional **32-bit RISC-V processor** implemented in **Verilog HDL**, designed for simulation and FPGA deployment.  
This project follows a **multi-cycle architecture**, executing one instruction in multiple steps — balancing performance and simplicity.

---

## 🚀 Features

- 🧩 **Multi-Cycle CPU Design**
  - Separate fetch, decode, execute, memory, and write-back stages
- ⚙️ **Extended ALU Operations**
  - Supports arithmetic, logic, and shift instructions
- 💾 **Instruction Memory Loader**
  - Load `.hex` files directly for simulation or FPGA use
- ⏱️ **Clock Divider**
  - Slows down internal clock for FPGA visual demonstration
- 🔢 **BCD to 7-Segment Display**
  - Continuously displays register `x1` content in real time
- 🧮 **Modular Verilog Architecture**
  - CPU, ALU, Register File, Control Unit, Memory Interface, etc.
- 💻 **Python Assembler**
  - Converts RISC-V assembly code into machine code (`.hex`) automatically

---


```

```



```markdown
## 📂 Project Structure

```bash
RISC-V32-MultiCycle-CPU/
│
├── src/
│   ├── cpu.v
│   ├── alu.v
│   ├── control_unit.v
│   ├── reg_file.v
│   ├── memory.v
│   ├── clock_divider.v
│   ├── bcd_to_7seg.v
│   └── top_module.v
│
├── testbench/
│   ├── cpu_tb.v
│   ├── alu_tb.v
│   └── memory_tb.v
│
├── assembler/
│   └── riscv_assembler.py
│
├── examples/
│   ├── add_test.hex
│   ├── loop_test.hex
│   └── factorial.hex
│
├── docs/
│   ├── architecture_diagram.png
│   └── design_notes.pdf
│
└── README.md
```
```

---

````

---

## 🧰 Supported Instructions

| Category | Instructions | Example |
|-----------|---------------|----------|
| Arithmetic | ADD, SUB, MUL | `ADD x1, x2, x3` |
| Logic | AND, OR, XOR | `AND x4, x1, x2` |
| Shift | SLL, SRL, SRA | `SLL x5, x6, 2` |
| Comparison | SLT, SLTU | `SLT x7, x8, x9` |
| Memory | LW, SW | `LW x1, 0(x2)` |
| Branch | BEQ, BNE, BLT, BGE | `BEQ x1, x2, label` |
| Jump | JAL, JALR | `JAL x1, label` |
| Immediate | ADDI, ANDI, ORI | `ADDI x3, x4, 5` |

---

## 🔧 Simulation & FPGA Setup

### 🧪 Simulation (ModelSim / Vivado)
1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/RISC-V32-MultiCycle-CPU.git
   cd RISC-V32-MultiCycle-CPU
````

2. Open `top_module.v` as top design file.
3. Add `cpu_tb.v` as testbench.
4. Run simulation and observe register/memory activity.

### 🖥️ FPGA Deployment

1. Synthesize `top_module.v` in Vivado.
2. Connect 7-segment display for register output.
3. Load `.bit` file to your FPGA board (e.g., Basys 3 or Nexys A7).

---

## 🧮 Example

```assembly
# add_test.asm
ADDI x1, x0, 5
ADDI x2, x0, 3
ADD  x3, x1, x2
SW   x3, 0(x0)
```

→ Assemble:

```bash
python assembler/riscv_assembler.py examples/add_test.asm
```

→ Output:

```
add_test.hex generated successfully!
```

---

## 📊 Future Enhancements

* 🔄 Pipeline version (5-stage)
* 🧠 Hazard detection and forwarding
* 🕹️ Interrupt and Exception handling
* 🗃️ Cache memory support
* 🧰 GUI-based assembler frontend

---

## ⭐ Acknowledgment

Special thanks to the RISC-V community for open ISA resources and academic guides that inspired this educational implementation.

```


- Or keep it as a clean, technical README for now?
```
