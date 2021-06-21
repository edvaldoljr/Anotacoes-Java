# Aula 3 - Conhecendo as variáveis:

Variáveis são contêineres para armazenar valores de dados.
Todo nome de variável começa com letra minúscula e as próximas com letra maiúscula.  Ex : nomeAluno;

- #### Declarando (criando) variáveis

  ##### Sintaxe : tipo variável = valor;

  ## TEMOS 8 TIPOS PRIMITIVOS DE VARIAVEIS.
  
  ### Tipos Primitivos: Números inteiros
  
  | **Tipo** | **Tamanho (bits)** | **Faixa**        | **Valor Padrão** |
  | -------- | ------------------ | ---------------- | ---------------- |
  | byte     | 8                  | -128 a 127       | 0                |
  | short    | 16                 | -32.768 a 32.767 | 0                |
  | int      | 32                 | -231 a 231 – 1   | 0                |
  | long     | 64                 | -263 a 263 -1    | 0L               |
  
  ### Tipos Primitivos: Números de Ponto Flutuante
  
  | Tipo   | Tamanho (bits) | Faixa                                                        | Valor Padrão |
  | ------ | -------------- | ------------------------------------------------------------ | ------------ |
  | float  | 32             | IEEE 754 ±1,40129846432481707e-45 a 3,40282346638528860e+38  | 0.0f         |
  | double | 64             | IEEE 754 ±4,94065645841246544e-324 a 1,79769313486231570e+308 | 0.0          |
  
  As variáveis do tipo double armazenam valores com maior magnitude e precisão do que as do tipo float, e devem ser preferivelmente empregadas quando a precisão do valor for um fator importante.
  
  
  
  ### Tipos Primitivos: Caracteres – char
  
  O tipo char permite armazenar um caractere Unicode, utilizando para isso 16 bits.
  
  Seu valor mínimo é ‘\u0000’ (ou 0), e seu valor máximo é ‘\uffff’ (ou 65535).
  
  O Unicode é um padrão da indústria para representar dados relacionados a texto, incluindo letras, símbolos e caracteres especiais. Valor padrão para o tipo char: ‘\u0000’
  
  Podemos armazenar um conjunto de caracteres usando um tipo especial de referência denominado **String** (que é na verdade uma classe), o qual será visto posteriormente.
  
  ### Tipos Primitivos: boolean
  
  O tipo boolean permite armazenar um valor lógico nos estados **True** ou **False** (verdadeiro ou falso), ocupando apenas 1 bit de espaço.
  
  Valor padrão para o tipo boolean: false

```java
package aulasjava;
public class ConhecendoVariaveis {
    public static void main(String[] args) {
     boolean casadoVerdadeiro = true;
     boolean solteiroFalso = false;
     char caractere = 'A';
     char caractereHexadecimal = '\u0041';
     String nomeAluno = "Edvaldo";
     byte idadeByte = 127;
     short idadeShort = 32767;
     int idadeDoAluno = 2147483;
     long numeroGrande = 263;
     float pontoFlutuante = 3.40282346638528860e;
     double pontoFlutuanteDobroDeCapacidade = 1.79769313486231570e;
    }
}
```


​        

