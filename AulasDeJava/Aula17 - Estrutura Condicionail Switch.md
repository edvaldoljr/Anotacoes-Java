# Aula17 - Estrutura Condicional Switch



## Java 14: exemplos de aprimoramentos de expressões de alternância

## 1. O que há de novo para o bloco switch no Java 14?

O Java 14 adiciona uma nova forma de rótulo de switch “case L ->” que permite várias constantes por case e retorna um valor para todo o bloco switch-case para que possa ser usado em expressões (expressões de switch). E a palavra-chave yield é usada para retornar o valor de uma expressão switch.

Agora, vamos ver exemplos de código para entender esses aprimoramentos para a construção de switch case.

## 2. Nova forma de etiqueta do interruptor

Com o bloco de comutação tradicional, cada caso é associado a apenas uma constante – portanto, você precisa passar por vários casos para um grupo de constantes que compartilham a mesma lógica. Considere o seguinte exemplo de código:

```java
public void daysOfMonth(int month) {
  switch (month) {
    case 1:
    case 3:
    case 5:
    case 7:
    case 8:
    case 10:
    case 12:
      System.out.println("this month has 31 days");
      break;
    case 4:
    case 6:
    case 9:
      System.out.println("this month has 30 days");
      break;
    case 2:
      System.out.println("February can have 28 or 29 days");
      break;
    default:
      System.out.println("invalid month");
 }
}
```

Você vê, este método imprime o número de dias em um determinado mês. Alguns meses têm 31 dias, outros têm 30 dias e o mês de fevereiro pode ter 28 ou 29 dias.

Usar casos de fall-through como esse é desnecessariamente detalhado. Portanto, no Java 14, você pode usar uma nova forma de rótulo de switch que permite várias constantes por caso, conforme abaixo:

```java
switch (month) {
  case 1, 3, 5, 7, 8, 10, 12 -> System.out.println("this month has 31 days");
  case 4, 6, 9 -> System.out.println("this month has 30 days");
  case 2 -> System.out.println("February can have 28 or 29 days");
  default -> System.out.println("invalid month");
}
```

Agora, com a nova forma de rótulo do switch “case L ->”, o código do bloco do switch parece mais claro, mais conciso e mais legível. Você pode usar várias constantes por maiúsculas e minúsculas para reduzir a verbosidade e não precisa usar explicitamente a instrução break para encerrar a maiúsculas e minúsculas, o que leva a um código menos propenso a erros (sem falhas e sem interrupções).

Na nova forma de rótulo switch, o código após o rótulo da seta pode ser uma expressão, um bloco ou uma instrução throw. Por exemplo:

```java
switch (month) {
  case 1, 3, 5, 7, 8, 10, 12 -> System.out.println("this month has 31 days");
  case 4, 6, 9 -> System.out.println("this month has 30 days");
  case 2 -> {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter year: ");
    int year = scanner.nextInt();
 
    if (year % 4 == 0)
      System.out.println("This february has 29 days");
    else
      System.out.println("This February has 28 days");
 }
  default -> throw new IllegalArgumentException("Invalid month");
}
```

Lembre-se de que, usando a nova forma de rótulo switch, não precisamos colocar a instrução break, pois o código não passa para o próximo caso.

## 3. Exemplos de expressões de comutação

A partir do Java 14, podemos usar um bloco switch case em uma expressão, o que significa que o bloco switch pode retornar um valor. Com a instrução switch tradicional, temos que usar a variável temporária conforme mostrado no exemplo de código a seguir:

```java
int days = 0;
switch (month) {
  case 1:
  case 3:
  case 5:
  case 7:
  case 8:
  case 10:
  case 12:
    days = 31;
    break;
  case 4:
  case 6:
  case 9:
    days = 30;
    break;
  case 2:
    days = 28;
    break;
  default:
    throw new IllegalArgumentException("Invalid month");
}
 
// use days...
```

Agora, com o Java 14, podemos reescrever o código acima da seguinte maneira:

```java
int days = switch (month) {
    case 1, 3, 5, 7, 8, 10, 12 -> 31;
    case 4, 6, 9 -> 30;
    case 2 -> 28;
    default -> 0;
};
// use days...
```

ou:

```java
System.out.println(
  switch (month) {
    case 1, 3, 5, 7, 8, 10, 12 -> 31;
    case 4, 6, 9 -> 30;
    case 2 -> 28;
    default -> 0;
 }
);
```

Esse uso conveniente do bloco switch é chamado ***de expressão switch\*** . Se o código de um caso for um bloco de código, você poderá usar a palavra-chave ***yield\*** para retornar o valor do bloco switch. Por exemplo:

```java
int days = switch (month) {
    case 1, 3, 5, 7, 8, 10, 12 -> 31;
    case 4, 6, 9 -> 30;
    case 2 -> {
      Scanner scanner = new Scanner(System.in);
      System.out.print("Enter year: ");
      int year = scanner.nextInt();
 
      if (year % 4 == 0)
        yield 29;
      else
        yield 28;
   }
    default -> 0;
};
// use days...
```

Além disso, você também pode usar a instrução yield em combinação com rótulos de maiúsculas tradicionais que terminam com dois pontos como este:

```java
int days = switch (month) {
  case 1, 3, 5, 7, 8, 10, 12:
    yield 31;
  case 4, 6, 9:
    yield 30;
  case 2: {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter year: ");
    int year = scanner.nextInt();
 
    if (year % 4 == 0)
      yield 29;
    else
      yield 28;
 
 }
  default: yield 0;
};
// use days...
```

Mas você não pode misturar “case L :” e “case L -> “ em um bloco switch. A palavra-chave **yield** é escolhida em vez de **return** para evitar confusão: **return** sai do método, enquanto **yield** retorna valor e sai do bloco switch.

**Conclusão:**

Espero que este post esclareça dúvidas que você possa ter com a instrução switch e a expressão switch. Acho que esses aprimoramentos são muito úteis para programadores, pois agora eles podem usar o bloco de comutação de maneiras mais flexíveis - também reduzindo a verbosidade da linguagem de programação Java.
