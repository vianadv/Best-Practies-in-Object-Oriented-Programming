
**Nome Completo:** Dependency Inversion Principle (Princípio da Inversão de Dependência).

**Explicação Técnica:** Dependa de abstrações, não de implementações concretas. Violar este princípio frequentemente leva à violação do [[OCP - Open Closed Principle]].

1. **Alto Nível:** Regras de negócio (ex: Processar Venda).
2. **Baixo Nível:** Ferramentas e detalhes (ex: Persistência em Disco, Envio de E-mail).
3. **Abstração:** É o contrato/interface no meio do caminho (ex: "Serviço de Mensagem") não dependa de uma ferramenta para realizar a regra de negocio, dependa da abstração, se você depender da ferramenta, ao usar outra ferramenta, terá que refatorar o código inteiro para essa outra ferramenta, se você usar a abstração, a ferramenta terá que obrigatoriamente depender dessa abstração para funcionar, assim invertendo a dependência, para gravar no hd e enviar e-mail essas funcionalidades terão de seguir a abstração (serviço de mensagem), caso contrario eu teria que fazer uma logica para cada uma (violando também o Principio do aberto fechado)
4. **Abstração:** O contrato (Interface) que intermedeia os dois níveis. 

A regra de negócio não deve conhecer a ferramenta. Ao depender de uma interface (ex: `ServicoMensagem`), as ferramentas de baixo nível (WhatsApp, Email) devem se adaptar ao contrato da regra de negócio, e não o contrário.

**Exemplos Práticos:**

1. **Cenário 1:** Um serviço de pedidos consumindo uma interface `IPagamento` em vez de estar acoplado diretamente à classe `PayPal`.
2. **Cenário 2:** Uma classe `Carro` que depende de `IMotor`, permitindo a troca entre `MotorEletrico` e `MotorGasolina` sem qualquer alteração no código do `Carro`.

**De Forma Simples:** O sistema deve funcionar como uma tomada: não importa o que você liga nela, desde que o encaixe (a interface) seja o mesmo.

[[00solid]]