O encapsulamento refere-se à capacidade de ocultar os detalhes de implementação e os processos internos de um objeto, expondo apenas uma interface controlada (assinaturas de métodos) para o mundo externo.

**Analogia do Vídeo Game:** Ao jogar, você interage com o controle (a interface). Você não precisa conhecer os circuitos internos ou a arquitetura do processador para operar o sistema; você apenas utiliza as interfaces disponíveis.

**Benefícios Arquiteturais:**

- **Isolamento de Implementação:** Permite modificar a lógica interna de um método sem gerar impacto nos componentes externos que o consomem. Se múltiplos pontos do sistema utilizam um método, a alteração da lógica centralizada evita a necessidade de refatorar todos os consumidores.

[[00fundamentos]]