A coesão é o princípio que determina que uma classe deve possuir apenas responsabilidades e atributos que sejam estritamente pertinentes à sua natureza. Uma classe coesa é focada e evita a dispersão de lógica.

**Exemplo Prático de Violação:** Em uma classe `Aluno`, não é admissível a existência do atributo `corDaCaneta` ou do método `lançarNota()`. O ato de lançar notas é uma responsabilidade administrativa ou do docente, não do objeto aluno. Se uma classe valida dados, persiste informações no banco e executa regras de negócio simultaneamente, ela carece de Coesão e deve ser refatorada.

[[00fundamentos]]