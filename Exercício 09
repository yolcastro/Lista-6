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

float *alocarMatrizFloat(int N) {
    float *p = NULL;

    if (!(p = (float*) malloc(N * N * sizeof(float)))) {
        puts("Memória insuficiente");
        exit(1);
    }

    return p;
}

void preencherMatriz(float *m, int N, int mx) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            m[i * N + j] = rand() % MX;
        }
    }
}

void binarizarMatriz(float *m, int *s, int N, float t) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            if (m[i * N + j] > t) {
                s[i * N + j] = 1;
            }
            else {
                s[i * N + j] = 0;
            }
        }
    }
}

void imprimirMatriz(float *m, int N) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%.2f ", m[i * N + j]);
        }
        printf("\n");
    }
}

void imprimirMatrizBinaria(int *m, int N) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", m[i * N + j]);
        }
        printf("\n");
    }
}

int main() {
    float *m;
    int *s;
    int N;
    float limiar;

    srand(time(NULL));

    printf("Digite o tamanho da matriz NxN: ");
    scanf("%d", &N);

    printf("Digite o valor do limiar (t): ");
    scanf("%f", &limiar);

    m = alocarMatrizFloat(N);
    s = alocarMatriz(N);

    preencherMatriz(m, N, MX);

    printf("Matriz com valores aleatórios:\n");
    imprimirMatriz(m, N);

    binarizarMatriz(m, s, N, limiar);

    printf("Matriz binária:\n");
    imprimirMatrizBinaria(s, N);

    free(m);
    free(s);

    return 0;
}
