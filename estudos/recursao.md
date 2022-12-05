# C - Recursion

- Técnica de programação, na qual um subprograma (função) chama a si mesmo.
- Importante: todas as funções recursivas devem encerrar a recursão a partir de um teste de valor ou condição!
- sempre pode ser substituído por programação com commands iterativos
- Vantagens da Recursividade
    - código mais compacto;
    - especialmente conveniente para estruturas de dados definidas recursivamente, tais como árvores;
    - código pode ser mais fácil de entender.
    - implementação mais imediata de funções matemáticas que já são definidas recursivamente.
- Desvantagens da Recursividade
    - maior ocupação de memória;
    - maior tempo de processamento

~~~c
// Fatorial sem recursão
int fatorial (int n)
{ 
    int fat = 1, i;
    for (i = n; i > 1; i--)
        fat = fat * i;
    return fat;
}

// Fatorial com recursão
// Regra de recursão: se n=0 fat=1,    se n>0 fat de n=    n * (fat de n-1)
int fatorial (int n)
{ 
    int fat = 1;
    if (n == 0)
        fat = 1;
    else
        fat = n * fatorial (n - 1);
    return fat;
}

// Sequencia de Fibonacci com recursão 
unsigned int fib_rec (unsigned int n)
{ 
    if (n < 2)
        return n;
    else 
        return    (fib_rec (n - 1) + fib_rec (n - 2);
}

// Função recursiva se passar num=0 imprime 4 3 2 1 0
void recursive (int num)
{    
    if (num < 5)
    {
        recursive (num + 1);
        printf ("%d ", num);        
    }
}
~~~