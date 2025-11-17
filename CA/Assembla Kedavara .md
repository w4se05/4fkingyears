## Overview
Assembly language is the direct interface between **software and hardware**.  
In MIPS, every instruction performs one simple operation on registers or memory.  
This chapter defines the **Instruction Set Architecture (ISA)** — the contract between hardware and software.

---
## [[Principles of MIPS Design]]

| Principle | Explanation |
|------------|--------------|
| **Simplicity favors regularity** | Fixed-length 32-bit instructions simplify decoding. |
| **Smaller is faster** | Limited number of registers (32) enables fast access. |
| **Make the common case fast** | Optimize arithmetic and data transfer — the most frequent operations. |
| **Good design demands compromise** | Balance performance, cost, and ease of implementation. |

---

## [[Registers and Operands]]

### Register File
MIPS has **32 general-purpose registers**, each **32 bits** wide.

| Register | Name | Usage |
|-----------|------|--------|
| `$zero` | Constant 0 | Always reads 0 |
| `$at` | Assembler Temp | Reserved by assembler |
| `$v0–$v1` | Values | Function return values |
| `$a0–$a3` | Arguments | Function parameters |
| `$t0–$t9` | Temporaries | Caller-saved |
| `$s0–$s7` | Saved | Callee-saved |
| `$k0–$k1` | Kernel | Reserved for OS |
| `$gp` | Global Pointer | Static data |
| `$sp` | Stack Pointer | Top of stack |
| `$fp` | Frame Pointer | Stack frame base |
| `$ra` | Return Address | Procedure return |

**Example**
```mips
add $t0, $s1, $s2    # $t0 = $s1 + $s2
````

---

## [[Memory Operands]]

MIPS uses **byte-addressed** memory.  
Because arithmetic operates only on registers, data must be moved explicitly:

```mips
lw $t0, 8($sp)     # load word from memory[$sp + 8]
sw $t1, 12($sp)    # store word to memory[$sp + 12]
```

Each address refers to **bytes**; words are 4 bytes and must be **aligned** (address % 4 = 0).

---

## [[Immediate Operands]]

Some instructions embed constants directly:

```mips
addi $s3, $s3, 10    # $s3 = $s3 + 10
andi $t0, $t0, 0xFF  # mask lower byte
```

Immediate field is 16 bits → range ≈ −32768 to 32767.

---

## [[Signed vs Unsigned Numbers]]

|Concept|Signed|Unsigned|
|---|---|---|
|Range|−2³¹ … 2³¹−1|0 … 2³²−1|
|Addition|`add`|`addu`|
|Subtraction|`sub`|`subu`|
|Comparison|`slt`|`sltu`|

**Two’s Complement**: invert bits + 1 to negate.  
Overflow occurs when signs of operands match but differ from result.

---

## [[Instruction Formats]]

All instructions are 32 bits long.

### R-type (Register)

|Field|Bits|Description|
|---|---|---|
|`opcode`|6|Operation code|
|`rs`|5|Source 1|
|`rt`|5|Source 2|
|`rd`|5|Destination|
|`shamt`|5|Shift amount|
|`funct`|6|Function specifier|

Example:

```mips
add $s1, $s2, $s3
```

---

### I-type (Immediate or Memory)

|Field|Bits|Description|
|---|---|---|
|`opcode`|6|Operation|
|`rs`|5|Base/source|
|`rt`|5|Destination|
|`immediate`|16|Constant / offset|

Example:

```mips
lw $t0, 8($sp)
addi $s0, $s0, 1
```

---

### J-type (Jump)

|Field|Bits|Description|
|---|---|---|
|`opcode`|6|Operation|
|`address`|26|Target address / index|

Example:

```mips
j  main
```

---

## [[Arithmetic and Logical Operations]]

|Category|Instruction|Example|Description|
|---|---|---|---|
|Arithmetic|`add`, `sub`|`add $t0,$t1,$t2`|Integer add/sub|
|Immediate|`addi`|`addi $t0,$t1,5`|Add constant|
|Comparison|`slt`, `sltu`|`slt $t0,$s1,$s2`|Set < test|
|Logical|`and`, `or`, `xor`, `nor`|`and $t0,$t1,$t2`|Bitwise ops|
|Shift|`sll`, `srl`, `sra`|`sll $t0,$t1,2`|Shift left/right|

---

## [[Decision and Control Flow]]

### Conditional Branches

Branches compare two registers and optionally jump.

```mips
beq $t0, $t1, Target   # if ($t0 == $t1) goto Target
bne $t0, $t1, Target   # if ($t0 != $t1) goto Target
```

Target is **PC-relative**:  
`Address = PC + 4 + (offset × 4)`

### Unconditional Jumps

```mips
j  Label       # Jump to absolute address
jr $ra         # Jump to address in $ra
jal Func       # Jump and link: saves return addr in $ra
```

---

## [[Procedures and Stack Frames]]

Procedure calls use **stack-based convention**.

|Register|Purpose|Saved by|
|---|---|---|
|`$a0–$a3`|Arguments|Caller|
|`$v0–$v1`|Return values|Callee|
|`$ra`|Return address|Callee|
|`$sp`|Stack pointer|Both|
|`$s0–$s7`|Saved regs|Callee|

### Example: Function Call

```mips
# caller
addi $sp,$sp,-8
sw   $ra,4($sp)
sw   $a0,0($sp)
jal  square
	lw   $ra,4($sp)
addi $sp,$sp,8
```

```mips
# callee: square(x)
square:
    mul $v0,$a0,$a0
    jr $ra
```

---

## [[Memory Organization and Addressing]]

- Memory is **byte addressed**; each word = 4 bytes.
    
- Data segment → globals / statics.
    
- Stack segment → procedure frames.
    
- Heap segment → dynamic allocation (`malloc`/`new`).
    

**Endianness:**  
MIPS = little-endian by convention in most simulators (least-significant byte first).

---

## [[Large Constants and Addresses]]

Immediates are limited to 16 bits → use `lui` and `ori`.

```mips
lui $t0, 0x1234     # load upper 16 bits
ori $t0, $t0, 0x5678  # combine lower 16 bits
# Result: $t0 = 0x12345678
```

---

## [[Bitwise Operations]]

Bit manipulation enables flag control and masking.

```mips
and $t0, $t1, $t2     # bitwise AND
or  $t0, $t1, $t2     # bitwise OR
xor $t0, $t1, $t2     # exclusive OR
nor $t0, $t1, $t2     # NOT (A OR B)
```

**Typical uses**

- Masking bits: `andi $t0,$t0,0xFF`
    
- Setting bits: `ori $t0,$t0,0x8`
    
- Testing bits: `and` + `beq`/`bne`
    

---

## [[Synchronization and Parallelism Primitives]]

Used in multiprocessor settings to ensure atomicity.

```mips
ll $t0, 0($s1)     # load linked
add $t0, $t0, 1
sc $t0, 0($s1)     # store conditional; succeeds only if no interference
beq $t0, $zero, retry
```

If another processor modifies the location, `sc` fails → must retry.

---

## [[Translating and Running a Program]]

**Stages of translation**

1. **Compiler** → converts C → Assembly
    
2. **Assembler** → Assembly → Object code (binary + symbol table)
    
3. **Linker** → merges objects, resolves labels
    
4. **Loader** → loads into memory, initializes registers, and jumps to `main`
    

---

## [[Complete Example – Sorting]]

Example: _C bubble sort → MIPS_

```c
for (i=0; i<n-1; i++)
  for (j=i+1; j<n; j++)
     if (A[i] > A[j]) swap(A[i], A[j]);
```

Translated sketch:

```mips
outer:
    addi $t0,$zero,0         # i=0
outer_loop:
    slti $t1,$t0,$s3         # i < n ?
    beq  $t1,$zero,done
    addi $t2,$t0,1           # j=i+1
inner_loop:
    slt  $t3,$t2,$s3
    beq  $t3,$zero,inc_i
    sll  $t4,$t0,2           # offset i
    sll  $t5,$t2,2           # offset j
    add  $t6,$s1,$t4
    add  $t7,$s1,$t5
    lw   $t8,0($t6)
    lw   $t9,0($t7)
    slt  $t3,$t9,$t8
    beq  $t3,$zero,next_j
    sw   $t8,0($t7)
    sw   $t9,0($t6)
next_j:
    addi $t2,$t2,1
    j    inner_loop
inc_i:
    addi $t0,$t0,1
    j    outer_loop
done:
```

---

## [[Arrays vs Pointers]]

In C, `A[i]` is equivalent to `*(A + i)`.  
MIPS computes address:

```
address = base + i * element_size
```

Example:

```mips
lw $t0, 4($s1)   # A[1], assuming A base in $s1
```

---

## [[Understanding Program Performance]]

|Level|Performance Factor|Control Levers|
|---|---|---|
|Algorithm|Asymptotic cost|Choose better algorithms|
|Compiler / Language|Instruction count|Optimize code generation|
|Processor|CPI, clock rate|Pipeline, cache, branch predict|
|Memory / I-O|Latency / bandwidth|Caches, parallel I/O|

---

## [[Common Pitfalls]]

- **Mismatched signed/unsigned** comparisons → unexpected results.
    
- **Unaligned memory access** → exceptions.
    
- **Forgetting to save `$ra`** before nested `jal`.
    
- **Stack pointer mis-management** → corrupted data.
    
- **Immediate overflow** beyond ±32 k.
    

---

## [[Concluding Remarks]]

MIPS exemplifies **RISC philosophy** — simplicity, regularity, and efficiency.  
Mastery of these instructions clarifies how high-level constructs execute on real hardware, and forms the conceptual base for understanding **pipelining**, **caches**, and **parallelism** in later chapters.

---

## [[Quick Reference Tables]]

### Arithmetic and Logical Ops

|Type|Syntax|Description|
|---|---|---|
|Add|`add rd,rs,rt`|rd = rs + rt|
|Add Immediate|`addi rt,rs,imm`|rt = rs + imm|
|Subtract|`sub rd,rs,rt`|rd = rs − rt|
|AND|`and rd,rs,rt`|Bitwise AND|
|OR Immediate|`ori rt,rs,imm`|Bitwise OR with imm|
|Set Less Than|`slt rd,rs,rt`|rd = (rs < rt)? 1: 0|

### Branch / Jump

|Instr|Action|
|---|---|
|`beq`|branch if equal|
|`bne`|branch if not equal|
|`j`|unconditional jump|
|`jr`|jump register|
|`jal`|jump and link|

### Memory

|Instr|Action|
|---|---|
|`lw`|load word|
|`sw`|store word|
|`lb` / `sb`|load/store byte|

---

> **Tip 🧠**  
> In MIPS, _everything_ reduces to:  
> 1️⃣ Load data → 2️⃣ Operate in registers → 3️⃣ Store result.  
> Understanding this triad is key to hardware-level fluency.

---
