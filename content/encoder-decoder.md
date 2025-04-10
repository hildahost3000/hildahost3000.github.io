---
title: Encoder and Decoder
---

As always, I have an easy illustration to explain what is encoder and decoder, and why do we need them. This time, an actual example will be used and it is practically possible to implement this.

Let's assume we have a simple keyboard with number 0, 1, 2... 9. And connected to that keyboard is a seven segment display. A seven segment display is a display that is made out of 7 lines and shaped like the number 8. Each line we can control on or off, and together they can display a number we want.

In this example, the goal is press a single number and have that number displayed on seven-segment display.

### Encoder

Since there are 10 different digits (0 to 9), we know that we can represent these number by using:
- 10 digits of decimal numbers, or
- 4 digits of binary numbers

Encoder is the process that we use when we choose to use 4 digits of binary numbers to represent 10 available digits. It converts multiple inputs into much more compact output.

This is the initial input on our keyboard.

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

When we press a number, that number is active as input.

Yes, we can use this 10 digits long as input. But one thing we will learn over and over again on building a computer is that we need everything to be as efficient as possible.

