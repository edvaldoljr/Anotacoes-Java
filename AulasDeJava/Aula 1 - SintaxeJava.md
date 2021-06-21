# Aula 1: Sintaxe Java

```java
public class Main {
	public static void main(String[] args) {
	System.out.println("Hello World");
	}
}
```

### Exemplo explicado

Cada linha de código executada em Java deve estar dentro de um `class`. Em nosso exemplo, chamamos a classe de **Main** . Uma aula sempre deve começar com uma primeira letra maiúscula.

**Nota:** Java diferencia maiúsculas de minúsculas: "MyClass" e "myclass" têm significados diferentes.

O nome do arquivo java **deve corresponder** ao nome da classe. Ao salvar o arquivo, salve-o usando o nome da classe e adicione ".java" ao final do nome do arquivo. Para executar o exemplo acima em seu computador, certifique-se de que o Java está instalado corretamente: 

## O método principal

O `main()`método é obrigatório e você o verá em todos os programas Java:

```java
public static void main(String[] args)
```

Qualquer código dentro do `main()`método será executado. Você não precisa entender as palavras-chave antes e depois do main. Você os conhecerá aos poucos ao ler este tutorial.

Por enquanto, lembre-se de que todo programa Java tem um `class`nome que deve corresponder ao nome do arquivo e que todo programa deve conter o `main()`método.

## System.out.println ()

Dentro do `main()`método, podemos usar o `println()` método para imprimir uma linha de texto na tela:

```java
	public static void main(String[] args) {
	System.out.println("Hello World");
	}
```

**Observação:** as chaves `{}`marcam o início e o fim de um bloco de código.

**Nota:** Cada instrução de código deve terminar com um ponto e vírgula ;.'