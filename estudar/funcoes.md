# C - Functions

- A function must perform a single task.
- Prototypes must be before the main function or in the header.

~~~c
void myFunc () {
    printf ("Hello World\n");
}
~~~

### Function Parameters

- Formal parameters.
- Actual function parameters.
- Parameters by reference

~~~c
/* Ex.: */
int mySum (int a, int b) {
    int result;
    result = a + b;
    return result; 
}

/* Ex.: */
void uppercase (char c) {
    printf ("%c", c - 32);
}

/* Ex.: Parameters by reference */
void mySwap (int *x, int *y) {    // call mySwap (&a, &b);
    int temp;
    temp = *x;
    *x = *y;
    *y = temp; 
} 
~~~

### Function Overloading

~~~c

~~~