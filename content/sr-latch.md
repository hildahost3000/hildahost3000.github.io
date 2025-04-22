---
title: SR Latch
---

The SR in SR Latch stands for Set and Reset. This is the simples type of latch, constructed using either NAND or NOR gates. It will receive 2 input, Set (S) and Reset (R), and produce 2 ouput, Q and Q̅ (the complement of Q).

The operation is also very simple. There are 4 states determined based on S and R. Since there are two ways to create SR latch, there are two truth tables.

### SR Latch Using NOR Gates

| S (Set) | R (Reset) | Q (Output) | Q̅ (Complement) | State        |
|---------|-----------|------------|----------------|--------------|
| 0       | 0         | Q (hold)   | Q̅ (hold)      | Hold         |
| 0       | 1         | 0          | 1              | Reset        |
| 1       | 0         | 1          | 0              | Set          |
| 1       | 1         | Invalid    | Invalid        | Invalid State|

The "Invalid" state occurs when both inputs are 1, causing both outputs to be 0, which is not allowed since Q and Q̅ should always be complements.

### SR Latch Using NAND Gates

| S (Set) | R (Reset) | Q (Output) | Q̅ (Complement) | State        |
|---------|-----------|------------|----------------|--------------|
| 0       | 0         | Invalid    | Invalid        | Invalid State|
| 0       | 1         | 1          | 0              | Set          |
| 1       | 0         | 0          | 1              | Reset        |
| 1       | 1         | Q (hold)   | Q̅ (hold)      | Hold         |

The "Invalid" state for NAND gates occurs when both inputs are 0, causing both outputs to be 1, which is also not allowed since Q and Q̅ should be complements.

### The value of Q
The initial Q is undefined until a Set or Reset state is explicitly defined. The value Q is basically the value that wants to be stored.

The benefit of using SR Latch instead of any gate, is because latch does not require continuous input. The input for Set and Reset only needs to be given once, and the value could be stored until the next set or reset is performed.