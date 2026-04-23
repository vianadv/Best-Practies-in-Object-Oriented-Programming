[[00ddd]]
A Linguagem Ubíqua é o idioma compartilhado e comum entre desenvolvedores e especialistas de domínio. O objetivo é eliminar a "tradução mental" entre o técnico e o negócio.
Ajuda a eliminar falhas de comunicação. Se o dono da empresa usa o termo "Apólice", esse termo deve aparecer no código, nas variáveis e no banco de dados, evitando "traduções" mentais constantes entre o técnico e o negócio

**Diretrizes:**

- Se o especialista de negócio utiliza o termo "Apólice", este deve ser o nome da classe, da variável e da tabela no banco, não "Contrato" ou "Documento".
- **Exemplo 1:** Utilizar `EfetuarRenovacao()` em vez de um método genérico `AtualizarStatus(4)`.
- **Exemplo 2:** No e-commerce, o método deve se chamar `FecharPedido()`, refletindo exatamente o termo usado pelos atendentes.
-  **De Forma Simples:** Todo mundo no projeto deve usar as mesmas palavras. Se o cliente diz "Venda", o programador escreve "Venda" no código.