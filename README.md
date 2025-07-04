# Avaliacao
import java.util.Scanner;

public class SistemaEscolar {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double[] notas = new double[8];
        double[] mediasBimestrais = new double[4];
        double[] mediasSemestrais = new double[2];
        double mediaFinal;

        System.out.println("===== Sistema Escolar =====");
        System.out.println("Digite as 8 notas anuais (2 por bimestre):");

        // Receber as 8 notas
        for (int i = 0; i < 8; i++) {
            System.out.print("Digite a nota " + (i + 1) + ": ");
            notas[i] = scanner.nextDouble();
        }

        // Calcular médias bimestrais (cada bimestre = 2 notas)
        for (int i = 0; i < 4; i++) {
            mediasBimestrais[i] = (notas[i * 2] + notas[i * 2 + 1]) / 2;
        }

        // Calcular médias semestrais
        mediasSemestrais[0] = (mediasBimestrais[0] + mediasBimestrais[1]) / 2;
        mediasSemestrais[1] = (mediasBimestrais[2] + mediasBimestrais[3]) / 2;

        // Calcular média final
        mediaFinal = (mediasSemestrais[0] + mediasSemestrais[1]) / 2;

        // Exibir resultados
        System.out.println("\n===== Resultados =====");
        for (int i = 0; i < 4; i++) {
            System.out.printf("Média do %dº bimestre: %.2f%n", i + 1, mediasBimestrais[i]);
        }

        for (int i = 0; i < 2; i++) {
            System.out.printf("Média do %dº semestre: %.2f%n", i + 1, mediasSemestrais[i]);
        }

        System.out.printf("Média final: %.2f%n", mediaFinal);

        scanner.close();
    }
}
import java.util.Scanner;

public class ConversorTemperatura {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("=======================================");
        System.out.println("     Conversor de Temperatura");
        System.out.println("=======================================");

        // Entrada
        System.out.print("Digite a temperatura em graus Celsius: ");
        double celsius = scanner.nextDouble();

        // Conversão
        double fahrenheit = (celsius * 9 / 5) + 32;
        double kelvin = celsius + 273.15;

        // Interpretação (opcional)
        String interpretacao;
        if (celsius < 0) {
            interpretacao = "Muito frio! 🥶";
        } else if (celsius >= 0 && celsius < 18) {
            interpretacao = "Temperatura fria.";
        } else if (celsius >= 18 && celsius < 30) {
            interpretacao = "Temperatura agradável.";
        } else if (celsius >= 30 && celsius < 40) {
            interpretacao = "Está quente! ☀️";
        } else {
            interpretacao = "Calor extremo! 🔥";
        }

        // Saída clara e detalhada
        System.out.println("\n========== Resultados ==========");
        System.out.printf("Temperatura original: %.2f °C%n", celsius);
        System.out.printf("Convertida para Fahrenheit: %.2f °F%n", fahrenheit);
        System.out.printf("Convertida para Kelvin: %.2f K%n", kelvin);
        System.out.println("Interpretação: " + interpretacao);
        System.out.println("=======================================");

        scanner.close();
    }
}
