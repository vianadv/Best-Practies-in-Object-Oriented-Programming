[[00obj]]

| Antes                                    | Depois                                                      |
| ---------------------------------------- | ----------------------------------------------------------- |
| Lista de alunos solta na classe `Turma`. | Classe `Alunos` que gerencia a lista internamente.          |
| `Turma` manipula a lista diretamente.    | `Turma` interage com métodos da classe `Alunos`.            |
| Encapsulamento fraco.                    | Respeito ao Princípio SRP - Single Responsibility Principle |

Qualquer classe que contenha uma coleção não deve conter outras variáveis de membro; a única propriedade que a classe deve ter é essa coleção. Basicamente, se você tem uma `List`, por exemplo, ela deve "morar" em uma classe só dela, e essa classe não deve possuir mais nada além dessa lista.

**Exemplo de problema:** Na classe `Turma`, se tivermos uma `List<String> alunos` misturada com outros atributos, a classe acaba fazendo coisas demais, manipulando a lista diretamente e tratando-a apenas como um detalhe escondido.

**Forma correta:** Crie uma classe dedicada, como `Alunos`, onde a única responsabilidade é cuidar da lista.

```java
public class Alunos {
    private List<String> lista = new ArrayList<>();

    public void adicionar(String nome) {
        lista.add(nome);
    }

    public int quantidade() {
        return lista.size();
    }
}
```

Dessa forma, a classe cuida apenas da lista, e ninguém a altera externamente, respeitando o encapsulamento.

**Utilização em outra classe:** Quando outra classe, como `Turma`, precisar da coleção, ela utiliza o objeto `Alunos`:

```java
public class Turma {
    private Alunos alunos;
    
    public Turma() {
        this.alunos = new Alunos();
    }

    public void novoAluno(String nome) {
        alunos.adicionar(nome);
    }

    public int totalDeAlunos() {
        return alunos.quantidade();
    }
}
```

O objeto `alunos`, que armazena a lista, é instanciado no construtor da classe que deseja utilizá-lo. A lista não é alterada diretamente; tudo é feito via métodos do objeto `Alunos`, que gerencia as alterações internamente.

**Conclusão:** Cada classe passa a ter sua função bem definida, tornando o código mais organizado e fácil de entender. Portanto: se você tem uma lista de coisas, crie um "dono exclusivo" para ela que saiba contar e organizar os itens.

**Benefícios:**

- **Antes:** Lista "perdida" na classe; a classe faz tudo; código confuso.

- **Depois:** Lista com "casa" própria (respeitando o encapsulamento); cada classe com uma única responsabilidade (respeitando o princípio **S** do **SOLID**); código limpo.