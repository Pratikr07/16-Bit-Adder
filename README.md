# 16-bit Ripple Carry Adder in Verilog

This repository contains a **gate-level, hierarchical implementation of a 16-bit ripple carry adder** written in Verilog, along with a testbench and waveform output. The design is simulated using **Icarus Verilog** and verified through **GTKWave**.

---

## 📁 Repository Structure

```
.
├── fadder.v          # 1-bit Full Adder (gate-level)
├── adder4bit.v       # 4-bit Ripple Carry Adder
├── adder16bit.v      # 16-bit Ripple Carry Adder with flags
├── tb_adder16bit.v   # Testbench for 16-bit adder
├── add16.vcd         # VCD waveform file
├── wave.png          # GTKWave screenshot (simulation result)
└── README.md
```

---

## ✨ Features

* Gate-level **1-bit Full Adder** using XOR, AND, OR gates
* Hierarchical design (1-bit → 4-bit → 16-bit)
* Computes common **ALU flags**:

  * **Sign flag**
  * **Zero flag**
  * **Carry flag**
  * **Parity flag**
  * **Overflow flag**
* Tested and simulated successfully
* Waveform verified using GTKWave

---

## 🧩 Module Overview

### 1️⃣ `fadder.v`

Implements a **1-bit full adder** using basic logic gates.

**Inputs:** `a`, `b`, `c` (carry-in)
**Outputs:** `s` (sum), `cout` (carry-out)

---

### 2️⃣ `adder4bit.v`

Builds a **4-bit ripple carry adder** using four instances of the full adder.

**Inputs:** `x[3:0]`, `y[3:0]`, `cin`
**Outputs:** `s[3:0]`, `cout`

---

### 3️⃣ `adder16bit.v`

Constructs a **16-bit ripple carry adder** using four 4-bit adders and generates status flags.

**Inputs:** `x[15:0]`, `y[15:0]`
**Outputs:**

* `z[15:0]` – Sum
* `sign` – MSB of result
* `zero` – Result is zero
* `carry` – Carry out
* `parity` – Even parity of result
* `overflow` – Signed overflow detection

---

### 4️⃣ `tb_adder16bit.v`

Testbench to verify the 16-bit adder with multiple test vectors. Generates a **VCD file** for waveform analysis.

---

## ▶️ Simulation Instructions

### Requirements

* **Icarus Verilog (tested on v0.9.7)**
* **GTKWave**
* VS Code / Terminal

### Compile

```bash
iverilog -o add16 fadder.v adder4bit.v adder16bit.v tb_adder16bit.v
```

### Run Simulation

```bash
vvp add16
```

### View Waveform

```bash
gtkwave add16.vcd
```

---

## 📊 Waveform Output

The waveform screenshot included in this repository shows:

* Correct sum generation
* Proper carry propagation
* Accurate flag behavior (sign, zero, carry, parity, overflow)

---

## 📌 Notes

* Designed using **structural (gate-level) Verilog**
* Compatible with **Verilog-2005** standard
* Suitable for **digital design labs, exams, and learning purposes**

---

## 👤 Author

**Pratik Rathod**
Electronics / Digital Design Enthusiast

---

If you find this project useful, feel free to ⭐ the repository!
