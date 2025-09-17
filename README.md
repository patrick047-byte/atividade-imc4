import java.util.Scanner;

public class CalculoIMC {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double peso = lerValor(sc, "Digite seu peso (kg): ");
        double altura = lerValor(sc, "Digite sua altura (m): ");

        double imc = calcularIMC(peso, altura);
        System.out.printf("Seu IMC é: %.2f%n", imc);

        String classificacao = classificarIMC(imc);
        System.out.println("Classificação: " + classificacao);

        sc.close();
    }

    // Método para ler valores do usuário
    public static double lerValor(Scanner sc, String mensagem) {
        System.out.print(mensagem);
        double valor = sc.nextDouble();
        while (valor <= 0) {
            System.out.print("Valor inválido. " + mensagem);
            valor = sc.nextDouble();
        }
        return valor;
    }

    // Método para calcular o IMC
    public static double calcularIMC(double peso, double altura) {
        return peso / (altura * altura);
    }

    // Método para classificar o IMC
    public static String classificarIMC(double imc) {
        if (imc < 18.5) {
            return "Abaixo do peso";
        } else if (imc < 24.9) {
            return "Peso normal";
        } else if (imc < 29.9) {
            return "Sobrepeso";
        } else {
            return "Obesidade";
        }
    }
}
