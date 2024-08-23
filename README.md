# TrabalhoJava
Crie um programa para uma empresa de que fornece um Cashback de acordo com  seu perfil de compra. 

public class Cliente {
    private String nome;
    private int idade;
    private double valorCompra;

    public Cliente(String nome, int idade, double valorCompra) {
        this.nome = nome;
        this.idade = idade;
        this.valorCompra = valorCompra;
    }

    public double calcularCashback() {
        if (idade >= 21 && valorCompra < 1000) {
            return valorCompra * 0.05;
        } else if (idade < 21 && valorCompra < 1000) {
            return valorCompra * 0.07;
        } else if (idade >= 21 && valorCompra >= 1000) {
            return valorCompra * 0.07;
        } else {
            return valorCompra * 0.10;
        }
    }

    public void imprimirDados() {
        System.out.println("Cliente: " + nome);
        System.out.println("Idade: " + idade);
        System.out.println("Cashback: R$ " + String.format("%.2f", calcularCashback()));
    }
}

public class Main {
    public static void main(String[] args) {
        Cliente cliente = new Cliente("João", 25, 800.0);
        cliente.imprimirDados();

        cliente = new Cliente("Maria", 18, 1200.0);
        cliente.imprimirDados();

        cliente = new Cliente("Pedro", 30, 500.0);
        cliente.imprimirDados();

        cliente = new Cliente("Ana", 19, 1500.0);
        cliente.imprimirDados();
    }
}
