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

We can also branch unconditionally, using `j`. You can also use `Exit` to leave a block.

