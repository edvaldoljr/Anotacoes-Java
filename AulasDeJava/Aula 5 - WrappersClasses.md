# Aula 5: Wrappers Classes

Os **Wrapper** são conhecidos na linguagem Java como classes especiais que possuem métodos capazes de fazer conversões em variáveis primitivas e também de encapsular tipos primitivos para serem trabalhados como objetos, ou seja, é feita um embrulho de streams que são fluxo de dados através de canais.

Sendo assim, existe uma classe Wrapper para cada tipo primitivo identificado pelo mesmo nome do tipo que possui e tendo a primeira letra maiúscula. Essa regra de declaração é aplicada a todos os tipos, exceto aos que são char classificados como Character e boolean como Boolean.

Cada tipo wrapper numérico em Java são subclasses da superclasse abstrataNumber (Java.lang.Number) que consegue acessar todos os métodos values que são: **doubleValue(), floatValue(), longValue(), intValue(), shortValue() e byteValue().**

### Trabalhando com os construtores Wrappers

Nos construtores Wrappers apenas a classe Character não fornece dois construtores, sendo que as demais aceitam dois construtores. A Listagem 1 mostra como funciona na prática a declaração desses construtores.

**Listagem 1**. Representação dos construtores de algumas classes Wrapper.

```java
 public class TestaWrapper {
     public static void main(String[] args) {
   
     String numInt = "9822";
     
     //Representação em String do tipo que está sendo criado
     Float fNum1 = new Float("500.50");
     Integer iNum1 = new Integer(numInt);
     Double dNum1 = new Double("512.22");
     
     //o argumento somente aceita do tipo char, por isso que é usado aspas simples
     Character cNum = new Character('a');
     
     //Criação do tipo primitivo natural
     Float fNum2 = new Float(500.50);
     Integer iNum2 = new Integer(2800);
     Double dNum2 = new Double(512.22);
     
     System.out.println("Float representadopor string: "+fNum1);
     System.out.println("Float natural: "+fNum2);
     System.out.println("Integer representado por string: "+iNum1);
     System.out.println("Char: "+cNum);
     }
}
```
Nos argumentos wrappers Boolean podem ser usados valores como: true, false ou String. Um ponto de observação é que os valores declarados dentro do construtor não diferencia as letras maiúsculas de minúsculas. A Listagem 2, gera um amostra do que foi explicado acima. Seria interessante,tentar adivinhar qual seria a saída dos valores antes de tentar reproduzir para compreender o entendimento.



**Listagem 2**. Representação dos construtores de classes WrapperBoolean.

```java
public class TestaWrapperBoolean {
    public static void main(String[] args) {
    boolean flag1 = true;
    boolean flag2 = false;
    String flag3 = "true";
   
    Boolean b1 = new Boolean("truE");
    Boolean b2 = new Boolean("TRUE");
    Boolean b3 = new Boolean("TuE");
    Boolean b4 = new Boolean(flag3);
 
    if(b1){
        System.out.println("B1 é verdadeiro!");
    }
     
    if(flag1 == b2){
        System.out.println("flag1 == b2: Igual");
    }else{
        System.out.println("flag1 == b2: Diferente");
    }
 
    System.out.println(flag1 == b1 ? "flag1 == b1: Igual" : "flag1 == b1: Diferente");
    System.out.println(flag1 == b3 ? "flag1 == b3: Igual" : "flag1 == b3: Diferente");
    System.out.println(flag1 == b4 ? "flag1 == b4: Igual" : "flag1 == b4: Diferente");
     
    Boolean b5 = new Boolean("false");
    Boolean b6 = new Boolean("faLse");
    Boolean b7 = new Boolean("FALSE");
    Boolean b8 = new Boolean("flse");
     
    System.out.println(flag2 == b5 ? "flag2 == b5: Igual" : "flag2 == b5: Diferente");
    System.out.println(flag2 == b6 ? "flag2 == b6: Igual" : "flag2 == b6: Diferente");
    System.out.println(flag2 == b7 ? "flag2 == b7: Igual" : "flag2 == b7: Diferente");
    System.out.println(flag2 == b8 ? "flag2 == b8: Diferente" : "flag2 == b8: Igual" );
    }
}

```
**Saida:**

B1 é verdadeiro!
flag1 == b2: Igual
flag1 == b1: Igual
flag1 == b3: Diferente
flag1 == b4: Igual
flag2 == b5: Igual
flag2 == b6: Igual
flag2 == b7: Igual
flag2 == b8: Diferente

Em caso de estudo, a Tabela  mostra todas as classes Wrapper com suas características definidas quando usadas no construtor.

| **Tipo primitivo** | **Classe Wrapper** | **Argumentos do construtor** |
| ------------------ | ------------------ | ---------------------------- |
| **boolean**        | Boolean            | booleanou String             |
| **byte**           | Byte               | byte ou String               |
| **char**           | Character          | char                         |
| **int**            | Integer            | int ou String                |
| **float**          | Float              | float, double ou String      |
| **double**         | Double             | double ou String             |
| **long**           | Long               | long ou String               |
| **short**          | Short              | short ou String              |