---
title: Basic Gates Implementation
---

To implement Boolean logic in physical world, we will use relay for starter. Let's break it down by using Claude Shannon's famous master thesis.

### Basic Boolean

Like Zuse when building Z3, Claude Shannon realized (a few years after Zuse) that the binary state of 0 and 1 can actually be represented with a switch. Therefore, it is possible to perform Boolean algebra practically using them.

In his master thesis, Shannon demonstrated how to use switches to implement AND and OR gates, and relay for NOT gate.

#### AND and OR Gates

A simple electrical circuit will be used, and the input is an electricity curent connected with a switch that represent 1 (closed) or 0 (open). The output will be observed, whether there is electricity (1) or no (0). 

1. AND Gate is implemented by connecting two switches in series. The output is only 1 when both inputs are 1. If one switch is open, electricity will not flow.

2. OR Gate is implemented by connecting two switches in parallel. The output is only 0 when both inputs are 0. If one switch is open, electricity can still flow from the other end.


#### NOT Gate
This version of electrical circuit will use a relay with a normally closed (NC) contact. 

3. NOT Gate is implemented by using a relay. When the input is 0, the NC contact is not changed and electricity still flow (1). When the input is 1, the NC contact opens and electricity will stop flowing (0).

### Universal and Exclusive Gates

Building upon the first three fundamental blocks, we can create other variations: NAND, NOR, XOR and XNOR. 

- NAND is NOT AND. It basically just negates the output of an AND gate.
- NOR is NOT OR. It negates the output of an OR gate.
- XOR stands for exclusive OR, it outputs 1 exclusively when only one input is 1.
- XNOR stands for exclusive NOT OR, it's the opposite of XOR. It outputs 1 exclusively when both input are of the same value.

XOR and XNOR are called exclusive gates because, well, they behave exclusively for OR and NOR.

NAND and NOR are called universal gates because they can be used to create any Boolean function. We will soon learn why this is extremely important.

