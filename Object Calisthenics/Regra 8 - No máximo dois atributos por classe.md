[[00obj]]
**Descrição:** Limite a carga de informações de uma classe para manter a Coesão. **Problema:** Classes com muitos atributos tornam-se difíceis de testar e manter, violando o Encapsulamento. **Então/Pense:** Agrupe atributos que fazem sentido juntos em novos Objetos de Valor.

Uma classe não deve carregar responsabilidades demais ao mesmo tempo. O ideal é agrupar as propriedades que fazem sentido estarem juntas em novas abstrações.

**❌ Exemplo ruim:**

```java
public class Pessoa {
    private String nome;
    private int idade;
    private String email;
    private String telefone;
    private String endereco;
}
```

- **Problemas:** Esta classe "sabe" de muita coisa, quebrando o Encapsulamento e a Responsabilidade Única (SRP). Ela tende a crescer desordenadamente (ferindo o princípio _Open/Closed_) e torna-se difícil de testar e manter.

**✅ Exemplo bom:**

```java
public class Pessoa {
    private Nome nome;
    private int idade;
    private Contato contato;
    private Endereco endereco;
}

public class Nome {
    private String primeiroNome;
    private String sobrenome;
}

public class Contato {
    private String email;
    private String telefone;
}
```

- **Vantagens:** Cada classe possui um propósito único e nenhuma delas tem atributos em excesso. O código torna-se muito mais coeso e organizado, pois tudo está em seu devido lugar.

**Conclusão:** Ao identificar que uma classe está acumulando muitos campos, extraia grupos de dados relacionados para novas classes (Value Objects). Isso facilita a reutilização e isola as validações de cada dado.