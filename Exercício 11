#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int *alocarMemoria(int n) {
    int *p = NULL;
    
    if (!(p = (int*) malloc(n * sizeof(int)))) {
        puts("Memória insuficiente");
        exit(1);
    }
    
    return p;
}

void preencherVetor(int *p, int n, int N) {
    for (int k = 0; k < n; k++) {
        *(p + k) = rand() % N;
    }
}

void imprimirVetor(int *p, int n) {
    for (int k = 0; k < n; k++) {
        printf("[%p] %d\n", p + k, *(p + k));
    }
}

void preencherMatriz(int *m, int *px, int *py, int n, int N) {
    for (int k = 0; k < n; k++) {
        int x_val = px[k];
        int y_val = py[k];
        
        m[x_val * N + y_val]++;
    }
}

void imprimirMatriz(int *matriz, int N) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%3d ", matriz[i * N + j]);
        }
        printf("\n");
    }
}

int main() {
    int *px, *py, *m;
    int N, n;
    srand(time(NULL));

    printf("Digite o tamanho da matriz NxN: ");
    scanf("%d", &N);

    printf("Digite o número de elementos para os vetores 'X' e 'Y': ");
    scanf("%d", &n);

    px = alocarMemoria(n);
    py = alocarMemoria(n);
    m = alocarMemoria(N * N);

    preencherVetor(px, n, N);
    preencherVetor(py, n, N);
    preencherMatriz(m, px, py, n, N);

    printf("Vetor X:\n");
    imprimirVetor(px, n);

    printf("Vetor Y:\n");
    imprimirVetor(py, n);

    printf("Matriz de coocorrências M:\n");
    imprimirMatriz(m, N);

    free(px);
    free(py);
    free(m);

    return 0;
}
