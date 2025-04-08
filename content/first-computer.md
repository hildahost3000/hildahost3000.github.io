---
title: First Computer
---

If we go back to the very beginning, we talked about mechanical calculator that was manual, heavy, and slow. We also talked about simplifying the base 10 system used on those calculators. By using binary system, we can represent any number just with 0 and 1, we can perform further manipulation using logical operations such as AND, OR, and NOT that we call Boolean Algebra.

At this point, these ideas belong to two different fields.
- mechanical calculator implementation is part of practical engineering
- binary system and logical operation is part of abstract mathematics

### First Binary Calculator

Enter Konrad Zuse, most likely the very first person who combined the two fields into one single working programmable binary mechanical computer slash calculator named Z1.




### First Computer
With the invention of switch and relay, enter Konrad Zuse, most likely was the very first person who combined the two fields into one single working programmable binary mechanical computer slash calculator named Z1.

Since Z1 was rather large in design, let's break it down by using Claude Shannon's famous master thesis.

### Basic Logic Gates Implementation

Like Zuse, Claude Shannon realized (a few years later) that the binary state of 0 and 1 can actually be represented with a switch. Therefore, it is possible to perform Boolean algebra practically using them.

In his master thesis, Shannon demonstrated how to use switches to implement AND and OR gates, and relay for NOT gate.

#### AND and OR Gates

A simple electrical circuit will be used, and the input is an electricity curent connected with a switch that represent 1 (closed) or 0 (open). The output will be observed, whether there is electricity (1) or no (0). 

1. AND Gate is implemented by connecting two switches in series. The output is only 1 when both inputs are 1. If one switch is open, electricity will not flow.

2. OR Gate is implemented by connecting two switches in parallel. The output is only 0 when both inputs are 0. If one switch is open, electricity can still flow from the other end.


#### NOT Gate
This version of electrical circuit will use a relay with a normally closed (NC) contact. 

3. NOT Gate is implemented by using a relay. When the input is 0, the NC contact is not changed and electricity still flow (1). When the input is 1, the NC contact opens and electricity will stop flowing (0).


### Z1

