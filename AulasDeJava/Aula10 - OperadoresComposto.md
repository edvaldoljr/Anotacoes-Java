#  Aula 10 - Operadores Composto

Os operadores compostos representam a 5ª categoria de operadores da [programação](https://pt.wikipedia.org/wiki/Programação_de_computadores) e, em resumo, fornecem uma maneira mais curta para realizar algumas operações aritméticas.

| ++     | **incremento**.              |
| ------ | ---------------------------- |
| **--** | **decremento**               |
| **+=** | **atribuição-adição**.       |
| **-=** | **atribuição-subtração**.    |
| ***=** | **atribuição-multiplicação** |
| **/=** | **atribuição-divisão**       |
| **%=** | **atribuição-resto**.        |



```java
public class OperadoresDeAtribuicao {
    public static void main(String[] args) {
        // =, ++, --, -=, +=, *=, /=, %=
        int salario = 1000;
        
        int salario1 = salario + 1000;

        int salario2 = 1000;
        salario2 += 1000;

        int salario3 = 1000;
        salario3 -= 1000;

        int salario4 = 1000;
        salario4 *= 1000;

        int salario5 = 1000;
        salario5 /= 1000;

        int salario6 = 10;
        salario6 %= 5;

        int salario7 = 1000;
        salario7 ++;
        
        System.out.println("= " + salario);
        System.out.println(" salario + 1000 " + salario1);
        System.out.println("+= " + salario2);
        System.out.println("-= " + salario3);
        System.out.println("*= " + salario4);
        System.out.println("/= " + salario5);
        System.out.println("%= " + salario6);
        System.out.println("==" + salario7);
    }
}
```

