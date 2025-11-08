## 🧠 Conceptual Section (Teach Mode)

### 1. Instruction Set Architecture (ISA)

> [!Definition] 💡 **ISA**
> The *Instruction Set Architecture* is the interface between hardware and software, defining what operations the computer can perform, how data is represented, and how programs interact with the hardware.

**Key Roles**
- Specifies **operations** (arithmetic, logic, control)
- Defines **registers**, **memory addressing**, and **data types**
- Ensures **program portability** across implementations of the same ISA

**Common ISAs:** MIPS, ARM, x86

> [!Note] 📘  
> Once you master one ISA, others are easier to learn — all share similar structural ideas.

---

### 2. Registers and Operands

> [!Definition] 💾 **Register**
> A small, fast storage cell directly inside the CPU used to hold operands for arithmetic or logic operations.

In **MIPS**:
- 32 registers, each 32 bits (1 word)
- `$0–$31` are general purpose  
- `$zero` always stores constant 0

**Design Principle:** *Smaller is faster* — 32 registers balance simplicity and performance.

---

### 3. Memory Operands and Addressing

When data exceeds register capacity, it is stored in memory.

> [!Definition] 💡 **Data Transfer Instructions**
> Move data between memory and registers:
> - `lw` (load word): register ← memory  
> - `sw` (store word): memory ← register

**Byte Addressing:**  
Each address points to one byte.  
A 32-bit word occupies 4 bytes, so word addresses differ by 4.

**Alignment Restriction:** words start at addresses multiple of 4.

**Endianness**
- *Big-endian:* most-significant byte at lowest address  
- *Little-endian:* least-significant byte at lowest address

---

### 4. Immediate Operands

> [!Definition] 💡 **Immediate**
> A constant value embedded directly in the instruction.

Example:  
`addi $s3, $s3, 4` adds 4 to register `$s3`.

Immediate operands save memory access time and energy.

---

### 5. Binary Representation and Signed Numbers

Computers represent numbers in **binary (base 2)** using bits {0, 1}.

> [!Definition] 💡 **Two’s Complement**
> Standard format for signed integers where the **most significant bit (MSB)** is the sign (0 positive, 1 negative).

**Range:**
$$
[-2^{n-1},\, 2^{n-1}-1]
$$

**Negation:** invert all bits and add 1.

> [!Example] ⚙️  
> $(5_{10}=00000101_2 \Rightarrow -5_{10}=11111011_2)$

---

### 6. Sign Extension

> [!Definition] 💡 **Sign Extension**
> Expanding an n-bit two’s complement value to m bits (m > n) by copying the sign bit into the new high bits.

Positive → fill with 0s | Negative → fill with 1s.

---

### 7. MIPS Instruction Formats

| Type | Fields | Purpose |
|------|---------|----------|
| **R-type** | `op | rs | rt | rd | shamt | funct` | Register operations |
| **I-type** | `op | rs | rt | immediate` | Immediate or memory operations |
| **J-type** | `op | address` | Jump instructions |

> [!Note] 🧩  
> Fixed 32-bit instruction length simplifies decoding and pipelining.

---

### 8. Logical and Shift Operations

| Instruction | Description |
|--------------|-------------|
| `sll` | Shift Left Logical – multiply by 2ⁿ |
| `srl` | Shift Right Logical – divide by 2ⁿ |
| `and`, `andi` | Bitwise AND |
| `or`, `ori` | Bitwise OR |
| `nor` | Bitwise NOT = NOR with 0 |

> [!Example] ⚙️  
> `sll $t2,$s0,4` → shifts `$s0` left 4 bits (×16).  

---

### 9. Decision Making and Branching

> [!Definition] 💡 **Conditional Branch**
> Alters program flow based on comparisons between registers.

- `beq $r1,$r2,label` → branch if equal  
- `bne $r1,$r2,label` → branch if not equal  

**Unconditional Jumps**
- `j label` – jump  
- `jal label` – jump and link (save return address)  
- `jr $ra` – return to caller

---

### 10. Comparison Instruction: `slt`

> [!Definition] 💡 **Set on Less Than**
> ```
> slt  $t0,$s3,$s4   # $t0=1 if $s3<$s4
> slti $t0,$s2,10    # $t0=1 if $s2<10
> ```

Used for implementing relational conditions together with `beq`/`bne`.

---

### 11. Procedures and the Stack

> [!Definition] 💡 **Procedure (Function)**
> A reusable block of code with parameters and return values.

**Calling Convention Registers**

| Purpose | Registers |
|----------|------------|
| Arguments | `$a0–$a3` |
| Return values | `$v0–$v1` |
| Return address | `$ra` |
| Stack pointer | `$sp` (29) |

The **stack** (LIFO structure) stores saved registers and local variables.  
Stacks in MIPS grow **downward** in memory.

---

### 12. Procedure Call Instructions

| Instruction | Function                                             |
| ----------- | ---------------------------------------------------- |
| `jal`       | Jump and Link – store return address (PC+4) in `$ra` |
| `jr $ra`    | Jump Register – return to caller                     |

---

### 13. Addressing Modes in MIPS

| Mode | Description | Example |
|------|--------------|----------|
| Immediate | Constant within instruction | `addi $t0,$t1,4` |
| Register | Operand in register | `add $t0,$t1,$t2` |
| Base (Displacement) | Memory address = register + offset | `lw $t0,8($sp)` |
| PC-Relative | Branch target = PC + offset | `beq $s0,$s1,L1` |
| Pseudodirect | 26-bit target + upper PC bits | `j target` |

---

### 14. Decoding Machine Language

> [!Example] ⚙️ **Decode 00AF8020₁₆**
>
> Binary → `000000 00101 01111 10000 00000 100000`  
> Fields: `op=000000`, `rs=$a1`, `rt=$t7`, `rd=$s0`, `funct=100000 (add)`  
> ✅ Instruction = `add $s0,$a1,$t7`

---

## 📘 Examples & Applications (Exam Mode)

### Example 1 — `if-else` Compilation

**C Code**
```
if (i == j)
  f = g + h;
else
  f = g - h;
Registers: $s0=f, $s1=g, $s2=h, $s3=i, $s4=j
```

```
MIPS

asm
Copy code
bne $s3,$s4,Else
add $s0,$s1,$s2
j Exit
Else: sub $s0,$s1,$s2
Exit:
```

### Example 2 — While Loop
C Code
```
c
Copy code
while (save[i] == k)
  i++;
Registers: $s3=i, $s5=k, $s6=base(save)
```

```
MIPS

asm
Copy code
Loop: sll $t1,$s3,2
add $t1,$t1,$s6
lw  $t0,0($t1)
bne $t0,$s5,Exit
addi $s3,$s3,1
j Loop
Exit:
```
### Example 3 — Procedure Call Using Stack
C Code
```
c
Copy code
int leaf_example(int g,int h,int i,int j){
  int f;
  f = (g + h) - (i + j);
  return f;
}
```

```
MIPS

asm
Copy code
leaf_example:
  addi $sp,$sp,-12
  sw $t1,8($sp)
  sw $t0,4($sp)
  sw $s0,0($sp)
  add $t0,$a0,$a1
  add $t1,$a2,$a3
  sub $s0,$t0,$t1
  add $v0,$s0,$zero
  lw $s0,0($sp)
  lw $t0,4($sp)
  lw $t1,8($sp)
  addi $sp,$sp,12
  jr $ra
```
