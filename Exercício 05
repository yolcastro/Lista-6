#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define MX 100

float *alocarMemoria(int qtd) {
    float *p = NULL;

    if (!(p = (float*) malloc(qtd * sizeof(float)))) {
        puts("Memória insuficiente");
        exit(1);
    }

    return p;
}

void preencherVetor(float *pv, int qtd) {
    for (int k = 0; k < qtd; k++) {
        *(pv + k) = rand() % MX;
    }
}

void imprimirVetor(float *pv, int qtd) {
    for (int k = 0; k < qtd; k++) {
        printf("[%p] %.2f\n", pv + k, *(pv + k));
    }
}

float somarElementos(float *pv, int qtd) {
    float soma = 0;
    for (int k = 0; k < qtd; k++) {
        soma = soma + *(pv + k);
    }
    return soma;
}

int main(int argc, char *argv[]) {
    if (argc != 2) {
        printf("Uso: %s <quantidade>\n", argv[0]);
        exit(1);
    }

    srand(time(NULL));

    int quantidade = atoi(argv[1]);

    if (quantidade <= 0) {
        printf("Valor precisa ser maior que zero.\n");
        exit(2);
    }

    float *pv = alocarMemoria(quantidade);

    preencherVetor(pv, quantidade);
    imprimirVetor(pv, quantidade);

    float soma = somarElementos(pv, quantidade);
    printf("Soma dos elementos: %.2f\n", soma);

    free(pv);

    return 0;
}
