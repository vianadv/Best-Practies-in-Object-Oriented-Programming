[[00ddd]]
Agregados são agrupamentos de objetos relacionados que são tratados como uma única unidade para garantir a consistência dos dados e regras de negócio.

**A Raiz de Agregado:** É o ponto de entrada único do agregado. Nenhuma entidade externa pode manipular os objetos internos do agregado sem passar pela Raiz.

- **Exemplo 1:** Um `Pedido` e seus `Itens`. Você só adiciona itens através do `Pedido` para que ele valide o estoque total.
- **Exemplo 2:** Uma `ContaBancaria` e seu `HistoricoDeTransacoes`. O histórico não é alterado diretamente sem passar pela lógica da conta.

**De Forma Simples:** É como um kit fechado. Se você quer mudar algo dentro da caixa, tem que falar com o responsável pela caixa toda.