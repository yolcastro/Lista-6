#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define MX 100

int *alocarMatriz(int N) {
    int *p = NULL;

    if (!(p = (int*) malloc(N * N * sizeof(int)))) {
        puts("Memória insuficiente.");
        exit(1);
    }

    return p;
}

void preencherMatriz(int *m, int N) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            m[i * N + j] = rand() % MX;
        }
    }
}

void imprimirMatriz(int *m, int N) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%3d ", m[i * N + j]);
        }
        printf("\n");
    }
}

int somaDiagonalPrincipal(int *m, int N) {
    int soma = 0;
    
    for (int i = 0; i < N; i++) {
        soma = soma + m[i * N + i];
    }
    
    return soma;
}

int main() {
    int *m;
    int N;

    srand(time(NULL));

    printf("Digite o tamanho da matriz NxN: ");
    scanf("%d", &N);

    m = alocarMatriz(N);

    preencherMatriz(m, N);

    printf("Matriz gerada:\n");
    imprimirMatriz(m, N);

    int soma = somaDiagonalPrincipal(m, N);

    if (soma % 2 == 0) {
        printf("A soma da diagonal principal é par.\n");
    }
    else {
        printf("A soma da diagonal principal é ímpar.\n");
    }

    free(m);

    return 0;
}
