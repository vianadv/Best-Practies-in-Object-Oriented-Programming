[[00uml]]

# 1 - OQUE PENSAR ANTES DE COMEÇAR A DESENHAR QUALQUER CLASSE

Antes de começar a desenhar o diagrama de fato, pense em 2 perguntas base
## 1.1 - Que problema esse sistema resolve?

- Sistema de vendas?
- Sistema de RH?
- Sistema de biblioteca?
- Sistema de logística?
- Sistema acadêmico?

A classe em si só fará sentido depois de você reconhecer o processo e a lógica do negócio

*Antes de realizar o diagrama escreva um mini texto ou alguns parágrafos sobre tudo oque entendeu do problema(ex: qual é o sistema?, quem usa o sistema?, quais são os processos do sistema?, etc...)

## 1.2 - Quais são os substantivos e verbos do domínio?

Essa é uma estratégia que facilita muito a vida na hora que você bate o olho em alguns pontos do problema.

### Substantivos são candidatos a se tornarem uma classe

Separe todos os substantivos do texto e julgue separadamente de acordo com o contexto se cada um deve se tornar uma classe!

Exemplo de um sistema de vendas:
- Cliente
- Pedido
- Produto
- Pagamento
- Endereço
- Nota fiscal

**⚠️POREM NEM TODOS OS SUBSTANTIVOS TEM QUE NECESSARIAMENTE SEREM UMA CLASSE!!!**

### Verbos são candidatos a responsabilidades/métodos/relacionamentos

- Cliente **faz** pedido
- Pedido **contém** itens
- pagamento **quita** pedido
- nota fiscal **é gerada para** o pedido

# 2- COMO PENSAR NAS COISAS QUE NÃO ESTÃO ÓBVIAS

Ao modelar, devemos tentar enxergar as coisas que estão implícitas
- oque vai variar
- oque vai quebrar
- oque é exceção
- oque o usuário assume que existe porém não falou

## 2.1 - Pergunte sobre o ciclo de vida dos objetos

- Como nasce?
- Pode ser alterada?
- Pode ser cancelada?
- Pode ser removida?
- Tem estados?
- Quando deixa de existir?
- Quem cria?
- Quem pode modificar?

Exemplo: 
	Classe Pedido
	- nasce quando o cliente confirma a compra
	- Pode estar nos estados: EmAberto, Pago, Enviado ou Cancelado
	- Depois de faturar o pedido, o mesmo não pode mais ser editado

Essas perguntas revelam atributos de estado, regras de negócio, métodos relevantes, possíveis classes auxiliares (ex: StatusPedido)

## 2.2 - Pergunte sobre regras de negócio

- Um cliente pode ter vários pedidos? Ou apenas 1 por vez?
- Um pedido pode existir sem itens?
- Um produto pode ser vendido sem ter no estoque?
- Um pedido pode ter mais de um pagamento?
- Um funcionário pode ter mais de um cargo?

## 2.3 - Pergunte sobre responsabilidades

- Quem deve fazer isso?
- Quem deve saber disso?

Exemplo ruim
	- Pedido:
		- calcula imposto
		- gera boleto
		- envia e-mail
		- salva no banco
		- valida CPF
		- emite nota fiscal
Tudo isso em uma classe só é um sinal ruim

Exemplo melhor
- **Pedido** mantém seu estado e itens
- **CalculadoraImposto** calcula imposto
- **ServicoPagamento** processa pagamento
- **ValidadorCPF** valida CPF
- **EmissorNotaFiscal** emite NF
Isso leva a um modelo mais limpo e coeso

# 3 - COMO IDENTIFICAR UMA CLASSE

Uma classe normalmente representa:
- uma entidade importante do negócio
- algo que precisa guardar estado
- algo que participa da regra do sistema


# 4 - COMO DESCOBRIR CLASSES ESCONDIDAS

### Sinais de alerta!!

Quando você vê um relacionamento de muitos pra muitos, desconfie...
Muitas vezes cabe uma **classe intermediária** escondida ai no meio

	Exemplo 1:
		- Aluno <-> Disciplina
		Parece simples, mas normalmente existe:
			- MATRÍCULA!!!!
		Porque a matrícula pode ter:
			- data
			- status
			- nota
			- frequência
			- semestre
	Exemplo 2:
		- Pedido <-> Produto
		Na prática quase sempre existe:
			- ITEM PEDIDO!!!
		Porque ele guarda:
			- quantidade
			- preço
			- desconto
			- subtotal

Regra prática
	- Se o relacionamento tiver:
		- atributos próprios
		- estado próprio
		- histórico
		- regras específicas

Então provavelmente ele deveria virar uma classe...

# 5 - COMO REVISAR SE UMA CLASSE ESTÁ BOA

Checklist
- Ela tem uma responsabilidade clara?
- O nome dela representa algo no domínio?
- Os atributos e métodos fazem sentido nela?
- Ela não está fazendo coisas demais?
- Ela não está vazia demais?
- Ela não está assumindo responsabilidades de outra classe?

# 6 - ERROS COMUNS

### 6.1 - Modelar tela invés de negócio

Errado:
- TelaLogin
- BotaoSalvar
- FormularioCliente

Melhor:
- Usuário
- Autenticação
- Cliente
# 7 - COMO PENSAR MELHOR DURANTE A MODELAGEM

- O que é importante no domínio?
- O que precisa existir ao longo do tempo?
- Quem é responsável por isso?
- Quem se relaciona com quem?
- Quantos podem existir de cada lado?
- Há regras ou restrições?
- Há estados?
- Há exceções?
- Há tipos diferentes?
- Há relacionamentos que escondem uma classe?

# 8 - PASSO A PASSO PARA MODELAR

#### Passo 1: Ler o problema e destacar substantivos e verbos
#### Passo 2: Identificar o fluxo principal
- Cliente escolhe produtos
- Cliente faz pedido
- Pagamento é processado
- Pedido é enviado
#### Passo 3: Listar as entidades centrais
- Cliente
- Pedido
- Produto
- Pagamento
#### Passo 4: Descubra regras
- pode?
- quantos?
- quando?
- quem?
- é obrigatório?
#### Passo 5: Defina os relacionamentos
- quem conhece quem?
- quem contém quem?
- quem depende de quem?
#### Passo 6: Defina multiplicidades
#### Passo 7: Revise responsabilidades

Cada classe deve ter sua função clara!!!
#### Passo 8: Procure classes escondidas

**!!ESPECIALMENTE EM RELAÇÕES MUITOS PRA MUITOS!!!**
#### Passo 9: Simplifique

Remova:
- excesso de detalhes
- tecnicidades
- informações irrelevantes naquele nível
# 9 - RESUMO RÁPIDO DE REVISÃO

Ideia central
- Modelar bem não é desenhar classes
- É entender o domínio e distribuir responsabilidades corretamente

 O que observar
- entidades
- atributos
- comportamentos
- relacionamentos
- multiplicidades
- regras
- estados
- exceções
- variações
- classes escondidas
#### Perguntas de ouro

- **Quem deve saber isso?**  
- **Quem deve fazer isso?**