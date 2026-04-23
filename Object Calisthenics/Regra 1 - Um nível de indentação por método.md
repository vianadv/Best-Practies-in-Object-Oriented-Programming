[[00obj]]
**Descrição:** Cada método deve ter exatamente um nível de profundidade lógica. **Problema:** Métodos com múltiplos blocos aninhados (`if` dentro de `for`) são difíceis de ler e manter. **Então/Pense:** Extraia a lógica interna para novos métodos menores. Quanto mais o código "anda para a direita", maior a complexidade.

exemplo:
- exemplo violação dessa regra: 

nesse caso temos 2 níveis de identação (o for e depois o if)
```js
function imprimirContasVencidas(clientes) {
    for (let cliente of clientes) { // Nível 1
        if (cliente.temContasAtrasadas()) { // Nível 2 (Violação)
            console.log(cliente.nome);
        }
    }
}
```

para resolver formatamos a lógica desse método para mais outros métodos, deixando apenas um nível de identação em cada um, fazendo com que fique mais simples

```js
function imprimirContasVencidas(clientes) {
    for (let cliente of clientes) { // Nível 1
        notificarSeInadimplente(cliente);
    }
}

function notificarSeInadimplente(cliente) {
    if (cliente.temContasAtrasadas()) { // Nível 1
        console.log(cliente.nome);
    }
}

```

Então: extraia os métodos e os deixe mais legíveis, "quanto mais o método estiver andando pra direita" que dizer que ele esta grande demais...