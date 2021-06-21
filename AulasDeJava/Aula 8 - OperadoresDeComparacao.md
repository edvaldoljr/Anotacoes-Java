# Aula 8 - Operadores de comparação



## Tabela de operadores de comparação

Os operadores mais utilizados na lógica de programação são: >, >=, <, <=, ==, !=.

- \> (maior): Retorna verdadeiro caso o primeiro valor seja maior que o segundo.

- \>= (maior ou igual): Retorna verdadeiro caso o primeiro valor seja maior ou igual ao segundo.

- < (menor): Retorna verdadeiro caso o primeiro valor seja menor que o segundo.

- <= (menor ou igual): Retorna verdadeiro caso o primeiro valor seja menor ou igual ao segundo

- == (igual a): Retorna verdadeiro caso o primeiro valor seja igual ao segundo.

- != (diferente de): Retorna verdadeiro caso o primeiro valor seja diferente do segundo.

  

    
  
    ```java
    package aulasjava;
    public class OperadoresDeComparacao {
        public static void main(String[] args) {
    	boolean dezMaiorQueVinte = 10 > 20;
    	System.out.println(dezMaiorQueVinte);
    
    	boolean dezMaiorOuIgual = 10 >= 20;
    	System.out.println(dezMaiorOuIgual);
    
    	boolean dezMenorOuIgual = 10 <= 20;
    	System.out.println(dezMenorOuIgual);
    
    	boolean dezMenorQueVinte = 10 < 20;
    	System.out.println(dezMenorQueVinte);
    
    	System.out.println(5 == 5); 
    
    	System.out.println(5 != 5);
        }
    }
    ```
    
     
