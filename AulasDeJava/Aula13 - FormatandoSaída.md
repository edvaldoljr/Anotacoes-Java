# Aula 13 - Formatando a saída de números inteiros e quebrados: Comandos Print, Printf e Println.

Sabemos que para imprimir um texto ou palavras na tela podemos utilizar os comandos Print, Printf e Println.

```java
public static void main(String[] args) {
    System.out.print("Imprimindo na tela  1 ");
    System.out.printf("Imprimindo na tela  2 ");
    System.out.println("Imprimindo na tela  3");
}
```

E se quisermos imprimir valores, como prosseguimos? Lembrando que existem valores inteiros e fracionários, 10 é um número inteiro e 10.5 é um número fracionário.

## Imprimindo números com o Printf

Se você leu o artigo anterior deve se lembrar que eu disse que o printf nada mais é que um comando para formatar um número, por isso que atribuímos o “f” ao final dele (printf).

Basicamente para formatar a saída de um número colocamos o sinal de **%,** é onde está o **%** que será inserido o valor. Após isso, dizemos qual é o tipo de valor que está sendo impresso, se for inteiro colocarmos **%d**, se for float ou double colocamos **%f** e caso usemos o printf para imprimir uma string colocamos **%s.**

Acompanhe o exemplo a seguir onde está sendo impresso valores diferentes:

```java
public static void main(String[] args) {
    String nome = "Kaio Ferreira";
    System.out.printf("%s",nome);
    System.out.printf("\n");
    int numeroInteiro = 10;
    System.out.printf("%d", numeroInteiro);
    System.out.printf("\n");
    float numeroFlutuante1 = 10.5f;
	System.out.printf("%f", numeroFlutuante1);
    System.out.printf("\n");
    double numeroFlutuante2 = 20.5;
    System.out.printf("%f", numeroFlutuante2);
}
```

Por tanto, quando usamos o comando **Printf** para concatenar (juntar) mensagens e valores não usa-se o sinal de mais (+), colocamos uma vírgula (,) para separar a mensagem das variáveis que serão inseridos.

Veja o exemplo onde imprimo os valores concatenados somente em uma única frase:

```java
public static void main(String[] args) {
    String nome = "Kaio Ferreira";
	int numeroInteiro = 10;
	float numeroFlutuante1 = 10.5f;
	double numeroFlutuante2 = 20.5;
    System.out.printf("O meu nome é: %s, numero inteiro é: %d, numero float e: %f e o numemero double é %f",nome,numeroInteiro,numeroFlutuante1, numeroFlutuante2);
}
```

Se você notou, a mesma sequência onde é definido que tipo de número vai ser impresso, foi colocado a variável correspondente separado por vírgula. Isso lembra bastante o Println, quando usamos o mais(+) para separar as frases das variáveis.

Outro aspecto que notamos ao imprimir um número fracionário é que da forma que definimos ele está sendo impresso por completo, como no exemplo acima, o numeroFlutuante1 está saindo por completo (10.500000). Para resolver este problema podemos limitar o número de casas decimais colocando **%.2f**, onde o número 2 é o número de casas decimais que deve aparecer.

```java
public static void main(String[] args) {
	String nome = "Kaio Ferreira";
	int numeroInteiro = 10;
	float numeroFlutuante1 = 10.5f;
	double numeroFlutuante2 = 20.5;
	System.out.printf("O meu nome é: %s, numero inteiro é: %d, numero float e: %.2f e o
	numemero double é %.2f",nome,numeroInteiro,numeroFlutuante1, numeroFlutuante2);
}
```
Esses são os métodos de formatação de números com o comando Printf, a seguir veremos como formatar números com o Println.

## Imprimindo números com o Println

Ao usamos o comando de impressão Println a concatenação de valores é feita usado o sinal de mais (+). Com esse comando para formatar um numero é preciso usar uma Classe chamada DecimalFormat.

Essa classe faz parte de um pacote de códigos que podemos definir um padrão para a nossa saída, acompanhe o exemplo:

```java
public static void main(String[] args) {
    float numeroFlutuante1 =  10.326665f;
    double numeroFlutuante2 = 20.56556;
    DecimalFormat numeroFormatado = new DecimalFormat("##.##");
    
    System.out.println("Meu primeiro número formatado com Println: " +
    numeroFormatado.format(numeroFlutuante1));
    System.out.println("Meu primeiro número formatado com Println: " +
    numeroFormatado.format(numeroFlutuante2));
   }
```
Primeiro eu chamo a classe DecimalFormat, apos isso eu inicializo ela passando o padrão de saída que desejo, no exemplo acima coloquei um numero com duas casas decimais após a virgula.