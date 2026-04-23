
**Nome Completo:** Interface Segregation Principle (Princípio da Segregação de Interface).

**Explicação Técnica:** Uma classe não deve ser compelida a depender de métodos que não utiliza. Interfaces "gordas" (com excesso de métodos) devem ser divididas em interfaces menores e específicas, evitando que classes implementadoras carreguem métodos inúteis.

**Exemplos Práticos:**

1. **Cenário 1:** Decompor uma interface `IMultifuncional` em `IImpressora` e `IScanner`. Uma impressora básica não deve ser forçada a implementar lógica de digitalização.
2. **Cenário 2:** Separar uma interface de `Trabalhador` em `IRealizaTarefa` e `IAlimentacao`, garantindo que um robô não precise implementar métodos de refeição.

**De Forma Simples:** Não obrigue ninguém a aceitar um "pacote completo" se a pessoa só quer usar uma coisa. Dê a ela apenas o que ela precisa.

[[00solid]]