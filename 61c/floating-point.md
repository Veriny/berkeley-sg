# Floating Point

## Representing Fractions

We have a binary point that signifies the boundary between the integer and fractional portion. That is, the number to the right of the decimal point represents $$2^{-1}$$, and the number to the right of the decimal number represents $$2^1$$. $$10.1010_2 = 2^1 + 2^{-1} + 2^{-3}$$ .

### Addition with a fixed point:

Same as traditional addition.

### Multiplication with a fixed point:

Same as traditional multiplication.

## Floating Binary Points

If we could just move the binary point wherever we wanted, we could store much more varied information. To do this we use a variant on scientific notation. It has a few components: given a scientific number $$a \times 2^{23}$$, $$a$$is the mantissa, $$23$$is the exponent, $$2$$is the radix, or base. In **IEEE 754 Floating Point Standard**, we dedicate one bit to the sign, 8 bits for our exponent, 23 bits for our significand.

We can use **bias notation** to represent more numbers, where the bias is a number subtracted to get the real number.

