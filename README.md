## Arquitetura Legada e Mapeamento de Débito Técnico (Technical Debt)

Este projeto foi desenvolvido na etapa inicial da minha formação acadêmica. Atualmente, a base de código serve como objeto de estudo para refatoração, separação de responsabilidades e aplicação de boas práticas em C. Abaixo está o mapeamento do débito técnico atual e o *roadmap* de resolução arquitetural:

* **[Problema Atual] Arquitetura Monolítica e Forte Acoplamento:** Todo o escopo do jogo (Game Loop, renderização gráfica, inputs lógicos e física) está concentrado em um único escopo de execução, resultando em um código monolítico de difícil manutenção.
* **[Solução Projetada] Modularização Procedural:** Refatoração do código para múltiplas unidades de compilação (separação em arquivos `.h` e `.c`). O objetivo é isolar a camada de abstração de hardware (Allegro) da camada de regras de negócio (Puzzles e Colisões).
* **[Problema Atual] Gestão de Estado Global:** Dependência de variáveis globais para controlar a pontuação, vida e status do jogador, quebrando o princípio de encapsulamento.
* **[Solução Projetada] Tipos Abstratos de Dados (ADTs):** Substituir as variáveis soltas por `structs` que representem o contexto do jogo e do jogador, passadas por referência (ponteiros) apenas para as funções que estritamente necessitam manipular esses dados.
