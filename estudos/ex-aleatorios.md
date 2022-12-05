# C - How To: Random numbers

~~~c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main() {
    int dice;
    srand (time (NULL);        
    dice = rand() % 6 + 1;    
    printf ("Dice face = %d\n", dice);
    return 0;
}
~~~