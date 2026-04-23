
**Nome Completo:** Single Responsibility Principle (Princípio da Responsabilidade Única).

**Explicação Técnica:** O fato de ser tecnicamente possível inserir qualquer lógica em qualquer classe não justifica tal prática. Cada classe ou arquivo deve possuir apenas uma única razão para mudar, focando exclusivamente em um assunto ou funcionalidade dentro do domínio.

**Exemplos Práticos:**

1. **Cenário 1:** Uma classe `GeradorDeRelatorio` cuja única função é a formatação de texto, separada de uma classe `RelatorioRepository` que lida estritamente com a persistência de dados.
2. **Cenário 2:** Uma classe que gerencia o estado e dados de um `Usuario` operando de forma independente da classe `AutenticacaoService`, que é responsável apenas pela validação de credenciais.

**De Forma Simples:** Cada arquivo deve cuidar de apenas um assunto. Se misturar, você acaba quebrando o que estava funcionando ao tentar consertar outra coisa.

[[00solid]]