# ** Aula 14 - Pacotes Java**

Pacotes Java são utilizados para organizar as classes da sua aplicação. Um programa pode, facilmente, ter mais de centenas de classes. Então é muito importante que todos os seus componentes fiquem organizados. Podemos pensar nos pacotes como uma pasta do seu sistema de arquivos.

Vamos imaginar uma loja que possui filiais em várias cidades. Para guardar essas informações foi criado pacote `br.com.loja` e a classe `Filial` que possui uma variável de classe chamada `cidade`.

A ilustração abaixo mostra um pacote com uma classe dentro e a estrutura de arquivos gerada pelo pacote:

![](http://high5devs.com/wp-content/uploads/2015/01/1.png)

A classe `Filial` está dentro do pacote `br.com.loja`.

Observe abaixo a definição da classe `Filial`:

```java
package br.com.loja;
 
public class Filial {
    private String cidade;
 
    public String getCidade() {
        return cidade;
    }
 
    public void setCidade(String cidade) {
        this.cidade = cidade;
    }
}
```

Repare o uso da instrução `package br.com.loja`. É ela que diz que a classe `Filial` está dentro do pacote `br.com.loja`.

Essa loja faz uso de transportadoras para movimentar cargas entre as filiais. Vamos criar um pacote chamado `br.com.transporte` para guardar a classe `Transportadora`. Essa classe possui o método `transportar` que recebe dois argumentos do tipo `Filial`, um será o remetente e o outro o destinatário.

![](http://high5devs.com/wp-content/uploads/2015/01/2.png)

Agora nós temos dois pacotes distintos. Cada um deles possui uma classe.

Veja o conteúdo da classe `Transportadora`:

```java
package br.com.transporte;
 
public class Transportadora {
 
    public void transportar(br.com.loja.Filial remetente, br.com.loja.Filial destinatario)
    {
        //Movimentar carga do remetente para o destinatário
    }
 
}
```

Perceba que para fazer referência ao tipo `Filial` que está dentro do pacote `br.com.loja`, nós tivemos que usar o nome completo da classe `Filial`, `br.com.loja.Filial`. Podemos usar a instrução import para usar apenas o nome `Filial` nos argumentos do método `transportar`:

```java
package br.com.transporte;
 
import br.com.loja.Filial;
 
public class Transportadora {
 
    public void transportar(Filial remetente, Filial destinatario)
    {
        //Movimentar carga do remetente para o destinatário
    }
 
}
```

A instrução `import` do código anterior apenas importou a classe `Filial` do pacote `br.com.loja` para ser utilizada. Mas também podemos importar todas as classes de um pacote de uma única só vez.

## **Importar classes individuais e pacotes inteiros**

É possível importar apenas uma classe por vez ou todas as classes de um pacote. Observe os pacotes e classes ilustradas abaixo:

![](http://high5devs.com/wp-content/uploads/2015/01/3.png)

O pacote `br.com.loja` contém a classe `Filial` e o pacote `br.com.loja.produto`. O pacote `br.com.loja.produto` contém duas classes: `Eletrica` e `Hidraulica`. O pacote `br.com.transporte` também contém duas classes: `Transportadora` e `Filial`.

Veja a estrutura de arquivos gerada na ilustração abaixo:

![](http://high5devs.com/wp-content/uploads/2015/01/4.png)

Para importar uma classe individualmente utilizamos o comando `import`. Podemos usar esse comando várias vezes dentro do nosso arquivo `java`. Vamos importar as classes `Eletrica` e `Hidraulica` do pacote `br.com.loja.produtos` e a classe `Filial` do pacote `br.com.loja` para o arquivo `Transportadora.java` do pacote `br.com.transporte`:

```java
package br.com.transporte;
 
import br.com.loja.Filial;
import br.com.loja.produto.Eletrica;
import br.com.loja.produto.Hidraulica;
 
public class Transportadora {
 
    public void transportar(Filial remetente, Filial destinatario) {
        // Movimentar carga do remetente para o destinatário
    }
 
}
```

Para importar todas as classes de um pacote também utilizamos o comando `import`, mas agora fazemos o uso do `*`. Para importar todas as classes do pacote `br.com.loja.produto`:

```java
import br.com.loja.produto.*
```

O código abaixo continua importando as classes `Filial`, `Eletrica` e `Hidraulica`. A diferença é que usamos o `*` para importar todas as classes do pacote `br.com.loja.produto`.

```java
package br.com.transporte;
 
import br.com.loja.Filial;
import br.com.loja.produto.*;
 
public class Transportadora {
 
    public void transportar(Filial remetente, Filial destinatario) {
        // Movimentar carga do remetente para o destinatário
    }
}
```

É muito importante saber que o `*` apenas importa todas as classes do pacote. Ele não importa as classes de sub-pacotes. Portanto, embora o pacote `br.com.loja.produto` esteja localizado dentro do pacote `br.com.loja`, o comando `import br.com.loja.*` irá importar apenas a classe `Filial`.

## **Classes com nomes iguais**

Não podemos ter Classes com o mesmo nome dentro do mesmo pacote, mas podemos criar classes com o mesmo nome desde que estejam em pacotes diferentes. O uso dos pacotes evita a colisão de nomes. Observe a ilustração a seguir que mostra dois pacotes diferentes com classes com nomes iguais:

![](http://high5devs.com/wp-content/uploads/2015/01/5.png)

A classe `Filial` do pacote `br.com.transporte` não tem nenhuma relação com a classe `Filial` do pacote `br.com.loja` e são dois componentes diferentes dentro da aplicação.

Perceba a relação com o sistema de arquivos do seu computador. Nós também não podemos ter dois arquivos com o mesmo nome dentro de uma mesma pasta, mas se eles estiverem em pastas diferentes não ocorre problema algum. Veja a estrutra de arquivos demonstrada pela ilustração anterior abaixo:

![](http://high5devs.com/wp-content/uploads/2015/01/6.png)

Podemos pensar nos pacotes como o sobrenome e a classe como o nome das pessoas. Imagine uma sala de aula com dois alunos chamados João. Se você for chamar pelo João, duas pessoas irão atender ao seu pedido. Mas se você chamar pelo João Pedrosa, apenas uma pessoa irá responder.

![](http://high5devs.com/wp-content/uploads/2015/01/7.png)

Neste caso, João é o nome de duas classes que estão em pacotes diferentes: Pedrosa e Carvalho.