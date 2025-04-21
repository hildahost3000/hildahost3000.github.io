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
Sum = A \oplus B \\
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

$$
\begin{aligned}
\text{Sum} &= A \oplus B \oplus C_{\text{in}} \\
\text{Carry-out} &= (A \cdot B) + (B \cdot C_{\text{in}}) + (A \cdot C_{\text{in}})
\end{aligned}
$$


It is also easy to imagine a full adder as two half-adders combined.

### Ripple Carry Adder
Knowing that half carry adders can be used to make a full adder, now we learn that full adders can be used to make a ripple carry adder.

As the name suggest, this is an adder whose carry can be carried to the next one, and to the next one, and so on that it resembles a ripple. This can be used to perform addition of binary numbers. It could be built using multiple full addders connected in series. And if broken down even smaller, each of the digit can be calculated using a half adder.

