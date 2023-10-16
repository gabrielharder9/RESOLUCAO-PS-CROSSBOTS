#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, k, m;                        /*declaração das variavies*/
    scanf("%d %d %d", &n, &k, &m); 
    int doces[n]; 

    for (int i = 0; i < n; i++) {    
        doces[i] = i + 1;              /*valores dentro do vetor indo de 1 a n*/
    }

    int posicaok = 0;                  /*posicao dos meninos*/
    int posicaom = n - 1;

    while (n > 0) {             /*laco principal ate que o tamanho do vetor seja 0*/ 
        posicaok = abs(posicaok + k - 1) % n;          /*calculo das posicoes*/ 
        posicaom = abs(posicaom - m + 1 + n) % n;      /*com o comando abs para evitar problemas com numeros negativos*/

        if (doces[posicaok] == doces[posicaom]) {      /*caso em que xandim ganha doce*/
            printf("%d\n", doces[posicaok]);           /*imprime apenas o doce em que se encontram*/
            for (int i = posicaok; i < n - 1; i++) {
                doces[i] = doces[i + 1];               /*retirada do doce*/
            }
            
            n--;                                       /*diminui o tamanho do vetor*/
            posicaom = abs(posicaom - 1 + n) % n;      /*calculo da nova posicao do marquim*/
        }
        else{                                          /*casos em que nao se encontram*/
            printf("%d %d\n", doces[posicaok], doces[posicaom]);     /*imprime a posicao dos meninos*/

            if (posicaok < posicaom) {                 /*caso em que a posicao de k é menor que de m*/
                for (int i = posicaok; i < n - 1; i++) {
                    doces[i] = doces[i + 1];
                }
                n--;
                posicaom = (posicaom - 1 + n) % n;

                for (int i = posicaom; i < n - 1; i++) {  /*possui dois for para retirar o numero dos dois doces pegos*/
                    doces[i] = doces[i + 1];
                }
                n--;
            }
             else{                                       /*caso em que a posicao k é maior que de m*/
                for (int i = posicaom; i < n - 1; i++) {
                    doces[i] = doces[i + 1];
                }
                n--;
                posicaok = (posicaok - 1 + n) % n;

                for (int i = posicaok; i < n - 1; i++) {
                    doces[i] = doces[i + 1];
                }
                n--;
             }
            posicaom = abs(posicaom - 1 + n) % n;
        }
    }
    return 0;                                        /*finalização do codigo*/
}