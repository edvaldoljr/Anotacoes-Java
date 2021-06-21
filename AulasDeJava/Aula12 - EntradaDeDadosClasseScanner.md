# Aula 12 - Entrada de Dados: Classe Scanner

Quem programa em Java, depara-se com a seguinte situação: como atribuir valores para uma variável usando o teclado?

No Java, a partir do Java 1.5 ou J2SE 5, que recebeu o codinome "Tiger", está disponível a **classe Scanner** do pacote **java.util**. Essa classe implementa as operações de entrada de dados pelo teclado no console.

| ............... | Para utilizar a classe Scanner em uma aplicação Java deve-se proceder da seguinte maneira: |
| --------------- | ------------------------------------------------------------ |
| [ 1 ]           | importar o pacote java.util: **import** java.util.Scanner;   |
| [ 2 ]           | Instanciar e criar um objeto Scanner: Scanner ler = ***\new\*** Scanner(System.in); |
| [ 3 ]           | Lendo valores através do teclado:                            |
| [ 3.1 ]         | Lendo um valor inteiro: **int** n;  System.out.printf("Informe um número para a tabuada: "); n = ler.**nextInt**(); |
| [ 3.2 ]         | Lendo um valor real: **float** preco;  System.out.printf("Informe o preço da mercadoria = R$ "); preco = ler.**nextFloat**(); |
| [ 3.3 ]         | Lendo um valor real: **double** salario;  System.out.printf("Informe o salário do Funcionário = R$ "); salario = ler.**nextDouble**(); |
| [ 3.4 ]         | Lendo uma String, usado na leitura de palavras simples que não usam o caractere de espaço (ou barra de espaço): **String** s;  System.out.printf("Informe uma palavra simples:\n"); s = ler.**next**(); |
| [ 3.5 ]         | Lendo uma String, usado na leitura de palavras compostas, por exemplo, Pato Branco: **String** s;  System.out.printf("Informe uma cadeia de caracteres:\n"); s = ler.**nextLine**(); |
| [ 3.6 ]         | Na leitura consecutiva de valores numéricos e String deve-se esvaziar o buffer do teclado antes da leitura do valor String, por exemplo: **int** n; **String** s;  System.out.printf("Informe um Número Inteiro: "); n = ler.**nextInt**();  ler.**nextLine**(); *// esvazia o buffer do teclado*  System.out.printf("Informe uma cadeia de caracteres:\n"); s = ler.**nextLine**(); |
| [ 3.7 ]         | Lendo um caractere usando o método **read()** do pacote de classes **System.in**: public static void main(String args[]) **throws** Exception { **char** c;  System.out.printf("Informe um Caractere: "); c = (**char**)System.in.**read**(); } |

```java
package Aulas;

import java.util.Scanner;

public class LeituraDadosTeclado{
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);

        String nome;
        float nota;

        System.out.print("Nome do aluno: ");
        nome = teclado.nextLine();

        System.out.print("Nota do aluno: ");
        nota = teclado.nextFloat();

        System.out.printf("A nota de %s é %.1f \n ", nome, nota);
    }
}
```

```java
package aulas;

import java.util.Scanner;

public class LeituraDadosTeclado {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.println("+-----------------------------------------------------+");
        System.out.printf("DIGITE SEU NOME COMPLETO: ");
        String nomeCompleto = teclado.nextLine();
        System.out.printf("Nome completo: %s \n",nomeCompleto);
        System.out.println("+-----------------------------------------------------+");
        System.out.printf("DIGITE SEU PRIMEIRO NOME: ");
        String primeiroNome = teclado.next();
        System.out.printf("Primeiro nome: %s \n", primeiroNome);
        System.out.println("+-----------------------------------------------------+");
        System.out.printf("DIGITE IDADE: ");
        int idade = teclado.nextInt();
        System.out.printf("Idade : %d \n", idade);
        System.out.println("+-----------------------------------------------------+");
        System.out.printf("DIGITE SUA ALTURA: ");
        double altura = teclado.nextDouble();
        System.out.printf("A sua altura é: %.2f", altura);
        System.out.println("+-----------------------------------------------------+")
        System.out.printf("TEM ANIMAL: ");
        boolean pet = teclado.hasNextBoolean();
        System.out.printf("Pet: %b ", pet);
        System.out.println("+-----------------------------------------------------+");
    }
}
```

```java
package aulas;

import java.util.Scanner;

public class LeituraDadosTeclado {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.println("DIGITE SEU NOME COMPLETO: ");
        String nomeCompleto = teclado.nextLine();
        System.out.println("DIGITE SEU PRIMEIRO NOME: ");
        String primeiroNome = teclado.next();
        System.out.println("DIGITE IDADE: ");
        int idade = teclado.nextInt();
        System.out.println("DIGITE SUA ALTURA: ");
        double altura = teclado.nextDouble();
        System.out.printf( " Nome completo : %s \n Primeiro nome: %S \n Idade: %d \n Altura: %.2f ",
                          nomeCompleto,primeiroNome,idade,altura);
    }
}
```

