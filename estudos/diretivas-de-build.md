# C - Build directives 

~~~c
//São commands que não são compilados. 
//São dirigidos ao pré-processador, executado pelo compilador antes da execução do processo de compilação propriamente dito. Veja mais em https://pt.wikibooks.org/wiki/Programar_em_C/Pr%C3%A9-processador
//São elas

#include<>
#define
    //#define nome_do_símbolo
    //#define nome_da_constante valor_da_constante
    //#define nome_da_macro(parâmetros) expressão_de_substituição

    //Ex.: de macro
    //#define max(A, B) ((A > B) ? (A) : (B))
    //#define min(A, B) ((A < B) ? (A) : (B))
    //...
    //x = max(i, j);
    //y = min(t, r);
#undef

#ifdef
    //O código entre as duas diretivas só será compilado se o símbolo (ou constante) nome_do_símbolo já tiver sido definido

#ifndef
/*Um uso muito comum das diretivas de compilação é em arquivos-cabeçalho, que só precisam/devem ser incluídos uma vez. Muitas vezes incluímos indiretamente um arquivo várias vezes, pois muitos cabeçalhos dependem de outros cabeçalhos. Para evitar problemas, costuma-se envolver o arquivo inteiro com um bloco condicional que só será compilado se o arquivo já não tiver incluído. Para isso usamos um símbolo baseado no nome do arquivo. Por Ex.:, se nosso arquivo se chama "cabecalho.h", é comum usar um símbolo com o nome CABECALHO_H

#ifndef CABECALHO_H
#define CABECALHO_H
.
.
.
#endif

Se o arquivo ainda não tiver sido incluído, ao chegar na primeira linha do arquivo, o pré-processador não encontrará o símbolo CABECALHO_H, e continuará a ler o arquivo, o que lhe fará definir o símbolo. Se tentarmos incluir novamente o arquivo, o pré-processador pulará todo o conteúdo pois o símbolo já foi definido. */

#if
#else
#elif
#endif

~~~