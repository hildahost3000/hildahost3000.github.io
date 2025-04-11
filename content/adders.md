---
title: Adders
---

One of the earliest task of the earliest computers is to perform arithmetic. Adders are important to perform addition and to support as a building block to other arithmetic operations. And not just performing addition for users, but also for the computer itself.

There are three types of adders:
- Half Adder
- Full Adder
- Ripple Carry Adder

### Half Adder

Half adder performs addition of two single binary digits, called as significant bits. It takes the 2 significant bits as input, and produce 2 output, one for the sum result and another one for whether it has a "carry" or not. When we add binary 0 and 1, the result is 1. But when we add 1 and 1, the result is 10, which have 2 digits. That's why carry is needed.

| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 | 0   | 0     |
| 0 | 1 | 1   | 0     |
| 1 | 0 | 1   | 0     |
| 1 | 1 | 0   | 1     |

$$
\begin{aligned}
Sum = A + B \\
Carry = A \cdot B
\end{aligned}
$$ 

Plain and simple.

### Full Adder

Full adder performs addition of two single significant bits, and a carry from the previous operation.


| A | B | Carry-in | Sum| Carry-out|
|---|---|------|---------|-------------------|
| 0 | 0 | 0    | 0       | 0                 |
| 0 | 0 | 1    | 1       | 0                 |
| 0 | 1 | 0    | 1       | 0                 |
| 0 | 1 | 1    | 0       | 1                 |
| 1 | 0 | 0    | 1       | 0                 |
| 1 | 0 | 1    | 0       | 1                 |
| 1 | 1 | 0    | 0       | 1                 |
| 1 | 1 | 1    | 1       | 1                 |

### Logic Equations for Full Adder

- **Sum (\( S \))**:
  \[
  S = A \oplus B \oplus C_{\text{in}}
  \]
  Where \(\oplus\) denotes the XOR operation.

- **Carry-out (\( C_{\text{out}} \))**:
  \[
  C_{\text{out}} = (A \cdot B) + (B \cdot C_{\text{in}}) + (A \cdot C_{\text{in}})
  \]
  Where \(\cdot\) denotes the AND operation, and \(+\) denotes the OR operation.

These equations and the truth table describe how a full adder computes the sum and carry-out for three input bits. The full adder is fundamental in building more complex arithmetic circuits like ripple carry adders for multi-bit binary addition.