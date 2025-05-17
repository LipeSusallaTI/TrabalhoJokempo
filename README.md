# TrabalhoJokempo
Trabalho Jokempo -- Luis Felipe e Felipe
```java
package projetopedrapapeltesoura;
//Importações

import java.util.Scanner;

public class ProjetoPedraPapeltesoura {

    public static void main(String[] args) {
        //Declaração de variáveis
        Scanner input = new Scanner(System.in);
        int vitorias = 0;
        int derrotas = 0;
        int empates = 0;
        boolean jogarNovamente = true;
        // enquanto jogarNovamente for true, vai fazer essa parte do código
        while (jogarNovamente) {
            System.out.println("==== MENU ==== ");
            System.out.println("0 → Pedra\n1 → Papel\n2 → Tesoura");
            System.out.println("Sua escolha:");
            int escolha = input.nextInt();
            // Se número não for alguma das opções, mostrar inválido
            if (escolha < 0 || escolha > 2) {
                System.out.println("Número inválido! Tente novamente.");
                return;
            }
            // Gerar jogada da IA
            int jogadaIa = (int) (Math.random() * 3);

            // Mostrar jogada da IA
            System.out.print("Eu escolhi ");
            switch (jogadaIa) {
                case 0:
                    System.out.println("Pedra!");
                    break;
                case 1:
                    System.out.println("Papel!");
                    break;
                case 2:
                    System.out.println("Tesoura!");
                    break;
            }

            // Determinar o resultado
            if (escolha == jogadaIa) {
                System.out.println("Resultado: Empate!");
                System.out.println("Eu quero vencer!");
                empates++;
            } else if ((escolha == 0 && jogadaIa == 2)
                    || (escolha == 1 && jogadaIa == 0)
                    || (escolha == 2 && jogadaIa == 1)) {
                System.out.println("Resultado: Você venceu!");
                System.out.println("Eu não irei perder na próxima!");
                vitorias++;
            } else {
                System.out.println("Resultado: Você perdeu!");
                System.out.println("Muahahaha eu venci!");
                derrotas++;
            }

            // Mostrar placar
            System.out.println("==== Placar Atual ====");
            System.out.println("Vitórias: " + vitorias);
            System.out.println("Derrotas: " + derrotas);
            System.out.println("Empates: " + empates);

            // Perguntar se quer jogar novamente
            while (true) {
                System.out.println("\nDeseja jogar novamente?");
                System.out.println("10 → Revanche");
                System.out.println("1 → Sair");
                System.out.print("Escolha: ");
                int escolhaRevanche = input.nextInt();

                if (escolhaRevanche == 10) {
                    break; // volta pro menu do jogo
                } else if (escolhaRevanche == 1) {
                    System.out.println("Saindo...");
                    jogarNovamente = false;
                    break; // Encerra o loop da pergunta
                    // Se o número não for 1 ou 10, mostrar inválido
                } else {
                    System.out.println("Número inválido! Digite 10 para revanche ou 1 para sair.");
                }
            }
        }
    }
}
```
