# Sub-Rotina-Assist-ncia-Medica-

Conheça melhor o projeto !

Este projeto consiste em uma classe Java chamada `CalculadoraSalario` que determina o tipo e o valor do desconto de assistência médica de um colaborador, com base em seu salário bruto. O programa calcula o desconto e o salário líquido e, em seguida, exibe os resultados.

-----

### Funcionalidades

O programa executa as seguintes ações:

1.  Recebe um valor de salário bruto.
2.  Aplica as regras de desconto com base em faixas salariais.
3.  Calcula o valor do desconto e o salário líquido.
4.  Identifica o tipo de desconto (`Isento`, `Mínimo`, `Médio`, `Máximo`).
5.  Imprime todos os resultados na tela.

-----

### Regras de Negócio

O cálculo do desconto segue as seguintes regras:

  * **Salário até R$ 2000,00:** Isento de desconto (0%).
  * **Salário de R$ 2000,01 até R$ 4000,00:** Desconto Mínimo (2%).
  * **Salário acima de R$ 4000,00:** Desconto Médio (4%).
  * **Se o valor do desconto calculado for superior a R$ 400,00:** O desconto é ajustado para R$ 400,00 e o tipo de desconto é classificado como Máximo.

-----

### Como Usar

Você pode usar a classe `CalculadoraSalario` para calcular os descontos de qualquer salário bruto. O método `main` já inclui exemplos de uso.

#### Exemplo de Código

```java
public class CalculadoraSalario {

    public void CalcularDesconto(double salarioBruto) {
        double percentualDesconto = 0;
        String tipoDeDesconto = "Isento";

        // Lógica para determinar o percentual de desconto
        if (salarioBruto <= 2000) {
            percentualDesconto = 0;
            tipoDeDesconto = "Isento";
        } else if (salarioBruto <= 4000) {
            percentualDesconto = 2;
            tipoDeDesconto = "Mínimo";
        } else {
            percentualDesconto = 4;
            tipoDeDesconto = "Médio";
        }

        double valorDeDesconto = (salarioBruto * percentualDesconto) / 100;
        
        // Regra do desconto máximo
        if (valorDeDesconto > 400) {
            valorDeDesconto = 400;
            tipoDeDesconto = "Máximo";
        }
        
        double salarioLiquido = salarioBruto - valorDeDesconto;

        // Impressão dos resultados
        System.out.println("Salário Bruto: R$" + salarioBruto);
        System.out.println("------------------------------------");
        System.out.println("1. O Salario Liquido e: R$" + salarioLiquido);
        System.out.println("2. O valor do Desconto e: R$" + valorDeDesconto);
        System.out.println("3. O Tipo de Desconto e: " + tipoDeDesconto);
    }

    public static void main(String[] args) {
        CalculadoraSalario calculadora = new CalculadoraSalario();
        
        // Exemplo 1
        calculadora.CalcularDesconto(5000); 
        System.out.println("\n--- Outro exemplo ---");
        
        // Exemplo 2
        calculadora.CalcularDesconto(3500); 
    }
}
```

#### Para Compilar e Executar

1.  Salve o código em um arquivo chamado `CalculadoraSalario.java`.
2.  Abra o terminal ou prompt de comando e navegue até o diretório do arquivo.
3.  Compile o código com o comando:
    ```
    javac CalculadoraSalario.java
    ```
4.  Execute a classe com o comando:
    ```
    java CalculadoraSalario
    ```
