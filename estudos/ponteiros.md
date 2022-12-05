# C - Pointers

- Ponteiros são variáveis que apontam para uma posição na memória.
- Um ponteiro contém o endereço da posição de memória.
- O asterisco indica que a variável armazena um endereço de memória, cujo conteúdo é do tipo especificado.
- '*' é um operador unário que devolve o valor da variável localizada no endereço que o segue.
- '&' é um operador unário que devolve o endereço de memória de seu operando.
- Se uma variável 'a' armazena o endereço de uma variável 'b', dizemos que 'a' aponta para 'b'.
- O endereço de uma variável é sempre o MENOR dos endereços de seus bytes, isto é, o endereço inicial.

- Alguns exemplos:
- **&p é o mesmo que *p

- Aritmética de Ponteiros:
- Ao serem incrementados, os ponteiros passam a apontar para a posição de memória do próximo elemento do seu tipo base.
- O quanto o valor do ponteiro irá aumentar ou diminuir depende do número de bytes que o tipo base ocupa.
- Quando um ponteiro é declarado o compilador aloca um ponteiro para apontar para a memória, sem que espaço seja reservado.

- Ponteiros e Vetores:
- Há uma estreita relação entre ponteiros e vetores.
- Vetores são SEMPRE passados por referência, pois são ponteiros que apontam para o primeiro elemento do vetor.
- O nome de um vetor é um ponteiro que aponta para a primeira posição do vetor.

 - *v é a mesma coisa que v[0]
 - v é a mesma coisa que &v[0]" // somente se v é um ponteiro
 - * (v + 1) é a mesma coisa que v[1]
 - * (v + i) é a mesma coisa que v[i]
 - v + i é a mesma coisa que &v[i]
 - **v é a mesma coisa que v[][]
 - * (*(v + i) + j) é a mesma coisa que v[i][j]

~~~c
// Ex.:
int *a, *b, *c;            // declaraçã de ponteiro
c = NULL;                 // faz com que ponteiro não aponte para lixo.
a = &b;                     // 'a' aponta para 'b' ('a' recebe o endereço de 'b')
c = a;                    // 'c' recebe 'a' e também passa a apontar para 'b'
a = *b;                 // 'a' recebe o conteúdo apontado por 'b' (a recebe o valor que está no endereço b)
printf ("%p\n", a);    // imprime o endereço contido no ponteiro 'a'

// Ex.:
int *a, b;
b = 10;
a = &b;
*a = 20;
printf("%d\n", b);    // imprime 20

//Ex.: aritmética de ponteiros
int *a, b;
a = &b;
printf ("%p\n", a);    // imprime o endereço de 'a'
a++;                    // aritmética de ponteiros, incrementa 'a' em 4 (tamanho do int na minha arquitetura)
printf ("%p\n", a);    // imprime endereço de 'a' (incrementado em 4 unidades)

// Ex.: prototipo de função que recebe matriz como parâmetro por referência
void somaUm (int matriz[], int tam );    // Ex.: de chamada: somaUm (minhaMatriz, tamanho);

// Ex.: prototipo de função que recebe string como parâmetro por referência: protótipo de função que recebe uma string por referência como parâmetro, o tamanho pode ser obtido com a função strlen (namestring)
void trocaEspaco (char nome[]);    // Ex.: de chamada: trocaEspaco (namestring);        

// Ex.: vetores e ponteiros
char nome[9] = "Mauricio";
printf ("%c\n", *nome);            // printa M
printf ("%c\n", * (nome + 1);    // printa a

// Ex.: matriz e ponteiros 
int mat[2][3] = {15, 25, 35}, {10, 20, 30}};
printf ("%d ", * (* (mat + 0) + 0);     //imprime 15
printf ("%d ", * (* (mat + 0) + 1);     //imprime 25
printf ("%d ", * (* (mat + 1) + 2);     //imprime 30

// função que troca os valores de x e y
void troca (int *x, int *y) {// chamar a função: troca(&a, &b); 
    int temp;
    temp = *x;
    *x = *y;
    *y = temp;    
} 

// função que soma 1 em todos os valores de uma matriz
void somaUm (int matriz[], int tam ) {    // chamar a função: somaUm (nomeMatriz, tamanho)
    int i;
    for (i = 0; i < tam; i++)
        matriz[i] += 1;
}

// função que troca os espaços de uma string por asteríscos
void trocaEspaco (char nome[]) {        // chamar a função: trocaEspaco (namestring);
    int i, tam;    
    tam = strlen (nome);
    for (i = 0; i < tam; i++)
        if (nome[i] == ' ')
            nome[i] = '*';
}
~~~

#### Ex.: pointers

~~~c
// programa com Ex.:s matrizes usando ponteiros

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define LINHAS    3
#define COLUNAS 4

void imprime (int v[][COLUNAS]) {

    int i,j;

    // Imprime arranjo jeito 1
    for (i = 0; i <    (LINHAS*COLUNAS); i++)
         printf ("i= %d ", * (*v + i);

    printf ("\n\n");

    // Imprime arranjo jeito 2
    for    (i = 0; i <    (LINHAS); i++)
        for    (j = 0; j <    (COLUNAS); j++)
             printf ("i= %d ", * (* (v + i) + j);

    printf("\n\n");
}

void imprimeP (int *v) {
     int i,j;

     // Imprime arranjo
     for    (i = 0; i <    (LINHAS * COLUNAS); i++)
                printf("i= %d ", * (v + i);

     printf("\n\n");

}

int main() {
    int v[LINHAS][COLUNAS] = {1, 2, 3, 4}, {5, 6, 7, 8 }, {9, 10, 11, 12}};
    int i=1, j=0;
    
    printf ("%d \n%d \n", * (*(v + i) +j), v[i][j]);

    return 0;
}
~~~