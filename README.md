#include <stdio.h>

int main() {
    // Variáveis
    unsigned long int Populacao1, Populacao2;
    float Area1, Area2;
    float PIB1, PIB2;
    int Pontos1, Pontos2;

    float Densidade1, Densidade2;
    float PIB_per_Capita1, PIB_per_Capita2;
    float SuperPoder1, SuperPoder2;

    char Cidade1[100], Cidade2[100];

    // Introdução
    printf("Cadastro de cartas do Super Trunfo\n\n");

    // Exemplo (sem entrada)
    printf("Exemplo de carta:\n");
    printf("Estado: A\n");
    printf("Codigo da carta: A01 \n");
    printf("Nome da cidade: Toritama\n");
    printf("Populacao: 75000\n");
    printf("Area: 1452.11 km²\n");
    printf("PIB: R$ 699.28 bilhões\n");
    printf("Numero de pontos turisticos: 10\n\n");

    // Entrada de dados - Carta 1
    printf("Digite os dados da Carta 1:\n");
    printf("Nome da cidade: ");
    scanf(" %[^\n]", Cidade1);
    printf("Populacao: ");
    scanf("%lu", &Populacao1);
    printf("Area (km²): ");
    scanf("%f", &Area1);
    printf("PIB (em bilhões): ");
    scanf("%f", &PIB1);
    printf("Numero de pontos turisticos: ");
    scanf("%d", &Pontos1);

    // Entrada de dados - Carta 2
    printf("\nDigite os dados da Carta 2:\n");
    printf("Nome da cidade: ");
    scanf(" %[^\n]", Cidade2);
    printf("Populacao: ");
    scanf("%lu", &Populacao2);
    printf("Area (km²): ");
    scanf("%f", &Area2);
    printf("PIB (em bilhões): ");
    scanf("%f", &PIB2);
    printf("Numero de pontos turisticos: ");
    scanf("%d", &Pontos2);

    // Validação básica
    if (Area1 <= 0 || Area2 <= 0 || Populacao1 == 0 || Populacao2 == 0) {
        printf("\nErro: área e população devem ser maiores que zero.\n");
        return 1;
    }

    // Cálculos
    Densidade1 = Populacao1 / Area1;
    PIB_per_Capita1 = (PIB1 * 1e9) / Populacao1;
    SuperPoder1 = Populacao1 + Area1 + PIB1 + Pontos1 + PIB_per_Capita1 + (1.0 / Densidade1);

    Densidade2 = Populacao2 / Area2;
    PIB_per_Capita2 = (PIB2 * 1e9) / Populacao2;
    SuperPoder2 = Populacao2 + Area2 + PIB2 + Pontos2 + PIB_per_Capita2 + (1.0 / Densidade2);

    // Exibição dos cálculos
    printf("\n--- Resultados ---\n");
    printf("Densidade Populacional (%s): %.2f\n", Cidade1, Densidade1);
    printf("PIB per Capita (%s): %.2f\n", Cidade1, PIB_per_Capita1);
    printf("Super Poder (%s): %.2f\n\n", Cidade1, SuperPoder1);

    printf("Densidade Populacional (%s): %.2f\n", Cidade2, Densidade2);
    printf("PIB per Capita (%s): %.2f\n", Cidade2, PIB_per_Capita2);
    printf("Super Poder (%s): %.2f\n\n", Cidade2, SuperPoder2);

    // Menu Interativo
    int opcao;
    printf("Escolha o atributo para comparar:\n");
    printf("1 - População\n");
    printf("2 - Área\n");
    printf("3 - PIB\n");
    printf("4 - Número de pontos turísticos\n");
    printf("5 - Densidade demográfica\n");
    printf("Digite a opção desejada (1-5): ");
    scanf("%d", &opcao);

    printf("\n--- Comparação ---\n");

    switch (opcao) {
        case 1:
            printf("Atributo: População\n");
            printf("%s: %lu habitantes\n", Cidade1, Populacao1);
            printf("%s: %lu habitantes\n", Cidade2, Populacao2);
            if (Populacao1 > Populacao2) {
                printf("Resultado: %s venceu!\n", Cidade1);
            } else if (Populacao2 > Populacao1) {
                printf("Resultado: %s venceu!\n", Cidade2);
            } else {
                printf("Resultado: Empate!\n");
            }
            break;

        case 2:
            printf("Atributo: Área\n");
            printf("%s: %.2f km²\n", Cidade1, Area1);
            printf("%s: %.2f km²\n", Cidade2, Area2);
            if (Area1 > Area2) {
                printf("Resultado: %s venceu!\n", Cidade1);
            } else if (Area2 > Area1) {
                printf("Resultado: %s venceu!\n", Cidade2);
            } else {
                printf("Resultado: Empate!\n");
            }
            break;

        case 3:
            printf("Atributo: PIB\n");
            printf("%s: R$ %.2f bilhões\n", Cidade1, PIB1);
            printf("%s: R$ %.2f bilhões\n", Cidade2, PIB2);
            if (PIB1 > PIB2) {
                printf("Resultado: %s venceu!\n", Cidade1);
            } else if (PIB2 > PIB1) {
                printf("Resultado: %s venceu!\n", Cidade2);
            } else {
                printf("Resultado: Empate!\n");
            }
            break;

        case 4:
            printf("Atributo: Pontos Turísticos\n");
            printf("%s: %d pontos\n", Cidade1, Pontos1);
            printf("%s: %d pontos\n", Cidade2, Pontos2);
            if (Pontos1 > Pontos2) {
                printf("Resultado: %s venceu!\n", Cidade1);
            } else if (Pontos2 > Pontos1) {
                printf("Resultado: %s venceu!\n", Cidade2);
            } else {
                printf("Resultado: Empate!\n");
            }
            break;

        case 5:
            printf("Atributo: Densidade Demográfica (menor vence)\n");
            printf("%s: %.2f hab/km²\n", Cidade1, Densidade1);
            printf("%s: %.2f hab/km²\n", Cidade2, Densidade2);
            if (Densidade1 < Densidade2) {
                printf("Resultado: %s venceu!\n", Cidade1);
            } else if (Densidade2 < Densidade1) {
                printf("Resultado: %s venceu!\n", Cidade2);
            } else {
                printf("Resultado: Empate!\n");
            }
            break;

        default:
            printf("Opção inválida. Por favor, selecione um número entre 1 e 5.\n");
            break;
    }

    return 0;
}
