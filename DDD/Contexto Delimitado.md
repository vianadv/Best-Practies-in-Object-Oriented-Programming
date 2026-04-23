[[00ddd]]
Bounded Context estabelece fronteiras onde um modelo de domínio específico é soberano. Em sistemas de grande escala, uma mesma entidade pode ter significados distintos em contextos diferentes.
Em sistemas grandes, uma mesma palavra pode mudar de sentido. O "Produto" no estoque (peso, tamanho) é diferente do "Produto" na venda (preço, promoção). O DDD separa esses mundos para que um não complique o outro.

**Exemplos:**

- **Contexto de Vendas:** O "Produto" foca em preço e estratégias de promoção.
- **Contexto de Logística:** O "Produto" foca em dimensões, peso e estoque.
- O DDD isola esses modelos para que a complexidade de um não polua o outro.

**De Forma Simples:** Divida o sistema em salas. O que acontece na cozinha não precisa atrapalhar o que acontece na garagem.