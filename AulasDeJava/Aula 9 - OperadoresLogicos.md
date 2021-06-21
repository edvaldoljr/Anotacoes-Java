# Aula 9 : Operadores Lógicos

```java
package aulasjava;
public class OperadoresLogicos {
    public static void main(String[] args) {
     int idade = 18;
     double altura = 1.60;
     System.out.println(idade >= 18 && altura >= 1.60);
    }
}
```
#### **Operador E ( && ) **

- O Operador “E” ou “&&” resulta em um valor VERDADEIRO se os dois valores de entrada da operação forem VERDADEIROS, caso contrário o resultado é FALSO. Abaixo a **tabela-verdade** da operação E.

  | **VALOR 1**    | **VALOR 2**    | **OPERAÇÃO E** |
  | -------------- | -------------- | -------------- |
  | **VERDADEIRO** | **VERDADEIRO** | **VERDADEIRO** |
  | VERDADEIRO     | FALSO          | FALSO          |
  | FALSO          | VERDADEIRO     | FALSO          |
  | FALSO          | FALSO          | FALSO          |



#### **Operador OU ( || ) **

- O Operador “OU” ou “||” resulta em um valor VERDADEIRO se ao menos UM dos dois valores de entrada da operação for VERDADEIRO, caso contrário o resultado é FALSO. Abaixo a **tabela-verdade** da operação OU.

  | **VALOR 1**    | **VALOR 2**    | **OPERAÇÃO OU** |
  | -------------- | -------------- | --------------- |
  | **VERDADEIRO** | **VERDADEIRO** | **VERDADEIRO**  |
  | **VERDADEIRO** | FALSO          | **VERDADEIRO**  |
  | FALSO          | **VERDADEIRO** | **VERDADEIRO**  |
  | FALSO          | FALSO          | FALSO           |

  