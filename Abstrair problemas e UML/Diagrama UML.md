[[00uml]]
### Perguntas iniciais
**1. Quem existe?**
Procuro as coisas do enunciado.

*Ex: Curso, Professor, Aluno, Pedido, Produto*

**2. O que cada um sabe?**
Esses viram os atributos.
**3. O que cada um faz?**
Esses viram os métodos.
**4. O que muda por tipo?**
Se algo muda conforme o tipo, penso em herança/polimorfismo.
*Ex: CursoOnline e CursoPresencial*
**5. O que é só ligação?**
Se algo só conecta duas entidades, pode ser uma classe de associação.
*Ex: Matricula, ItemPedido*
**6. Isso é uma lista fechada de opções?**
Se só pode ter alguns valores definidos, penso em enum.
*Ex: StatusPedido, Turno, TipoCurso*
**7. Isso é um contrato de comportamento?**
Se várias classes fazem a mesma coisa de formas diferentes, penso em interface.
*Ex: PagamentoService, Notificavel*
**8. Existe uma base comum, mas incompleta?**
Se existe algo genérico que serve como base para outros tipos, penso em classe abstrata.
*Ex: Curso, Funcionario, Conta*

### Perguntas que eu faço

Quem são os personagens do problema?
O que cada um sabe?
O que cada um faz?
O que muda conforme o tipo?
O que é só ligação entre dois objetos?
Isso é uma lista fechada de opções?
Isso é um contrato de comportamento?
Existe uma base comum incompleta?


Regra de ouro
UML é consequência, não começo.
Primeiro eu separo os papéis. Depois eu desenho.

Sinal de erro
Se uma classe:

guarda dados
faz conta
decide regra
controla lista
representa vínculo

ela está fazendo coisa demais.

Resumo mental

Coisas -> Classes
Informações -> Atributos
Ações -> Métodos
Tipos diferentes -> Herança
Ligações -> Associação / Classe associativa
Opções fixas -> Enum
Mesmo comportamento em classes diferentes -> Interface
Base comum incompleta -> Classe abstrata
