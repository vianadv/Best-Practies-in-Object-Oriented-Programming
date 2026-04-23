[[00obj]]
Os objetos devem realizar ações e comportamentos, em vez de simplesmente entregar seus dados internos para que outros decidam por eles (o que configura uma quebra de encapsulamento).

Utilizar excessivamente _getters_ e _setters_ é, na prática, quase o mesmo que deixar a informação pública. Em vez disso, crie métodos que façam sentido e que possuam um significado real para o domínio do sistema.

### Princípio "Tell, Don't Ask" (Diga, não pergunte)

Este princípio estabelece que devemos dizer ao objeto o que ele deve fazer, em vez de perguntar sobre seu estado interno para realizar uma validação externa.

**❌ Exemplo de violação (Perguntar e Validar fora):**

```java
// Código na classe Main utilizando o objeto "carro"
carro.setVelocidade(250);
if (carro.getVelocidade() >= carro.getVelocidadeMaxima()) {
    throw new Exception("Velocidade acima do permitido");
}
```

No código acima, estamos perguntando ao objeto e fazendo uma validação ao mesmo tempo, violando o _Tell, Don't Ask_.

**✅ Exemplo correto (Dizer ao objeto para agir):**

```java
// Dentro da classe Carro
public void acelerarAte(int velocidade) {
    if (velocidade > this.velocidadeMaxima) {
        throw new Exception("O carro não suporta esta velocidade");
    }
    this.velocidadeAtual = velocidade;
}

// Na classe Main, apenas damos a ordem:
carro.acelerarAte(250);
```

Desta forma, dizemos ao objeto o que fazer em vez de consultá-lo. O `Carro` resolve o problema com suas próprias regras, sem espalhar a lógica de negócio para fora da classe.

### Outros Exemplos Práticos:

- **Conta Bancária:** Se você chamar um `getSaldo()` e realizar a lógica de saque na `Main`, você está expondo detalhes internos e regras de negócio. O correto é dizer à conta para sacar: `conta.sacar(valor)`. Toda a validação acontece internamente na classe `ContaBancaria`, respeitando o encapsulamento.
- **Lâmpada:** Chame `lampada.ligar()` em vez de pegar o estado atual e mudar manualmente para "on".
- **Pontuação:** Utilize `pontuacao.adicionar(10)` em vez de fazer um `setScore(getScore() + 10)`

**Então/Pense:** Crie métodos que tenham significado e representem comportamentos reais do objeto no domínio.