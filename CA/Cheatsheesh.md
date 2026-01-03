## **Chapter 2: Array-Related Exercises**
**Focus:** Translating C array logic into MIPS assembly.
**Master Rule:** Arrays use **Byte Addressing**. You *must* multiply integer indices by 4 (`sll $reg, 2`) before adding to the Base Address.

### **1. Basic Array Access (Exercise 2.3)**
**Task:** `B[8] = A[i - j];`
* **Registers:** `i`=`$s3`, `j`=`$s4`, Base A=`$s6`, Base B=`$s7`.

**Step-by-Step Derivation:**
1.  **Calculate Index:** Compute the integer index `i - j`.
2.  **Convert to Offset:** Multiply that index by 4 (shift left 2) to get bytes.
3.  **Calculate Address:** Add the Base Address of A to the Offset.
4.  **Load Data:** Fetch the value from memory.
5.  **Store Data:** Save to B[8] (Offset = $8 \times 4 = 32$).

**MIPS Code:**
```mips
sub  $s3, $s3, $s4      # Step 1: i - j
sll  $t1, $s3, 2        # Step 2: Offset = (i - j) * 4
add  $t1, $t1, $s6      # Step 3: Address = Base A + Offset
lw   $t0, 0($t1)        # Step 4: Load A[i-j]
sw   $t0, 32($s7)       # Step 5: Store to B[8] (Offset 32)
````

### **2. Computed Indices (Exercise 2.4)**

**Task:** `B[g] = A[f] + A[f + 1];`

- **Registers:** `f`=`$s0`, `g`=`$s1`, Base A=`$s6`, Base B=$s7.

**Step-by-Step Derivation:**

1. **Address `A[f]`:** Shift `f` left 2, add to Base A.
2. **Address `B[g]`:** Shift `g` left 2, add to Base B.
3. **Load `A[f]`:** Load word from the address calculated in Step 1.
4. **Load `A[f+1]`:** Add 4 bytes to A[f]'s address (next word), then load.
5. **Compute Sum:** Add the two loaded values.
6. **Store:** Save result to address B[g].

**MIPS Code:**

MIPS Assembler

```
sll  $t0, $s0, 2        # Step 1a: f * 4
add  $t0, $s6, $t0      # Step 1b: Address of A[f]
sll  $t1, $s1, 2        # Step 2a: g * 4
add  $t1, $s7, $t1      # Step 2b: Address of B[g]
lw   $s0, 0($t0)        # Step 3: Load A[f]
addi $t2, $t0, 4        # Step 4a: Address of A[f+1] is A[f] + 4
lw   $t0, 0($t2)        # Step 4b: Load A[f+1]
add  $t0, $t0, $s0      # Step 5: Result = A[f] + A[f+1]
sw   $t0, 0($t1)        # Step 6: Store result in B[g]
```

### **3. Sorting Logic (Exercise 2.6)**

**Task:** `if (A[i] > A[j]) swap(A[i], A[j]);`

**Step-by-Step Derivation:**

1. **Load:** Get values from memory for `A[i]` and `A[j]`.
    
2. **Compare:** Use `slt` (Set Less Than). Check if `A[j] < A[i]`.
    
3. **Branch:** If `A[j] >= A[i]` (meaning order is correct or equal), skip the swap.
    
4. **Swap:** If we didn't branch, store `A[j]`'s value into `A[i]`'s slot, and vice-versa.

**MIPS Code:**

MIPS Assembler

```
# Assumes $s2 points to A[i], $t2 points to A[j]
lw   $s3, 0($s2)        # Step 1: Load A[i]
lw   $t3, 0($t2)        # Step 1: Load A[j]
slt  $t4, $t3, $s3      # Step 2: $t4 = 1 if A[j] < A[i]
beq  $t4, $zero, L2     # Step 3: If order correct, skip
sw   $t3, 0($s2)        # Step 4: Store old A[j] into A[i] location
sw   $s3, 0($t2)        # Step 4: Store old A[i] into A[j] location
L2:
```

---

## **Chapter 3: Arithmetic Algorithms**

### **Part A: Multiplication**

Constraint: 4-bit numbers.

Stop Rule: Stop exactly after Iteration 4 (Matches bit count).

**Step-by-Step Procedure (Per Iteration):**

1. **Check LSB:** Look at the rightmost bit of the **Multiplier**.
    
    - If **1**: Add _Multiplicand_ to _Product_.
        
    - If **0**: Do nothing (No Op).
        
2. **Shift Left:** Shift the **Multiplicand** register 1 bit left.
    
3. **Shift Right:** Shift the **Multiplier** register 1 bit right.
    

Table: $2 \times 3$ ($0010 \times 0011$)

| Iteration | Step | Multiplier | Multiplicand | Product |
| :--- | :--- | :--- | :--- | :--- |
| 0 | Initial values | 0011 | 0000 0010 | 0000 0000 |
| 1 | 1a: 1 $\Rightarrow$ Prod + Mcand | 0011 | 0000 0010 | 0000 0010 |
| | 2: Shift left Mcand | 0011 | 0000 0100 | 0000 0010 |
| | 3: Shift right Mplier | 0001 | 0000 0100 | 0000 0010 |
| 2 | 1a: 1 $\Rightarrow$ Prod + Mcand | 0001 | 0000 0100 | 0000 0110 |
| | 2: Shift left Mcand | 0001 | 0000 1000 | 0000 0110 |
| | 3: Shift right Mplier | 0000 | 0000 1000 | 0000 0110 |
| 3 | 1: 0 $\Rightarrow$ No operation | 0000 | 0000 1000 | 0000 0110 |
| | 2: Shift left Mcand | 0000 | 0001 0000 | 0000 0110 |
| | 3: Shift right Mplier | 0000 | 0001 0000 | 0000 0110 |
| 4 | 1: 0 $\Rightarrow$ No operation | 0000 | 0001 0000 | 0000 0110 |
| | 2: Shift left Mcand | 0000 | 0010 0000 | 0000 0110 |
| | 3: Shift right Mplier | 0000 | 0010 0000 | 0000 0110 |

### **Part B: Division**

Constraint: 4-bit numbers.

Stop Rule: Stop exactly after Iteration 5 (Bit count + 1).

**Step-by-Step Procedure (Per Iteration):**

1. **Subtract:** Calculate `Remainder = Remainder - Divisor`.
    
2. **Test Sign:** Look at the Leftmost Bit (MSB) of the result.
    - **If 1 (-ve):** Failure.
        - **Action A:** Restore (Add Divisor back to Remainder).
        - **Action B:** Shift Quotient Left, set new bit to **0**.
    - **If 0 (+ve):** Success.
        - **Action:** Keep new Remainder. Shift Quotient Left, set new bit to **1**.
3. **Shift Divisor:** Shift the **Divisor** register 1 bit right.

Table: $7 / 2$ ($0111 / 0010$)

| Iteration | Step | Quotient | Divisor | Remainder |
| :--- | :--- | :--- | :--- | :--- |
| 0 | Initial values | 0000 | 0010 0000 | 0000 0111 |
| 1 | 1: Rem = Rem - Div | 0000 | 0010 0000 | 1110 0111 (-ve) |
| | 2b: Restore, Q<<1, Q0=0 | 0000 | 0010 0000 | 0000 0111 |
| | 3: Shift Div right | 0000 | 0001 0000 | 0000 0111 |
| 2 | 1: Rem = Rem - Div | 0000 | 0001 0000 | 1111 0111 (-ve) |
| | 2b: Restore, Q<<1, Q0=0 | 0000 | 0001 0000 | 0000 0111 |
| | 3: Shift Div right | 0000 | 0000 1000 | 0000 0111 |
| 3 | 1: Rem = Rem - Div | 0000 | 0000 1000 | 1111 1111 (-ve) |
| | 2b: Restore, Q<<1, Q0=0 | 0000 | 0000 1000 | 0000 0111 |
| | 3: Shift Div right | 0000 | 0000 0100 | 0000 0111 |
| 4 | 1: Rem = Rem - Div | 0000 | 0000 0100 | 0000 0011 (+ve) |
| | 2a: Keep, Q<<1, Q0=1 | 0001 | 0000 0100 | 0000 0011 |
| | 3: Shift Div right | 0001 | 0000 0010 | 0000 0011 |
| 5 | 1: Rem = Rem - Div | 0001 | 0000 0010 | 0000 0001 (+ve) |
| | 2a: Keep, Q<<1, Q0=1 | 0011 | 0000 0010 | 0000 0001 |
| | 3: Shift Div right | 0011 | 0000 0001 | 0000 0001 |

### **Part C: Float Representation**

**Example:** Convert **-0.75** to IEEE 754.

**Step-by-Step Procedure:**

1. **Determine Sign (S):**
    - Negative number $\rightarrow$ **S = 1**.
2. **Convert to Binary:**
    - $0.75 \times 2 = 1.5$ (Bit=1, Rem=0.5).
    - $0.5 \times 2 = 1.0$ (Bit=1, Rem=0.0).
    - Result: **$0.11_{two}$**.

3. **Normalize:**
    - Shift $0.11_{two}$ right to get one non-zero digit left of dot.
    - Result: **$1.1_{two} \times 2^{-1}$**.

4. **Calculate Biased Exponent (E):**
    - **Single:** $-1 + 127 = 126$ ($01111110$).
    - **Double:** $-1 + 1023 = 1022$ ($01111111110$).

5. **Determine Fraction (F):**
    - Take normalized $1.1$, drop the leading `1.`.
    - F = **$1000...$**

Single Precision (32-bit):

|  S  | Exponent (8 bits) |   Fraction (23 bits)    |
| :-: | :---------------: | :---------------------: |
|  1  |     01111110      | 10000000000000000000000 |

Double Precision (64-bit):

| S | Exponent (11 bits) | Fraction (52 bits) |
| :---: | :---: | :---: |
| 1 | 01111111110 | 100000... (all zeros) |

---

## **Chapter 4: Datapath Exercises**

## **Chapter 4: Datapath Exercises (The "Pro" Control Unit)**

### **1. Master Control Truth Table (Grouped by Stage)**
*Organized by where the signal is used in the pipeline. This helps you map it to the diagram.*

| **Instr**  | **RegDst** | **ALUOp**     | **ALUSrc**  | **Branch** | **MemRead** | **MemWrite** | **RegWrite** | **MemtoReg** |
| ---------- | ---------- | ------------- | ----------- | ---------- | ----------- | ------------ | ------------ | ------------ |
| **R-Type** | **1** (Rd) | **10** (Func) | **0** (Reg) | 0          | 0           | 0            | **1**        | **0** (ALU)  |
| **lw**     | **0** (Rt) | **00** (Add)  | **1** (Imm) | 0          | **1**       | 0            | **1**        | **1** (Mem)  |
| **sw**     | **X**      | **00** (Add)  | **1** (Imm) | 0          | 0           | **1**        | **0**        | **X**        |
| **beq**    | **X**      | **01** (Sub)  | **0** (Reg) | **1**      | 0           | 0            | **0**        | **X**        |

---

### **3. The "X" Files (Don't Care Logic)**
*Why is it X? Because safety mechanisms elsewhere prevent the garbage data from doing harm.*

| Instruction | Signal | Value | **Why is it X (Don't Care)?** |
| :--- | :--- | :---: | :--- |
| **sw** | `RegDst` | **X** | We are **not writing** to any register (`RegWrite=0`). It doesn't matter which destination register bits (`Rt` or `Rd`) are sent to the "Write Register" port, because the "Write Enable" button is OFF. |
| **sw** | `MemtoReg` | **X** | Same reason. We aren't writing back to the register file, so it doesn't matter if the data waiting at the "Write Data" port comes from Memory or ALU. It will be ignored. |
| **beq** | `RegDst` | **X** | `beq` does not save a result. `RegWrite` is 0, so the destination register index is irrelevant. |
| **beq** | `MemtoReg` | **X** | `beq` does not write back. The value on the write bus is irrelevant. |
| **j** | `ALUSrc` | **X** | The Jump instruction uses the `Jump Address` fields and modifies the PC directly. It ignores the ALU entirely, so the ALU inputs don't matter. |

---

### **4. ALU Control Detail (Decoding the "10")**
*The Main Control sets `ALUOp`. The ALU Control unit sees that and decides the specific math.*

| Instruction | **ALUOp** (from Main Control) | **Funct Field** (Instruction bits 5-0) | **Actual ALU Action**               |
| :---------- | :---------------------------: | :------------------------------------: | :---------------------------------- |
| **lw / sw** |         **00** (Add)          |          XXXXXX (Don't Care)           | **Add** (Base + Offset)             |
| **beq**     |         **01** (Sub)          |          XXXXXX (Don't Care)           | **Subtract** (Check if result is 0) |
| **R-Type**  |    **10** (Look at Funct)     |             `100000` (add)             | **Add**                             |
| **R-Type**  |    **10** (Look at Funct)     |             `100010` (sub)             | **Subtract**                        |
| **R-Type**  |    **10** (Look at Funct)     |             `100100` (and)             | **AND**                             |
| **R-Type**  |    **10** (Look at Funct)     |             `100101` (or)              | **OR**                              |
| **R-Type**  |    **10** (Look at Funct)     |             `101010` (slt)             | **Set Less Than**                   |


### **3. Hardware Failure Analysis (Expanded)**

**Strategy:** To solve *any* failure scenario, follow this 3-step logic:
1.  **Locate:** Find the broken wire/gate on the diagram.
2.  **Define Error:** What value is it sending? (Always 0? Always 1?)
3.  **Check Impact:** Walk through every instruction. Does it *rely* on that signal being correct?

#### **Group A: The Branch & Jump Failures (Control Flow)**

**Scenario 1: AND Gate Stuck-at-1 (The "Forced Branch")**
* **The Mechanism:** The AND gate controls the PC Mux. If it sends a `1`, the Mux *ignores* the sequential instruction (PC+4) and *forces* the PC to jump to the Branch Target Address.
* **Impact:**
    * **`add`, `sub`, `lw`:** **BROKEN.** These instructions behave like unconditional jumps. They will execute, but then the program violently skips code instead of going to the next line.
    * **`beq` (Not Taken):** **BROKEN.** It branches even when the numbers aren't equal.
    * **`j`:** **SAFE.** The Jump Mux is *after* the Branch Mux, so the Jump signal overrides the broken Branch signal.

**Scenario 2: Zero Signal Stuck-at-0 (The "Blind Comparator")**
* **The Mechanism:** The `Zero` wire reports if `Input A == Input B`. A "Stuck-at-0" means the ALU shouts "They are DIFFERENT!" forever.
* **Impact:**
    * **`beq` (Equal):** **BROKEN.** The numbers are equal, but the ALU says they aren't. The AND gate sees a `0`, the branch is NOT taken, and the loop fails.
    * **`beq` (Not Equal):** **SAFE.** The ALU correctly reports "Not Equal".

**Scenario 3: Jump Stuck-at-1 (The "Infinite Hopper")**
* **The Mechanism:** The Control Unit forces the Jump Mux to *always* load the Target Address (bits 0-25).
* **Impact:**
    * **Everything except `j`:** **BROKEN.** Every single instruction acts like a Jump. The program cannot execute sequentially.

---

#### **Group B: Register Write Failures (Critical Data Loss)**

**Scenario 4: RegWrite Stuck-at-0 (The "Read-Only Mode")**
* **The Mechanism:** `RegWrite` is the "Save" button on the Register File. If it's stuck at 0, the button is broken. You can do math, but you can't save the answer.
* **Impact:**
    * **`add`, `sub`:** **BROKEN.** $3 + 4 = 7$ happens in the ALU, but the "7" bounces off the Register File and vanishes.
    * **`lw`:** **BROKEN.** The data arrives from memory, but cannot be saved to the register.
    * **`sw`, `beq`, `j`:** **SAFE.** These instructions only *read* from registers; they don't need to save anything.

**Scenario 5: RegWrite Stuck-at-1 (The "Accidental Overwrite")**
* **The Mechanism:** The "Save" button is jammed ON. Every instruction *will* write to a register, even if it shouldn't.
* **Impact:**
    * **`sw`:** **BROKEN.** It saves data to memory (correct), BUT it *also* overwrites register `$rt` with the Memory Address (incorrect).
    * **`beq`:** **BROKEN.** It compares values, BUT it *also* overwrites a register with the ALU result (Subtracted value). This destroys data.

---

#### **Group C: Data Path Selection Failures (Mux Failures)**

**Scenario 6: ALUSrc Stuck-at-0 (The "Register Loyal")**
* **The Mechanism:** The Mux before the ALU decides: "Do I use a Register or an Immediate?" Stuck-at-0 means it **ALWAYS uses a Register**.
* **Impact:**
    * **`lw`, `sw`:** **BROKEN.** These need the *Offset* (Immediate) to calculate the address (e.g., `8($s0)`). The Mux blocks the `8` and grabs a register value instead. The ALU calculates a garbage address.
    * **`add`, `sub`:** **SAFE.** They want a register value anyway.

**Scenario 7: ALUSrc Stuck-at-1 (The "Constant Lover")**
* **The Mechanism:** The Mux **ALWAYS uses the Immediate**.
* **Impact:**
    * **`add`, `sub`:** **BROKEN.** Instead of adding `$s1 + $s2`, it adds `$s1 + [Random Bits from the instruction]`.
    * **`lw`, `sw`:** **SAFE.** They need the Immediate.

**Scenario 8: MemtoReg Stuck-at-0 (The "ALU Forcer")**
* **The Mechanism:** The Write-Back Mux decides: "Does the data come from the ALU or Memory?" Stuck-at-0 means it **ALWAYS picks the ALU**.
* **Impact:**
    * **`lw`:** **BROKEN.** We want the *Data* inside the box. This error gives us the *Address* on the box label.
    * **`add`:** **SAFE.** It wants the ALU result.

**Scenario 9: MemtoReg Stuck-at-1 (The "Memory Forcer")**
* **The Mechanism:** The Write-Back Mux **ALWAYS picks Memory**.
* **Impact:**
    * **`add`, `sub`:** **BROKEN.** The ALU calculates the math result (correct), but the Mux throws it away. Instead, it reads a random value from Data Memory and saves *that* into the register.

---

#### **Group D: The Tricky Ones (Destination & Operation)**

**Scenario 10: RegDst Stuck-at-0 (The "Rt Obsession")**
* **The Mechanism:** This Mux aims the "Write Data" at the correct register. Stuck-at-0 means it always aims at **`$rt` (Bits 20-16)**.
* **Impact:**
    * **`lw`:** **SAFE.** `lw` naturally writes to `$rt`.
    * **`add`, `sub` (R-Type):** **BROKEN.** R-types are supposed to write to `$rd` (Bits 15-11). This error forces them to overwrite `$rt` instead, corrupting the wrong variable.

**Scenario 11: RegDst Stuck-at-1 (The "Rd Obsession")**
* **The Mechanism:** The Mux always aims at **`$rd` (Bits 15-11)**.
* **Impact:**
    * **R-Type:** **SAFE.**
    * **`lw`:** **BROKEN.** `lw` writes to `$rd` instead of `$rt`. Since `$rd` bits are part of the Immediate field in I-Type instructions, this writes to a semi-random register.

**Scenario 12: ALUOp Stuck-at-Add (00)**
* **The Mechanism:** The ALU Control is ignored; the ALU is forced to **ADD**.
* **Impact:**
    * **`beq`:** **BROKEN.** `beq` needs subtraction to check if `a - b = 0`. If it Adds, it checks if `a + b = 0`. The branch decision will be wrong.
    * **`sub`:** **BROKEN.** It becomes an `add`.
    * **`lw`, `sw`:** **SAFE.** They need addition for address calculation.

---

### **Summary Table: "Is it Broken?"**
*Use this quick check during the exam.*

| Fault | **R-Type** (`add`) | **Load** (`lw`) | **Store** (`sw`) | **Branch** (`beq`) |
| :--- | :---: | :---: | :---: | :---: |
| **RegDst Stuck-0** | ❌ Wrong Reg | ✅ Safe | N/A | N/A |
| **RegDst Stuck-1** | ✅ Safe | ❌ Wrong Reg | N/A | N/A |
| **RegWrite Stuck-0** | ❌ Lost Data | ❌ Lost Data | ✅ Safe | ✅ Safe |
| **RegWrite Stuck-1** | ✅ Safe | ✅ Safe | ❌ Corrupts Reg | ❌ Corrupts Reg |
| **ALUSrc Stuck-0** | ✅ Safe | ❌ Bad Addr | ❌ Bad Addr | ✅ Safe |
| **ALUSrc Stuck-1** | ❌ Bad Math | ✅ Safe | ✅ Safe | ❌ Bad Logic |
| **MemtoReg Stuck-0** | ✅ Safe | ❌ Saves Addr | N/A | N/A |
| **MemtoReg Stuck-1** | ❌ Saves Mem | ✅ Safe | N/A | N/A |