#include <stdio.h>
#include <string.h> // Necessário para as funções strcpy e strcmp

// Estrutura para representar uma carta de cidade
typedef struct {
    char nome[50];
    char codigo[10];
    long long populacao;
    double area;
    double pib;
    int num_pontos_turisticos;
} CartaCidade;

int main() {
    // --- Criando um "baralho" com as cartas ---
    CartaCidade baralho[2]; // Um array para 2 cartas (neste exemplo)

    // Carta 0: Rio de Janeiro
    strcpy(baralho[0].nome, "Rio de Janeiro");
    strcpy(baralho[0].codigo, "a01");
    baralho[0].populacao = 6748000;
    baralho[0].area = 1200.27;
    baralho[0].pib = 380.00; // PIB em bilhões de reais
    baralho[0].num_pontos_turisticos = 58;

    // Carta 1: Sao Paulo
    strcpy(baralho[1].nome, "Sao Paulo");
    strcpy(baralho[1].codigo, "a02");
    baralho[1].populacao = 11452000;
    baralho[1].area = 1521.00;
    baralho[1].pib = 3500.00; // PIB em bilhões de reais
    baralho[1].num_pontos_turisticos = 50;

    // Variáveis para as cartas escolhidas pelo usuário
    CartaCidade carta_jogador1;
    CartaCidade carta_jogador2;
    int carta1_encontrada = 0;
    int carta2_encontrada = 0;
    char codigo_escolhido1[10];
    char codigo_escolhido2[10];

    // --- Exibindo as opções de cartas ---
    printf("Cartas disponiveis para escolha:\n");
    for (int i = 0; i < 2; i++) {
        printf("- %s (Codigo: %s)\n", baralho[i].nome, baralho[i].codigo);
    }
    printf("\n");

    // --- Escolha da primeira carta ---
    do {
        printf("Jogador 1, digite o codigo da sua carta: ");
        scanf("%s", codigo_escolhido1);

        for (int i = 0; i < 2; i++) {
            if (strcmp(codigo_escolhido1, baralho[i].codigo) == 0) {
                carta_jogador1 = baralho[i]; // Copia a carta para o jogador 1
                carta1_encontrada = 1;
                break; // Sai do loop, a carta foi encontrada
            }
        }
        if (!carta1_encontrada) {
            printf("Codigo de carta invalido. Tente novamente.\n");
        }
    } while (!carta1_encontrada);

    // --- Exibindo informacoes da carta escolhida pelo Jogador 1 ---
    printf("\nVoce escolheu: %s\n", carta_jogador1.nome);
    printf("Populacao: %lld habitantes\n", carta_jogador1.populacao);
    printf("Area: %.2f km2\n", carta_jogador1.area);
    printf("PIB: R$ %.2f bilhoes\n", carta_jogador1.pib);
    printf("Pontos Turisticos: %d\n", carta_jogador1.num_pontos_turisticos);
    printf("\n");

    // --- Escolha da segunda carta (diferente da primeira) ---
    do {
        printf("Jogador 2, digite o codigo da sua carta (diferente da primeira): ");
        scanf("%s", codigo_escolhido2);

        // Verifica se é diferente da primeira carta escolhida
        if (strcmp(codigo_escolhido2, codigo_escolhido1) == 0) {
            printf("Essa carta ja foi escolhida pelo Jogador 1. Escolha outra.\n");
            continue; // Volta para o inicio do loop
        }

        for (int i = 0; i < 2; i++) {
            if (strcmp(codigo_escolhido2, baralho[i].codigo) == 0) {
                carta_jogador2 = baralho[i]; // Copia a carta para o jogador 2
                carta2_encontrada = 1;
                break; // Sai do loop, a carta foi encontrada
            }
            // Não é necessário um 'else' aqui, pois o 'if' e 'break' cuidam do sucesso.
        }
        if (!carta2_encontrada) {
            printf("Codigo de carta invalido. Tente novamente.\n");
        }
    } while (!carta2_encontrada);

    // --- Exibindo informacoes da carta escolhida pelo Jogador 2 ---
    printf("\nO oponente escolheu: %s\n", carta_jogador2.nome);
    printf("Populacao: %lld habitantes\n", carta_jogador2.populacao);
    printf("Area: %.2f km2\n", carta_jogador2.area);
    printf("PIB: R$ %.2f bilhoes\n", carta_jogador2.pib);
    printf("Pontos Turisticos: %d\n", carta_jogador2.num_pontos_turisticos);
    printf("\n");

    // --- Escolha do Atributo de Comparação ---
    int escolha;
    printf("Escolha o atributo para comparar:\n");
    printf("1. Populacao\n");
    printf("2. Area\n");
    printf("3. PIB\n");
    printf("4. Numero de pontos turisticos\n");
    printf("5. Densidade Populacional (MENOR valor vence!)\n"); // Nova opção e regra
    printf("Digite o numero da sua escolha: ");
    scanf("%d", &escolha);

    // --- Comparação de Cartas e Exibição dos Resultados ---
    printf("\n--- Comparacao de Cartas ---\n");
    printf("Carta do Jogador 1: %s\n", carta_jogador1.nome);
    printf("Carta do Jogador 2: %s\n", carta_jogador2.nome);
    printf("----------------------------\n");

    switch (escolha) {
        case 1: // Populacao (maior vence)
            printf("Atributo escolhido: Populacao\n");
            printf("%s: %lld habitantes\n", carta_jogador1.nome, carta_jogador1.populacao);
            printf("%s: %lld habitantes\n", carta_jogador2.nome, carta_jogador2.populacao);

            if (carta_jogador1.populacao > carta_jogador2.populacao) {
                printf("Vencedor: %s (Maior Populacao)\n", carta_jogador1.nome);
            } else if (carta_jogador2.populacao > carta_jogador1.populacao) {
                printf("Vencedor: %s (Maior Populacao)\n", carta_jogador2.nome);
            } else {
                printf("Empate em Populacao!\n");
            }
            break;

        case 2: // Area (maior vence)
            printf("Atributo escolhido: Area\n");
            printf("%s: %.2f km2\n", carta_jogador1.nome, carta_jogador1.area);
            printf("%s: %.2f km2\n", carta_jogador2.nome, carta_jogador2.area);

            if (carta_jogador1.area > carta_jogador2.area) {
                printf("Vencedor: %s (Maior Area)\n", carta_jogador1.nome);
            } else if (carta_jogador2.area > carta_jogador1.area) {
                printf("Vencedor: %s (Maior Area)\n", carta_jogador2.nome);
            } else {
                printf("Empate em Area!\n");
            }
            break;

        case 3: // PIB (maior vence)
            printf("Atributo escolhido: PIB (em bilhoes de reais)\n");
            printf("%s: R$ %.2f bilhoes\n", carta_jogador1.nome, carta_jogador1.pib);
            printf("%s: R$ %.2f bilhoes\n", carta_jogador2.nome, carta_jogador2.pib);

            if (carta_jogador1.pib > carta_jogador2.pib) {
                printf("Vencedor: %s (Maior PIB)\n", carta_jogador1.nome);
            } else if (carta_jogador2.pib > carta_jogador1.pib) {
                printf("Vencedor: %s (Maior PIB)\n", carta_jogador2.nome);
            } else {
                printf("Empate em PIB!\n");
            }
            break;

        case 4: // Numero de pontos turisticos (maior vence)
            printf("Atributo escolhido: Numero de pontos turisticos\n");
            printf("%s: %d pontos\n", carta_jogador1.nome, carta_jogador1.num_pontos_turisticos);
            printf("%s: %d pontos\n", carta_jogador2.nome, carta_jogador2.num_pontos_turisticos);

            if (carta_jogador1.num_pontos_turisticos > carta_jogador2.num_pontos_turisticos) {
                printf("Vencedor: %s (Mais pontos turisticos)\n", carta_jogador1.nome);
            } else if (carta_jogador2.num_pontos_turisticos > carta_jogador1.num_pontos_turisticos) {
                printf("Vencedor: %s (Mais pontos turisticos)\n", carta_jogador2.nome);
            } else {
                printf("Empate em pontos turisticos!\n");
            }
            break;

        case 5: // Densidade Populacional (MENOR valor vence!)
            printf("Atributo escolhido: Densidade Populacional\n");
            // Calcula a densidade populacional para cada carta
            // Importante fazer o cast para double para garantir divisão com ponto flutuante
            double densidade1 = (double)carta_jogador1.populacao / carta_jogador1.area;
            double densidade2 = (double)carta_jogador2.populacao / carta_jogador2.area;

            printf("%s: %.2f hab/km2\n", carta_jogador1.nome, densidade1);
            printf("%s: %.2f hab/km2\n", carta_jogador2.nome, densidade2);

            // Regra especial: o MENOR valor de densidade vence
            if (densidade1 < densidade2) {
                printf("Vencedor: %s (Menor Densidade Populacional)\n", carta_jogador1.nome);
            } else if (densidade2 < densidade1) {
                printf("Vencedor: %s (Menor Densidade Populacional)\n", carta_jogador2.nome);
            } else {
                printf("Empate em Densidade Populacional!\n");
            }
            break;

        default:
            printf("Escolha invalida. Por favor, selecione 1, 2, 3, 4 ou 5.\n");
            break;
    }

    return 0;
}