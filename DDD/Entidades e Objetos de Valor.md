[[00ddd]]
A distinção entre como identificamos os objetos no domínio.
Entidades são como pessoas (identificadas pelo CPF, mesmo que mudem o cabelo). Objetos de Valor são como uma nota de dinheiro (não importa qual nota é, desde que o valor seja o mesmo) e são sempre imutáveis.

|   |   |   |
|---|---|---|
|Característica|Entidade|Objeto de Valor (Value Object)|
|**Identidade**|Possui ID único (RG, CPF, Serial).|Definido apenas pela combinação de seus dados.|
|**Continuidade**|Mantém a identidade mesmo se os dados mudarem.|Se um detalhe muda, o objeto é substituído.|
|**Mutabilidade**|Geralmente mutável ao longo do ciclo de vida.|Sempre **Imutável**.|
|**Exemplos**|`Usuario` (ID 123), `Pedido` (Série 001).|`Endereco`, `Moeda`, `Preço`, `CPF`.|
Entidades têm "RG". Objetos de Valor são apenas informações que, se você mudar um detalhe, já viram outra coisa.