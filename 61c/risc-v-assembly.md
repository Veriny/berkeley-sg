# RISC-V, Assembly

## Registers

High-level languages like C, Java, and C++ use **variables**, but assembly languages cannot use variables. Instead, assembly uses **registers,** special locations directly built into the hardware that operations are done on. They're really fast compared to variables.

If a processor runs at 4.0 GHz, that means that every quarter of a nanosecond, it can access a register! 

**RISC-V has 32 registers, each 32 bits wide \(words\).**

These registers are numbered from `x0` to `x31`. `x0` is special and cannot be changed from 0, so only 31 registers can actually hold values. 

{% hint style="danger" %}
Registers have no type.  Operations treat register content as they wish.
{% endhint %}

## Addition and Subtraction

A RISC-V implementation of adding numbers looks like this:

```text
add x1, x2, x3
```

where the first thing, `add,` is the operation, followed by operands — the register for the result to be stored in, the and the two registers to be added. Note: you can add/subtract an integer to itself, i.e. `add x1, x1, x2`. 

In order to add raw integer values, use `addi` — somehing like `addi x3, x4, 10.` 

## Load and Store to Memory

{% hint style="info" %}
RISC-V is little-endian, meaning that when bytes are stored in memory,  meanign that the least-significant byte in a word gets the smallest address inside that word. **Remember, endianness is the order in which BYTES ARE STORED IN MEMORY.**
{% endhint %}

In RISC-V, load words are used to load memory into registers. 

```text
lw x10, 12(x15)
```

Supposing `x15` is an integer array, this loads the 3rd element of the array into the register `x10`.

To store from the register to the memory, use the store word.

```text
lw x10, 12(x15) # store A[3] in x10
add x10, x12, x10 #add x12 + a[3]
sw x10, 40(x15) # store x10 in A[10] in memory
```

 We can load and store individual bytes using `lb` and `sb`.

## Conditionals

The _if-_statement instruction is `beq reg1, reg2, L1` — this stands for branch if equal — go to statement `L1` if the two register values are equal. In contrast, `bne` is used for branch not equal.

### Branches

A branch is a change in control flow. Conditional branches are as described before. There are also less than or equal to,  `blt` and `bge` respectively. There are also unsigned versions, `bltu` and `bgeu`.

We can also branch unconditionally, using `j`. 

Labels are blocks of RISC-V code that can be jumped to with `j.`

## Logical Operators

`and`, `or`, `xor,` `sll, srl` represent the logical operators of RISC-V. As usual, there are always two variants, register versions and immediate versions.

Note that there is no `not` operator — simply `xor` with 11111111 will work.

### Logical Shifting:

For shifting left, shift the bits to the left, they fall of the end, and we insert zeroes on the right.

### Arithmetic Shifting

For shifting to the right, move n bits to the rightr and insert higher order sign bit into empty bits.

## Functions

There are a few steps to calling a function in RISC-V.

* Put the arguments in a palce where the function can access them. 
* Transfer control to the function
* Allocate storage and resourcesn needed for the function
* Perform the functions task
* Store teh returne value, rekease local storage \(stack\), and restore any registers used.

We want ton use registers because registers are faster than memory. We have

* `a0-a7` eight argument registers used to pass parameters and two return values `a0-a1`.
* `ra` is the return address register to return the the point of the origin.
* `s0-s1` and `s2-s11` — saved registers

Functions are invoked using `jal` and functions are returned using `jr.` 

### Caller v.s. Callee

When the callee returns, it needs to know which registers are still safe. Saved registers are saved in `s0 - s11`, and temporary registers `a0-a7, ra, t0-t6` are not preserved across function calls.

## Allocating Space on Stack

Before the call, our stack pointer is at some location. During our call, our stack pointer moves downwards, creating space, if needed for the return address, the argument registers, saved registers, and local variables.

{% hint style="info" %}
In the case that your stack pointer moves, it is better use the frame pointer as a point of reference.
{% endhint %}

