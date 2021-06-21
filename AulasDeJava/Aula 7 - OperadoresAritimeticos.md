# Aula 7 - Operadores Aritméticos

#### Aritmética

Os operadores aritméticos são **operadores binários**, ou seja, funcionam com dois operandos. Por exemplo, a expressão **“a + 1”** contém o operador binário **“+” (mais)** e os dois operandos **“a”** e **“1”**.

| Operação      | Operador | Expressão algébrica | Expressão Java |
| ------------- | -------- | ------------------- | -------------- |
| Adição        | +        | a + b               | a + b          |
| Subtração     | -        | b - a               | b - a          |
| Multiplicação | *        | ab                  | b * a          |
| Divisão       | /        | a / b               | a / b          |
| Resto         | %        | a mod b             | a % b          |

**Observação importante**: a divisão de inteiros produz um quociente do tipo inteiro, quando possuímos o número 1 maior que o número 2 por exemplo, a expressão 9 / 6 o resultado é interpretado como 1 e a expressão 23 / 8 é avaliada como 2, ou seja a parte fracionária em uma divisão de inteiros é descartada, não contendo nenhum arredondamento.

O **módulo (%)** fornece o resto da divisão, na expressão “x % y”, o resultado é o restante depois que x é dividido por y, sendo assim na expressão “7 % 4” o resultado é 3 e “17 % 5” o resultado produz 2. Esse operador é mais utilizado com operandos inteiros, mas também pode ser utilizado com outros tipos.

```java
public class OperadoresAritimeticos {
    public static void main(String[] args) {
    int a = 30;
    int b = 5;
    int c = 10;
    int total = (a + b + c) / 10;
    System.out.println("O resultado = "+total);
    }
}
```

**Troque os operadores um a um e veja os resultados.**

