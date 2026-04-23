# 🚀 Boas Práticas em Engenharia de Software: POO, SOLID e Design Limpo

Este repositório é um compêndio dos meus estudos sobre como escrever código limpo, manutenível e de alta qualidade. Aqui, organizo conceitos fundamentais que vão desde os pilares da Programação Orientada a Objetos (POO) até regras rígidas de design de código e arquitetura.

## 🏛️ Fundamentos e Pilares

### Coesão e Responsabilidade
Uma classe deve realizar e possuir apenas aquilo que faz sentido para a sua própria existência. Se uma classe valida dados, guarda informações e executa regras de negócio ao mesmo tempo, ela está a fazer coisas a mais e deve ser dividida.

### Encapsulamento
Esconda os processos internos. Quem utiliza um método não precisa de saber como ele funciona "por baixo do capô", apenas como interagir com ele. Isso permite que a lógica interna mude sem quebrar os componentes externos.

### Acoplamento
O segredo é o **baixo acoplamento**. Devemos procurar sempre depender de abstrações estáveis (interfaces) em vez de implementações concretas que mudam frequentemente.

---

## 💎 Princípios SOLID

* **S - Single Responsibility:** Uma classe deve ter uma, e apenas uma, razão para mudar.
* **O - Open/Closed:** Entidades de software devem estar abertas para extensão, mas fechadas para modificação. Adicione novas funcionalidades criando novos ficheiros, não alterando os existentes.
* **L - Liskov Substitution:** Classes derivadas devem poder substituir as suas classes base sem quebrar o sistema.
* **I - Interface Segregation:** Nenhuma classe deve ser forçada a depender de métodos que não utiliza.
* **D - Dependency Inversion:** Dependa de abstrações, não de implementações. Módulos de alto nível não devem depender de módulos de baixo nível.

---

## 🏋️ Object Calisthenics (O "Treino" do Código Limpo)

Um conjunto de 9 regras rígidas para elevar o nível do design orientado a objetos:

1. **Apenas um nível de indentação por método:** Se tem um `if` dentro de um `for`, extraia o conteúdo para um novo método.
2. **Não use ELSE:** Utilize as técnicas de **Fail Fast** (lançar erros cedo) e **Early Return**. Se o código atinge um `return`, tudo o que está abaixo é ignorado.
3. **Envolva os tipos primitivos (Wrap Primitives):** Se um tipo de dado possui regras ou validações (como um CPF ou E-mail), ele merece a sua própria classe. **Se o dado tem uma regra, ele merece uma classe.**
4. **First-Class Collections:** Uma classe que contém uma coleção não deve ter nenhuma outra variável de instância.
5. **Um ponto por linha (Lei de Demeter):** Não converse com "estranhos". Evite correntes longas como `pedido.getCliente().getEndereco().getCidade()`. Use `pedido.getCidadeDoCliente()`.
6. **Não abrevie:** Economize confusão, não letras. Nomes claros evitam que as pessoas tenham de adivinhar o que o código faz.
7. **Mantenha as entidades pequenas:** Idealmente, mantenha as classes entre 50 a 200 linhas. Se não consegue explicar o que uma classe faz rapidamente, ela é demasiado grande.
8. **No máximo dois atributos por classe:** Isto força uma alta coesão e a criação de novas abstrações.
9. **Diga, não pergunte (Tell, Don't Ask):** Não use *getters* e *setters* para decidir o que fazer fora do objeto. Diga ao objeto o que fazer e deixe-o gerir o seu próprio estado.

---

## 🏗️ Domain-Driven Design (DDD)

* **Linguagem Ubíqua:** Desenvolvedores e especialistas de negócio devem falar a mesma língua no código.
* **Contexto Delimitado (Bounded Context):** O sistema deve ser dividido em áreas específicas onde os termos têm significados bem definidos.
* **Entidades vs Objetos de Valor (Value Objects):** Entidades têm uma identidade única (ID); Objetos de Valor são definidos pelos seus atributos e são imutáveis.
* **Agregados:** Um conjunto de objetos de domínio que podem ser tratados como uma unidade única para garantir a integridade dos dados.

---

> "A simplicidade é o último grau da sofisticação." — Leonardo da Vinci
