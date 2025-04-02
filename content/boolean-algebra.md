---
title: Boolean Algebra
---

Nearly two centuries after Leibniz published how to use binary system to represent any number, another major advancement came up from George Boole.

While studying logics, Boole was inspired to create a new mathematical framework. The goal is to systematically solve arguments like "If A is true, and B is true, then C must be true" by representing them mathemathically using 1 for true and 0 for false.

### Logical Operation

There are two states:
- 1 for true
- 0 for false

There are three primary operations:
- AND, multiplication (+)
- OR, addition (.)
- NOT, negation (~)

Instead of using an abstract argument, let's use easier examples.

> If I have money (A) AND the grocery store is open (B), then I can buy food (C).

The result C is 1 only if A = 1 and B = 1. This is the fundamental rule for AND operation.

If we change the value of A and B, and observe the result of C, we will get this table.

| Money (A) | Store (B) | Can buy food (C)|
|---|---|---------|
| 0 | 0 |    0    |
| 0 | 1 |    0    |
| 1 | 0 |    0    |
| 1 | 1 |    1    |

We call this table a truth table. This particular table is called the truth table for AND operation.

With the same logic, we can make truth tables for OR and NOT.

> If I have a bicycle (A) OR the train is running (B), then I can go to school (C).
> 
The result C is 0 only if A = 0 and B = 0. This is the fundamental rule for OR operation.

The truth table for OR is:
| Bicycle (A) | Train (B) | Can go to school (C) |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   1    |

Lastly, we have NOT operation which is the simplest. Basically, it negates the argument.

> I eat (A).

If I eat (A is 1), then the negation of A is 0 (I do NOT eat). 

The truth table for NOT is:
| I eat (A) | I do not eat (~A)|
|---|-------|
| 0 |   1   |
| 1 |   0   |


### Algebra Laws

There are also algebraic laws that can be used for logical operations:
- Commutative Laws
- Associative Laws
- Distributi Laws
- Identity Laws
- Null Laws
- Complement Laws


#### Commutative Laws
In AND and OR operations, the order of inputs doesn’t matter.
$$
A \cdot B = B \cdot A \quad (\text{AND}) \\
A + B = B + A \quad (\text{OR})
$$

#### Associative Laws
In AND and OR operations, input can be grouped and it will not affect the result of the operations.
$$
(A \cdot B) \cdot C = A \cdot (B \cdot C) \quad (\text{AND}) \\
(A + B) + C = A + (B + C) \quad (\text{OR})
$$

#### Distributive Laws
We can distribute AND over OR operations, and vice versa.
$$
A \cdot (B + C) = (A \cdot B) + (A \cdot C) \\
A + (B \cdot C) = (A + B) \cdot (A + C)
$$

#### Identity Laws

Multiplying a variable by 1 (AND) or adding 0 (OR) to it does not change the result.

$$
A \cdot 1 = A \quad \\
A + 0 = A \quad
$$

#### Null Laws

Multiplying a variable by 0 (AND) results in 0 and adding 0 (OR) to it results in 1. 

$$
A \cdot 0 = 0 \quad  \\
A + 1 = 1 \quad
$$

#### Complement Laws

Multiplying (AND) by the complement (NOT) of a variable results in 0.
Adding (OR) by the complement (NOT) of a variable results in 1.

A variable ANDed or ORed with its complement gives fixed results:
$$
A \cdot \overline{A} = 0 \quad \\
A + \overline{A} = 1 \quad 
$$

### De Morgan's Laws
Following the strong foundation laid out by Boole, Augustus de Morgan, who was a mathematician and logician, expanded it even further. For de Morgan, it was to use negation (NOT) to interact with the previous Boolean algebra.
   
First law:
$$
\overline{A \cdot B} = \overline{A} + \overline{B} \\
NOT(A \cdot B) = (NOT A) + (NOT B)
$$

Second law:
$$
\overline{A + B} = \overline{A} \cdot \overline{B}\\
NOT (A + B) = (NOT A) \cdot (NOT B)
$$

This will later be useful to make Boolean algebra more simplified.