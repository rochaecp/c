# C - How To: Argc and Argv parameters

- Argc is an int
- Argv is a pointer: **argv
- Arg 0 == nameBin, Arg 1 == arg1, ...
- Call: ./nameBin arg1 arg2 arg3

~~~c
#include <stdio.h>
int main (int argc, char *argv[]) {
    int i;
    for (i = 0; i < argc; i++)
        printf ("Parameter %d = %s\n", i, argv[ i ]); 
    return 0;
}
~~~