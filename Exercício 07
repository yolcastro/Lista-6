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
    for (int i = 0; i < qtd; i++) {
        *(pv + i) = rand() % MX;
    }
}

float calcularEmq(float *A, float *B, int qtd) {
    float emq = 0;
    for (int i = 0; i < qtd; i++) {
        emq += (A[i] - B[i]) * (A[i] - B[i]);
    }
    return emq / qtd;
}

int main(int argc, char *argv[]) {
    if (argc != 2) {
        printf("Uso: %s <quantidade>\n", argv[0]);
        exit(1);
    }

    srand(time(NULL));
    
    int quantidade;
    quantidade = atoi(argv[1]);

    if (quantidade <= 0) {
        printf("Valor precisa ser maior que zero.\n");
        exit(2);
    }

    float *A;
    float *B;
    
    A = alocarMemoria(quantidade);
    B = alocarMemoria(quantidade);

    preencherVetor(A, quantidade);
    preencherVetor(B, quantidade);

    float erro;
    erro = calcularEmq(A, B, quantidade);

    printf("Erro médio quadrático entre 'A' e 'B': %.2f\n", erro);

    free(A);
    free(B);

    return 0;
}
