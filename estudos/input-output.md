# C - Output

- printf and scanf formats: %d, %f, %ld, %lf, %e, %c, %s, %x, %p
    - %4d     // int with 4 spaces
    - %03d    // if var == 2 print 002
    - %.2f     // 2 decimal places
    - %c        // scanf(" %c", &myChar); or fflush - (stdin)
    - %x        // pointer in hexa
    - %p         // pointer
    - %ld        // long int
    - %lf        // long float

~~~c

~~~

## Input

~~~c
/* Input string - without spaces */
char name[15];
scanf ("%s", name);    // without character '&'.
~~~