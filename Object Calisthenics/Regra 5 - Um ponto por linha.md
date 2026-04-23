Não converse com o amigo do amigo! É mais fácil conversar com o amigo diretamente (não fale com estranhos). Um método não deve conhecer a estrutura interna de outro objeto.

**❌ Forma errada:**

```java
String cidade = pedido.getCliente().getEndereco().getCidade();
```

- **Problemas:** Você sabe demais sobre os outros objetos (rompe o encapsulamento). Se mudar qualquer detalhe nessa cadeia, o restante quebra; o código fica frágil.

**✅ Forma correta:**

```java
public class Pedido {
    private Cliente cliente;

    public String getCidadeDoCliente() {
        return cliente.getCidade();
    }
}

public class Cliente {
    private Endereco endereco;

    public String getCidade() {
        return endereco.getCidade();
    }
}

// E agora você utiliza assim:
String cidade = pedido.getCidadeDoCliente();
```

- **Vantagens:** Apenas um ponto; código mais seguro; cada classe resolve seu próprio problema.

**Essa regra ajuda em:**

- Código mais fácil de dar manutenção;
- Encapsulamento;
- Baixo acoplamento.

**Exceção desta regra:** A única exceção ocorre quando você está **montando** ou **configurando** uma única coisa, como um personagem de videogame ou um sanduíche. Exemplo (Fluent Interface/Builder):

```java
Personagem.comCabeloAzul().comCapaPreta().comEspadaDeFogo().criar();
```

**Por que isso é permitido?** Porque você não está pulando de objeto em objeto (Mãe -> Chave -> Carro). Você está o tempo todo falando com o **mesmo objeto** (o Personagem), apenas adicionando "adesivos" nele.

- Se for para "bisbilhotar" o que tem dentro dos outros, é proibido.
- Se for para "personalizar" a mesma coisa, está liberado.

[[00obj]]