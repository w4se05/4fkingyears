## 🧠 Conceptual Section (Teach Mode)

### 1. Introduction

All computer arithmetic is based on **binary representation**.  
Since hardware can only represent a finite number of bits, every computation must handle issues of **overflow**, **precision**, and **rounding**.

> [!Goal] 🎯  
> Understand integer and floating-point arithmetic, detect overflow, and explain how multiplication/division are implemented in hardware.

---

### 2. Overflow in Addition and Subtraction

> [!Definition] 💡 **Overflow**
> Occurs when the arithmetic result exceeds the range representable by the given number of bits.

**Rules**
- **Addition:** Overflow occurs when adding two numbers with the **same sign** produces a result with a **different sign**.
- **Subtraction:** Overflow occurs when subtracting numbers of **different signs** yields a result with the **wrong sign**.

**Examples**
| Operation | Example | Overflow? |
|------------|----------|------------|
| (+) + (+) → (−) | `+120 + +100` | ✅ Yes |
| (−) + (−) → (+) | `−80 + −90` | ✅ Yes |
| (+) − (−) → (−) | `+5 − (−10)` | ✅ Yes |
| (−) − (+) → (+) | `−3 − (+4)` | ✅ Yes |

**MIPS Instructions**
- Detect overflow: `add`, `addi`, `sub`
- Ignore overflow: `addu`, `addiu`, `subu`

> [!Note] 📘  
> Hardware can raise an **overflow exception** or ignore it, depending on the instruction used.

---

### 3. Binary Multiplication

> [!Definition] 💡 **Multiplication Algorithm**
> Repeatedly shift and add partial products to form the result.

**Terminology**
- **Multiplicand (M):** Number being multiplied  
- **Multiplier (Q):** Number that multiplies  
- **Product (P):** Final 64-bit result for 32-bit operands

**Basic Algorithm**
1. Initialize `P = 0`.
2. If least significant bit (LSB) of multiplier = 1 → add multiplicand to `P`.
3. Shift multiplicand left by 1, multiplier right by 1.
4. Repeat for 32 steps.

> [!Property] 🧩  
> 32-bit × 32-bit → 64-bit product; each iteration requires one addition and two shifts.

---

### 4. Multiplication Hardware Implementation

- **Registers:**  
  - Multiplicand (32 bits)  
  - Multiplier (32 bits)  
  - Product (64 bits)  
  - ALU (32-bit)
- **Refined Design:** Combines the multiplier into the right half of the product register; product is shifted right instead of the multiplicand being shifted left.

> [!Note] ⚙️  
> This design reduces hardware size and simplifies control logic.

---

### 5. Division

> [!Definition] 💡 **Division Algorithm**
> Hardware division mirrors long division using **repeated subtraction** and **bitwise shifting**.

**Terminology**
- **Dividend (D):** Number to be divided  
- **Divisor (V):** Number dividing D  
- **Quotient (Q):** Result  
- **Remainder (R):** Leftover after division

**Algorithm Steps**
1. Initialize `R = D`.  
2. Shift divisor right one bit per iteration.  
3. Subtract divisor from remainder.  
4. If result ≥ 0 → record 1 in quotient bit; else restore R and record 0.  
5. Repeat until quotient fully computed.

> [!Property] 🧩  
> Similar to multiplication, division uses conditional subtraction and shifting.

---

### 6. Optimized Division Hardware

- **Divisor, ALU, Quotient:** 32 bits  
- **Remainder Register:** 64 bits  
- **Improvement:** Remainder shifts left each iteration; quotient merges into remainder’s right half.  

This halves ALU size and improves speed.

---

### 7. Floating-Point Representation

> [!Definition] 💡 **Floating-Point Number**
> Represents real numbers in binary scientific notation:
> $$
> (-1)^S \times F \times 2^E
> $$
> where  
> \(S\) = sign bit,  
> \(F\) = fraction (mantissa),  
> \(E\) = exponent.

**Normalized Form**
- Binary scientific form ensures one nonzero bit before the binary point.  
Example:
$$
1.101_2 \times 2^3
$$

> [!Note] 📘  
> Floating-point allows a movable binary point for representing wide numeric ranges.

---

### 8. IEEE 754 Floating-Point Standard

| Format | Bits | Sign | Exponent | Fraction | Bias |
|---------|------|-------|-----------|-----------|-------|
| Single (32-bit) | 32 | 1 | 8 | 23 | 127 |
| Double (64-bit) | 64 | 1 | 11 | 52 | 1023 |

> [!Formula] 🧮  
> Normalized Value:
> $$
> (-1)^S \times (1 + \text{Fraction}) \times 2^{E_{\text{stored}} - \text{Bias}}
> $$
> The leading “1” is implicit — called the *hidden bit*.

---

### 9. IEEE Encodings and Special Cases

Let `e` = exponent field, `f` = fraction field.

| e | f | Meaning | Representation |
|---|---|----------|----------------|
| 0 | 0 | ±0 | Zero |
| 0 | ≠0 | Subnormal | $(-1)^S(0 + f)2^{1-Bias}$ |
| 1 ≤ e ≤ eₘₐₓ−1 | Any | Normalized | $(-1)^S(1 + f)2^{e-Bias}$ |
| e = eₘₐₓ, f = 0 | ±∞ | Overflow |
| e = eₘₐₓ, f ≠ 0 | NaN | Not a Number |

> [!Property] 🧩  
> **Overflow → ±∞**, **Underflow → Subnormal or 0**

---

### 10. Range and Precision

| Format | Exponent Range | Approx Range | Precision |
|---------|----------------|---------------|------------|
| Single | [1, 254] | ±[2⁻¹²⁶, 2¹²⁷] | ~7 digits |
| Double | [1, 2046] | ±[2⁻¹⁰²², 2¹⁰²³] | ~16 digits |

> [!Note] 📘  
> Using **biased exponents** allows unsigned comparisons and simplifies hardware logic.

---

### 11. Floating-Point Arithmetic

#### 11.1 Addition/Subtraction
1. Align exponents.  
2. Add/subtract mantissas.  
3. Normalize and round result.  
4. Detect overflow/underflow.

#### 11.2 Multiplication
1. Add exponents (minus bias).  
2. Multiply mantissas.  
3. Normalize and round.  
4. Detect overflow/underflow.

> [!Warning] ⚠️  
> Floating-point arithmetic is **not associative** — \((a+b)+c \neq a+(b+c)\) due to rounding.

---

### 12. Numerical Limitations

> [!Definition] 💡 **Finite Precision**
> Since floating-point uses limited bits, not all real numbers can be exactly represented.

**Consequences**
- Rounding errors accumulate over many operations.  
- Small differences in order of evaluation can produce large numeric differences.

---

### 13. Key MIPS Arithmetic Insights

- Most modern processors use **two’s complement** for integer arithmetic.  
- Floating-point arithmetic follows **IEEE 754**.  
- Arithmetic operations are often **pipelined** and **parallelized** for speed.  
- MIPS includes both **integer** and **floating-point** cores:
  - Integer core: ~98% of instructions  
  - Floating-point core: ~66% of arithmetic-heavy workloads

---

## 📘 Examples & Applications (Exam Mode)

### Example 1 — Overflow Detection

Add:
$$
A = 01000000_2\ (64_{10}), \quad B = 01000000_2\ (64_{10})
$$
$$
A + B = 10000000_2\ (-128_{10})
$$
✅ Overflow occurred — same-sign addition produced opposite-sign result.

---

### Example 2 — Unsigned Multiplication (4-bit)

Multiply:
$$
A = 1011_2 (11_{10}), \quad B = 0110_2 (6_{10})
$$

**Partial Products**

| Step | Multiplier Bit | Add | Intermediate Product |
|------|----------------|------|-----------------------|
| 1 | 0 | — | 000000 |
| 2 | 1 | A<<1 | 10110 |
| 3 | 1 | A<<2 | 101100 |
| 4 | 0 | — | — |

**Final:**
$$
P = 01000110_2 = 66_{10}
$$

✅ Result = 11 × 6 = 66

---

### Example 3 — IEEE 754 Encoding (Single Precision)

Encode:
$$
x = -6.75_{10}
$$

**Step 1:** Binary  
$$
6.75_{10} = 110.11_2 = 1.1011_2 \times 2^2
$$

**Step 2:** Fields  
- Sign = 1  
- Exponent = 2 + 127 = 129 = 10000001₂  
- Fraction = 10110000000000000000000₂

**Result**
1 | 10000001 | 10110000000000000000000  
= 11000000110110000000000000000000₂  
= C0D80000₁₆

✅ IEEE 754 Single Precision = `C0D80000₁₆`  
--- 
## 🧾 Summary Section 
- **Overflow:** Occurs when result exceeds bit range.   
- **Multiplication:** Performed via shift-and-add; 32×32 → 64-bit result.  
- **Division:** Iterative shift-and-subtract method.   
- **Floating-Point:**     - Value = $(-1)^S(1 + f)2^{E-Bias}$    
- **Bias** = 127 (single), 1023 (double)    
- **Special cases:** ±0, Subnormal, ±∞, NaN   
- **Precision:** Limited → rounding errors inevitable.  
- **IEEE 754:** Defines format, rounding, and exceptions for floating-point arithmetic.``