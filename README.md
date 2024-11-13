# calculadora.java
Calculadora simples em Java que permite realizar operações básicas como adição, subtração, multiplicação e divisão. A aplicação é voltada para o aprendizado de conceitos fundamentais da linguagem, incluindo manipulação de entradas e validação de dados. Interface de usuário via terminal.
import java.util.ArrayList;
import java.util.Scanner;

class Produto {
    String nome;
    double preco;

    Produto(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }
}
public class Calculadora {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Produto> carrinho = new ArrayList<>();
        double total = 0.0;

        System.out.println("Bem-vindo à Simulação de Compra!");

        while (true) {
            System.out.print("Digite o nome do produto ou 'finalizar' para encerrar: ");
            String nomeProduto = scanner.nextLine();

            if (nomeProduto.equalsIgnoreCase("finalizar")) {
                break;
            }

            System.out.print("Digite o preço do produto: ");
            double precoProduto = scanner.nextDouble();
            scanner.nextLine();

            Produto produto = new Produto(nomeProduto, precoProduto);
            carrinho.add(produto);
            total += precoProduto;

            System.out.println("Produto adicionado: " + nomeProduto + " - R$" + precoProduto);
            System.out.println("Total atual: R$" + total);
        }

        System.out.println("\nResumo da Compra:");
        for (Produto produto : carrinho) {
            System.out.println("- " + produto.nome + ": R$" + produto.preco);
        }

        System.out.println("Total da compra: R$" + total);
        System.out.println("Obrigado pela compra!");

        scanner.close();
    }
}
