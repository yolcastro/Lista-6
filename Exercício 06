#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define MX 100

float *alocarMemoria(int qtd) {
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

float calcularMedia(int *pv, int qtd) {
    float soma = 0;
    for (int k = 0; k < qtd; k++) {
        soma = soma + *(pv + k);
    }
    return soma / qtd;
}

float calcularMediana(int *pv, int qtd) {
    for (int i = 0; i < (qtd - 1); i++) {
        for (int j = i + 1; j < qtd; j++) {
            if (*(pv + i) > *(pv + j)) {
                int temp;
                temp = *(pv + i);
                *(pv + i) = *(pv + j);
                *(pv + j) = temp;
            }
        }
    }

    if (qtd % 2 != 0) {
        return *(pv + qtd / 2);
    }
    else {
        return (*(pv + qtd / 2 - 1) + *(pv + qtd / 2)) / 2;
    }
}

int calcularModa(int *pv, int qtd) {
    int maximo = 0;
    int moda = *(pv + 0);

    for (int i = 0; i < qtd; i++) {
        int count = 0;
        for (int j = 0; j < qtd; j++) {
            if (*(pv + i) == *(pv + j)) {
                count++;
            }
        }

        if (count > maximo) {
            maximo = count;
            moda = *(pv + i);
        }
    }

    return moda;
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

    int *pv = alocarMemoria(quantidade);

    preencherVetor(pv, quantidade);
    imprimirVetor(pv, quantidade);

    float media = calcularMedia(pv, quantidade);
    float mediana = calcularMediana(pv, quantidade);
    int moda = calcularModa(pv, quantidade);

    printf("Média: %.2f\n", media);
    printf("Mediana: %.2f\n", mediana);
    printf("Moda: %d\n", moda);

    free(pv);

    return 0;
}
