# C - Structures 

- Tipos simples em C: char, int, float, double, ponteiros.
- Tipos estruturados em C: arranjos, estruturas, arquivos.
- typedef permite ao usuário criar tipos personalizados. Usar sempre visibilidade global para typedef.
- Ex.:: typedef unsigned int NATURAL;
- Novos tipos são declarados como globais. Dados heterogêneos.
- Obs: atribuições com estrutura: p1 = p2;
- usamos (*p).nome pois o operador Ponto tem maior precedência do que o * do Ponteiro.
- Operador seta: Para funções com parâmetro do tipo estrutura, onde ponteiros devem ser utilizados.
    - "p->nome é o mesmo que (*p).nome

~~~c
// Declaração de uma estrutura
typedef struct pessoa {
    int idade;
    char nome[60];
} PESSOA;    // nome da estrutura

// Inicializações de uma estrutura
PESSOA p1 = {25, "Maurício"};        // outra forma: struct pessoa p1 = {25, "Maurício"};     

// Acesso aos dados da estrutura
p1.idade = 25;
scanf ("%d", &p1.idade); 
scanf ("%s", p1.nome);    //string não recebe &

// Vetores de estruturas
PESSOA p[2] = {25, "Mauricio Rocha"} , {30, "Mauricio Fera"}};    
printf ("%d\n%s\n", p[0].idade, p[0].nome);

// Recebendo estrutura como parâmetro por referência - Ex.: 1
void printaPessoa (PESSOA *p) {    // chamanda printaPessoa (&p1);
    printf ("%d\n", p->idade);        // outra forma printf ("%d\n", (*p).idade);
    printf ("%s\n", p->nome);        // outra forma printf ("%s\n", (*p).nome);
}

// Recebendo estrutura como parâmetro por referência - Ex.: 2
void lePessoa (PESSOA *p) {    // chamanda printaPessoa (&p1);
    scanf ("%d", &p->idade);    // Lê-se "p seta idade" é o mesmo que scanf ("%d", &(*p).idade);
    scanf ("%s", p->nome);        // é o mesmo que scanf ("%s", (*p).nome);
}

// Estrutura dentro de estrutura
typedef struct data {
    int dia, mes, ano;
}DATA;

typedef struct pessoa {
    char nome[50];
    DATA dataNasc;
}PESSOA;

// Inicializando
PESSOA p1 = {"Mauricio", {15, 01, 1992} };
~~~

### Structures - example

~~~c
#include <stdio.h>

typedef struct pessoa {
    int idade;    
    char nome[30];    
}PESSOA;

void lePessoa (PESSOA *p) {
    scanf ("%d", &p->idade);    // Lê-se "p seta idade" é o mesmo que scanf ("%d", &(*p).idade);
    scanf ("%s", p->nome);        // é o mesmo que scanf ("%s", (*p).nome);
}

void printaPessoa (PESSOA *p) {
    printf ("%d\n", p->idade);    // outra forma printf ("%d\n", (*p).idade);
    printf ("%s\n", p->nome);    // outra forma printf ("%s\n", (*p).nome);
}

int main() {
    PESSOA p; 
    lePessoa (&p);
    printaPessoa (&p);
    return 0;
}
~~~