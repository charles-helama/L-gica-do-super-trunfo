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
    scanf(" %[^\n]", Cidade1);  // Lê até a quebra de linha
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

    // Cálculos - Carta 1
    Densidade1 = Populacao1 / Area1;
    PIB_per_Capita1 = (PIB1 * 1e9) / Populacao1;
    SuperPoder1 = Populacao1 + Area1 + PIB1 + Pontos1 + PIB_per_Capita1 + (1.0 / Densidade1);

    // Cálculos - Carta 2
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

    // Comparações
    printf("--- Comparacoes (1 = Carta 1 vence, 0 = Carta 2 vence) ---\n");
    printf("Populacao: %d\n", Populacao1 > Populacao2);
    printf("Area: %d\n", Area1 > Area2);
    printf("PIB: %d\n", PIB1 > PIB2);
    printf("Pontos Turisticos: %d\n", Pontos1 > Pontos2);
    printf("PIB per Capita: %d\n", PIB_per_Capita1 > PIB_per_Capita2);
    printf("Densidade Populacional (menor vence): %d\n", Densidade1 < Densidade2);
    printf("Super Poder: %d\n", SuperPoder1 > SuperPoder2);

    // Comparação específica: Densidade Populacional
    printf("\n--- Comparação com base em Densidade Populacional (menor vence) ---\n");
    printf("Densidade Populacional %s: %.2f\n", Cidade1, Densidade1);
    printf("Densidade Populacional %s: %.2f\n", Cidade2, Densidade2);

    if (Densidade1 < Densidade2) {
        printf("Resultado: Carta 1 (%s) venceu com menor densidade populacional!\n", Cidade1);
    } else if (Densidade2 < Densidade1) {
        printf("Resultado: Carta 2 (%s) venceu com menor densidade populacional!\n", Cidade2);
    } else {
        printf("Resultado: Empate! Ambas as cartas têm a mesma densidade populacional.\n");
    }

    return 0;
}