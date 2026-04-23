[[00obj]]
**Descrição:** Nomes devem ser claros, completos e objetivos. Abreviações geram ambiguidade. **Problema:** O que é `CltMgr`? O que é `Usr`? **Então/Pense:** Se alguém precisar de uma explicação para entender o nome, ele está errado. Nomes excessivamente longos podem indicar violação do SRP - Single Responsibility Principle.

Escreva tudo de forma completa e objetiva, mesmo que o nome fique extenso. Não economize letras; economize confusão.

**❌ Código ruim:**
```java
public class CltMgr {
    private Usr usr;
    
    public void addUsr(Usr u) {
        usr = u;
    }
}
```

- **O que é `CltMgr`? `Usr` significa o quê?** Quem lê o código não deve ter que tentar adivinhar as intenções do autor. Nomes abreviados dificultam a manutenção e o entendimento imediato.

**✅ Código bom:**

```java
public class ClienteManager {
    private Usuario usuario;

    public void adicionarUsuario(Usuario usuario) {
        this.usuario = usuario;
    }
}
```

- **Dá para entender sem explicação:** Menos dor de cabeça e zero confusão para quem herdar esse código.

> **Conclusão:** Se alguém não conseguiu entender o nome de imediato, o nome está errado.

**💡 Análise Crítica:** É importante observar que, quando o nome de um método ou de uma variável está muito extenso, isso pode ser um sinal de alerta. Nomes exageradamente longos podem indicar que sua classe está assumindo responsabilidades que não lhe pertencem, rompendo o **Princípio da Responsabilidade Única (o "S" do SOLID)**. Se você precisa de muitas palavras para descrever o que uma coisa faz, talvez ela esteja fazendo coisas demais.