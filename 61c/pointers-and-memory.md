# Pointers and Memory

## Memory

Memory in C is split up into the stack memory \(things that are not manually allocated, data becomes garbage after the function which used it returns\), the heap memory, \(things that you manually allocate with `malloc` , `calloc`, or `realloc`\). 

Allocated memory always holds garbage until it is initialized.                  

## Pointers

C uses pointers to memory explicitly. Here is an example:

```c
int x = 2;
int *p = &x;
```

Just like in Java, line 1 stores the two in a box in memory. However, p is a pointer, and its value is an address to an int. In order to recover that int, we **dereference the pointer,** using `*p`.

