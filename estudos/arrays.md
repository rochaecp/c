# C - Arrays

- Main diagonal of the matrix:    i == j.

~~~cpp
int grades1[5];             
grades[0] = 27;             
int grades2[3] = {1, 2, 3}; 
int x[50] = {0};                         // initializes all indexes to zero
int x[5] = {10, 20, 30};         // uninitialized positions are filled with zero

float grades[2][3];                            
float grades[2][3][5];                     
char names[2][20] = {"Mauricio", "Maria"};    // ("nome = %s\n", names[0]);    -> Maurício
char y[2][2] = {'a', 'h'} , {'e', 'h'}};        // this is not a string
int x[2][3] = {1, 2, 3} , {4, 5, 6}}; 

/* Ex.: output */
int x[5][5] = {0};
for (int i = 0; i < 2; i++)
    for (int j = 0; j < 3; j++)
        printf ("%d ", x[i][j]);
~~~