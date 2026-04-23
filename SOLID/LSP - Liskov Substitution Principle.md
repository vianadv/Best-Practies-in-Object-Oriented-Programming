
**Nome Completo:** Liskov Substitution Principle (Princípio da Substituição de Liskov).

**Explicação Técnica:** Uma classe filha deve ser capaz de substituir sua classe base sem alterar a integridade do sistema. Isso significa respeitar rigorosamente os contratos: se a classe mãe define que um método retorna um `INT` de valor **positivo**, todas as filhas devem obrigatoriamente retornar um `INT` positivo. Se a classe filha lança uma exceção inesperada ou altera drasticamente o comportamento, o princípio é violado.

**O Caso da Ave/Pinguim:** Se a classe mãe `Ave` possui o método `voar()`, e a classe filha `Pinguim` herda de `Ave` mas lança uma exceção "Pinguins não voam", o contrato foi quebrado. A hierarquia correta exigiria a segregação em `AveQueVoa` e `AveQueNaoVoa`.

**Exemplos Práticos:**

1. **Cenário 1:** `ContaCorrente` e `ContaPoupanca` devem permitir operações de saque de forma consistente com o que é definido em `ContaBancaria`.
2. **Cenário 2:** Um `Quadrado` não deve herdar de `Retangulo` se a alteração da largura forçar uma mudança automática na altura, violando a expectativa de comportamento de um retângulo genérico.

**De Forma Simples:** Se você diz que algo é um "tipo de", ele tem que agir exatamente como o original em todas as situações básicas, sem dar erro onde o original não daria.

Se o código espera uma `Ave` e chama `voar()`, mas o `Pinguim` lança uma exceção "Pinguins não voam" ou retorna zero, você violou Liskov, pois o comportamento esperado da mãe foi quebrado.

[[00solid]]