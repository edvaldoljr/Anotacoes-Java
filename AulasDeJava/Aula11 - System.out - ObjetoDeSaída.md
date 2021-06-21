# Aula 11 - System.out - Objeto de saída 

O objeto **System.out** é a saída padrão, que permite exibir as Strings no console (terminal) de comando quando o aplicativo de Java é executado. Dentro desse objeto existem métodos para gerar saídas de Strings, entre elas são: println, print e o printf.

### O método System.out.println()

A instrução System.out.println(), gera uma saída de texto entre aspas duplas significando uma String, criando uma nova linha e posicionando o cursor na linha abaixo, o que é identificado pela terminação **“ln”**.

```java
public class TextoSimples {
    public static void main(String[] args) {
        System.out.println("Seu texto é inserido aqui entre aspas duplas");
    }
}
```


### O método System.out.print()

O método com **print**, se for observado não possui o “ln”, por isso exibe uma String sem criar uma nova linha, deixando o seu cursor na mesma linha, veja no exemplo.



```java
public class TextoSimplesPrint {
    public static void main(String[] args) {
         System.out.print("José");
         System.out.print("Silva Moraes");
    }
}
```

### Caractere de escape

O caractere de escape pode ser considerado um caracter especial, permitindo inserir uma nova linha dentro dos métodos print e println do objeto System.out. Veja o exemplo.

```java
public class TextoSequenciaCaractere {
	public static void main(String[] args) {
    System.out.print("Antônio \n Vieira \n dos\n Santo\n ");
    }
}
```

No exemplo acima não é impresso o “**\n**”, porque o Java identifica que é uma sequência de escape (barra invertida e um caractere de escape) dentro de uma String de caracteres.

A sequência de escape “\n” é representada por um caractere de nova linha o “n”, fazendo que o cursor de saída da tela mova-se para o começo de uma nova linha. Vejamos algumas sequências de escapes.

- \n - Nova linha. Posiciona o cursor de tela no início da próxima linha
- \t - Tabulação horizontal. Move o cursor de tela para a próxima parada de tabulação.
- \r - Posiciona o cursor da tela no início da linha atual - não avança para a próxima linha. Qualquer saída de caracteres gerada depois de algum retorno já gerado é sobrescrito os caracteres anteriores gerados na linha atual.
- \” -  Aspas duplas. Utilizada para imprimir um caractere de aspas duplas. Exemplo, System.out.println(“\”aspas\””); exibe “aspas”

### O método printf()

O argumento do método printf é uma **String de formato** que pode consistir em texto fixo e **especificadores de formato**. A letra “**f**” no final da palavra “print” significa “**formatted**” ou seja exibe os dados formatados.

Os especificadores de formato são como marcadores de lugares para um valor, especificando o tipo da saída dos dados que iniciam com um sinal de porcentagem (%) seguido por um caractere representando seu tipo de dado.

Veja no exemplo, o especificador de formato **%s**, que é um marcador de lugar para uma String, se for especificado um número no lugar irá gerar um erro.

Imprime caracteres de Strings referente a cada posição

```java
public class TextoPrintf{
	public static void main(String[] args) {
        System.out.printf("%s\n %s\n", "Marcela", "Nogueira");
    }
}
```

**Veja alguns especificadores de formato**

- **%d** - representa números inteiros
- **%f** - representa números floats
- **%2f** - representa números doubles
- **%b** - representa valores booleanos
- **%c** - representa valores char

Veja um exemplo de saída de números com o especificador de formato.

Exibindo números com o especificador de formato %d

```java
public class Testa_Especificador {
	public static void main(String[] args) {
        int num1 = 10;
        int num2 = 30;
        System.out.printf("Soma das variáveis num1 e num 2 = %d",(num1 + num2));
	}
}
```

##### Principais diferenças dos métodos.

- **System.out.println** - Insere uma nova linha, deixando o marcador posicionado na linha abaixo.

- **System.out.print** - Mantém o cursor na mesma linha. Geralmente são utilizadas sequências de escape para pular uma linha.

- **System.out.printf** - Especifica o formato da entrada do tipo de valor, que deve ser o mesmo tipo de dados apontado na instrução. Se possuir alguma dúvida verifique o especificadores de formato dos tipos de dados que podem ser usados.

