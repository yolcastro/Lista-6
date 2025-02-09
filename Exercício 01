#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main (int argc, char *argv[]) {
    if (argc != 4) {
        printf("Use: %s <numero1> <numero2> <operacao> \n", argv[0]);
        exit(1);
    }
    
    int numero1 = atoi(argv[1]);
    int numero2 = atoi(argv[2]);
    char *operacao = argv[3];

    if (strcmp(operacao, "somar") == 0) {
        printf("Resultado: %d \n", numero1 + numero2);
    }
    else if (strcmp(operacao, "multiplicar") == 0) {
        printf("Resultado: %d \n", numero1 * numero2);
    }
    else {
        printf("Operação inválida.");
        exit(2);
    }

    return 0;
}
