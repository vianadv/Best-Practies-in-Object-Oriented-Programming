**Descrição:** O uso de `else` indica excesso de responsabilidade ou lógica mal estruturada. **Técnicas:**

- **Fail Fast:** Valide as condições de erro no início do método e lance exceções.
- **Early Return:** Retorne o resultado assim que a condição for satisfeita.

```csharp
// Exemplo Fail Fast / Early Return
public void Processar(Dados dados) {
    if (dados == null) throw new ArgumentException(); // Fail Fast
    if (!dados.Ativo) return; // Early Return
    
    // Logica principal sem necessidade de ELSE
}
```

**Então/Pense:** Sempre trabalhe com `return` e `continue`. Tenha em mente que, ao atingir um `return` ou `continue`, o código que está abaixo dele não será executado. Isso ajuda a evitar o uso do `else` e facilita a inversão ou modificação das validações. Além disso, sempre lance o erro antes de qualquer outra coisa, evitando processar toda a lógica que, no final, acabaria dando errado.

[[00obj]]