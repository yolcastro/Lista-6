#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <math.h>

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
    for (int i = 0; i < qtd; i++) {
        *(pv + i) = rand() % MX;
    }
}

float calcularMSE(float *A, float *B, int qtd) {
    float mse = 0;

    for (int i = 0; i < qtd; i++) {
        mse += (A[i] - B[i]) * (A[i] - B[i]);
    }

    return mse / qtd;
}

float calcularMAE(float *A, float *B, int qtd) {
    float mae = 0;

    for (int i = 0; i < qtd; i++) {
        mae += fabs(A[i] - B[i]);
    }
    
    return mae / qtd;
}

float calcularErro(float *A, float *B, int qtd, float (*erro)(float*, float*, int)) {
    return erro(A, B, qtd);
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

    float *A = alocarMemoria(quantidade);
    float *B = alocarMemoria(quantidade);

    preencherVetor(A, quantidade);
    preencherVetor(B, quantidade);

    float mse = calcularErro(A, B, quantidade, calcularMSE);
    printf("Erro médio quadrático (MSE): %.2f\n", mse);

    float mae = calcularErro(A, B, quantidade, calcularMAE);
    printf("Erro absoluto médio (MAE): %.2f\n", mae);

    free(A);
    free(B);

    return 0;
}
