
**Nome Completo:** Open Closed Principle (Princípio do Aberto e Fechado).

**Explicação Técnica:** Entidades de software devem estar abertas para extensão, mas fechadas para modificação. Em vez de alterar o código-fonte de uma classe sempre que um novo requisito surge (como adicionar múltiplos `if/else` para diferentes redes sociais em uma classe `RedeSocialPost`), deve-se utilizar abstrações.

Invés de modicar a classe RedeSocialPost a cada nova atualização ou a cada nova rede social que queira adicionar, você pode criar uma classe abstrata ou interface, que ai sim tudo aquilo que você for adicionar de novidade, apenas estenda ou implemente a RedeSocialPost:

```java
//exemplo com classe abs:
public abstract class RedeSocialPost{
	public abstract void postar(String conteudo);
}

public class YoutubePost extends RedeSocialPost {
	@Override
	public void postar(String conteudo){
		sout("Post para o youtube: " + conteudo);
	}
}

public class FacebookPost extends RedeSocialPost {
	@Override
	public void postar(String conteudo){
		sout("Post para o facebook: " + conteudo);
	}
}

//exemplo com interfaces:
public interface RedeSocialPost{
	void postar(String conteudo);
}

public class YoutubePost implements RedeSocialPost {
    @Override
    public void postar(String conteudo) {
        System.out.println("🎥 YouTube: Enviando vídeo: " + conteudo);
    }
}

public class FacebookPost implements RedeSocialPost {
    @Override
    public void postar(String conteudo) {
        System.out.println("👥 Facebook: Postando no feed: " + conteudo);
    }
}

public class TwitterPost implements RedeSocialPost {
    @Override
    public void postar(String conteudo) {
        System.out.println("🐦 Twitter: Enviando Tweet: " + conteudo);
    }
}


```

- **Interfaces:** Utilizadas quando não há nada em comum além da assinatura do método (define _o que_ fazer).
- **Classes Abstratas:** Utilizadas para definir o contrato e, opcionalmente, fornecer uma base de funcionamento padrão, garantindo que as classes filhas sigam um padrão de base.

**Exemplos Práticos:**

1. **Cenário 1:** Um motor de cálculo de descontos onde novos tipos de desconto são implementados via interface `Desconto`, eliminando condicionais na classe principal.
2. **Cenário 2:** Um sistema de notificações que suporta novos canais (SMS, WhatsApp, Email) através de novas implementações de uma interface `Notificador`.

**De Forma Simples:** Você deve conseguir colocar funções novas no programa apenas adicionando arquivos novos, como se fossem "peças de encaixe", sem precisar apagar ou mudar o que já está pronto.

[[00solid]]