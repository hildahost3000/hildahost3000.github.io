---
title: Encoder and Decoder
---

As always, I have an easy illustration to explain what is encoder and decoder, and why do we need them. This time, an actual example will be used and it is practically possible to implement this.

Let's assume we have a simple keyboard with 10 keys: 0, 1, 2... 9. And connected to that keyboard is a seven segment display. A seven segment display is a display that is made out of 7 lines and shaped like the number 8. Each line we can control on or off, and together they can display a number we want.

In this example, the goal is press a single key and have that number displayed on seven-segment display.

### Encoder

Since there are 10 different key (0 to 9), we know that we can represent these keys by using:
- 10 digits of decimal numbers, or
- 4 digits of binary numbers

Encoder is the process that we use when we choose to use 4 digits of binary numbers to represent 10 required values. It converts multiple inputs into much more compact output.

This is the initial input on our keyboard.

| D9 | D8 | D7 | D6 | D5 | D4 | D3 | D2 | D1 | D0 | Key |
|----|----|----|----|----|----|----|----|----|----|------------|
| 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0          |
| 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1          |
| 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 2          |
| 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 0  | 3          |
| 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 4          |
| 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 0  | 5          |
| 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 0  | 6          |
| 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 7          |
| 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 0  | 8          |
| 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 9          |

When key 0 is pressed, the input is 1000000000. If key 8 is pressed, then the input is 000000010.

Yes, technically we can use this 10 digits for our process. But one thing to learn over and over again on building a computer is that everything needs to be as efficient as possible. Therefore, knowing that it is possible to represent 10 different values just by using 4 digits, that option has to be chosen.

| Key | Y3 | Y2 | Y1 | Y0 |
|---------|----|----|----|----|
| 0       | 0  | 0  | 0  | 0  |
| 1       | 0  | 0  | 0  | 1  |
| 2       | 0  | 0  | 1  | 0  |
| 3       | 0  | 0  | 1  | 1  |
| 4       | 0  | 1  | 0  | 0  |
| 5       | 0  | 1  | 0  | 1  |
| 6       | 0  | 1  | 1  | 0  |
| 7       | 0  | 1  | 1  | 1  |
| 8       | 1  | 0  | 0  | 0  |
| 9       | 1  | 0  | 0  | 1  |

Great! Now, when key 0 is pressed, instead of having to say 1000000000, it is possible just to say 0000 instead. And instead of 000000010 for key 8, it is now just 1000. Much more shorter and efficient.

This could be recreated by using just OR gates. For simplicity, let's consider a 4 to 2 encoder for starter.

| D3 | D2 | D1 | D0 | Y1 | Y0 |
|----|----|----|----|----|----|
| 0  | 0  | 0  | 1  | 0  | 0  |
| 0  | 0  | 1  | 0  | 0  | 1  |
| 0  | 1  | 0  | 0  | 1  | 0  |
| 1  | 0  | 0  | 0  | 1  | 1  |

$$
Y_0 = D_1 + D_3 \\
Y_1 = D_2 + D_3
$$

In total, this 4-to-2 encoder will require 2 OR gates. 

And back to our case of 10-to-4 encoder.

$$

\begin{align*}
Y_0 &= D_1 + D_3 + D_5 + D_7 + D_9 \\
Y_1 &= D_2 + D_3 + D_6 + D_7 \\
Y_2 &= D_4 + D_5 + D_6 + D_7 + D_8 + D_9 \\
Y_3 &= D_8 + D_9
\end{align*}
$$

With this encoder, we have succesfully simplify 10 digits long of information to just using 4 digits. This information could be passed forward to the next process.

### Decoder

Having the 4 digits in our hands, the next task is to display the key pressed on the seven segment display. As the name suggests, the seven segment display has 7 segments, meaning it has 7 different value to control.

Decoder is the opposite of encoder, in which a compact input is converted into multiple output.

In this case, the seven segment display is mapped from segment a to g.
For example, when the key 1 is pressed, to display digit "1", segment b anc c will be activated. To display digit "8", all segment from a to g will be activated. 

Here is the full table to map the key pressed, to the 4 digits after each key gets encoded (A, B, C, D) and to the 7 segment display (a, b, c, d, e, f, g)
| Key | A | B | C | D | a | b | c | d | e | f | g |
|---------|---|---|---|---|---|---|---|---|---|---|---|
| 0       | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 |
| 1       | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| 2       | 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
| 3       | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
| 4       | 0 | 1 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 5       | 0 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
| 6       | 0 | 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 | 1 |
| 7       | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| 8       | 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 9       | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 1 | 1 |

The equations for this table is going to get long, but they are not necessarily complicated. Since they are so long, we don't need to prove each equation. As long as we understand the theory, we are good to go!

$$
\begin{align*}
a = \overline{B} \cdot \overline{D} + A \cdot \overline{C} + B \cdot C \cdot \overline{D} + \overline{A} \cdot C \cdot D \\

b = \overline{A} \cdot \overline{C} \cdot \overline{D} + \overline{A} \cdot B \cdot \overline{C} + \overline{B} \cdot C \cdot D + A \cdot B \cdot \overline{C} + A \cdot \overline{B} \cdot C \\

c = \overline{A} \cdot B \cdot \overline{C} + \overline{A} \cdot \overline{B} \cdot C + B \cdot \overline{C} \cdot D + A \cdot \overline{B} \cdot C \cdot D \\

d = \overline{B} \cdot \overline{C} \cdot D + B \cdot \overline{C} \cdot \overline{D} + \overline{A} \cdot C \cdot D + A \cdot \overline{B} \cdot C

e = \overline{A} \cdot \overline{B} \cdot D + C \cdot D + A \cdot \overline{B} \cdot \overline{D} \\

f = \overline{A} \cdot \overline{B} \cdot \overline{D} + \overline{A} \cdot C \cdot D + B \cdot C \cdot \overline{D} + A \cdot \overline{C} \cdot D \\

g = \overline{A} \cdot \overline{B} \cdot C + B \cdot \overline{C} \cdot D + A \cdot B \cdot \overline{C} + A \cdot \overline{B} \cdot \overline{D} \\
\end{align*}
$$


### Wrap Up

In this section, we learned how to:
- encode 10 different keys on keyboard to 4 digits using 10-to-4 encoder
- decode 4 digits to control a seven segment display using 4-to-7 decoder