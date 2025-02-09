#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define MX 100

int *alocarMemoria(int qtd) {
    int *p = NULL;

    if (!(p = (int*) malloc(qtd * sizeof(int)))) {
        puts("Memória insuficiente");
        exit(1);
    }

    return p;
}

void preencherVetor(int *pv, int qtd) {
    for (int k = 0; k < qtd; k++) {
        *(pv + k) = rand() % MX;
    }
}

void imprimirVetor(int *pv, int qtd) {
    for (int k = 0; k < qtd; k++) {
        printf("[%p] %d\n", pv + k, *(pv + k));
    }
}

void maiorMenor(int *pv, int qtd, int *maior, int *menor) {
    *maior = pv[0];
    *menor = pv[0];

    for (int k = 1; k < qtd; k++) {
        if (pv[k] > *maior) {
            *maior = pv[k];
        }
        if (pv[k] < *menor) {
            *menor = pv[k];
        }
    }
}

int main (int argc, char *argv[]) {
    if (argc!=2) {
        printf("Use: %s <quantidade> \n",argv[0]);
        exit(1);
    }

    srand(time(NULL));

    int quantidade = atoi(argv[1]);
    
    if (quantidade <= 0) {
        printf("Valor precisa ser maior que zero.\n");
        exit(2);
    }

    int *pv;

    pv = alocarMemoria(quantidade);
    preencherVetor(pv, quantidade);
    imprimirVetor(pv, quantidade);

    int maior, menor;
    maiorMenor(pv, quantidade, &maior, &menor);
    
    printf("Endereço do maior: [%p]\n", maior);
    printf("Endereço do menor: [%p]\n", menor);
    
    free(pv);
    
    return 0;
}
