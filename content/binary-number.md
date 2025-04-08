---
title: Binary Number
---

The word binary comes from Latin root bīni, which means consisting of two, involving two.

In this case, we will use two digits, which is 0 and 1, to represent any number.

For starter, when we count in decimal, we start with one digit and we have 1, 2, 3. When we reach 9, we use a second digit to represent the next numbers: 10, 11, 12, and so on.

In binary, we start with one digit and we have 0, 1. When we reach 1, we use a second digit to represent the next numbers; 10 and 11. 

### Represent to Decimal 

To make it easier to understand it, let's establish the rule to represent any base-n number to decimal.

For decimal, there are 9 digits (0 to 9), we use base 10. It means, we can represent number by using 10 and powers of 10. 

Let's say we have 578, five hundred seventy eight. We can represent it as:

$$
\begin{aligned}
578 &= (5 \times 100) + (7 \times 10) + (8 \times 1) \\
    &= (5 \times 10^2) + (7 \times 10^1) + (8 \times 10^0)
\end{aligned}
$$


For binary, instead of 10 we use 2 because we only have 2 digits, 0 and 1. Let's say we have the number 101. We can convert it to decimal by:

$$
\begin{aligned}
101 &= (1 \times 2^2) + (0 \times 2^1) + (1 \times 2^0) \\
    &= (1 \times 4) + (0 \times 2) + (1 \times 1) \\
    &= 4 + 0 + 1 = 5
\end{aligned}
$$


### Conversion to Binary

But the problem is, our everyday numbers are in decimal, right? So we need to convert it the other way around. We can do it by doing repeated division by 2 and keeping track of the remainder.

Let's use the number 5 from our previous binary conversion. This is how we get 101:

$$
\begin{aligned}
5 \div 2 &= 2 \, \text{remainder } 1 \\
2 \div 2 &= 1 \, \text{remainder } 0 \\
1 \div 2 &= 0 \, \text{remainder } 1
\end{aligned}
$$


Reading the remainders from bottom to top, we get 101.
