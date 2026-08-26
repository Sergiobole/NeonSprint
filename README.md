# GDD: Neon Sprint — Documento de Design de Jogo & Checklist

| Metadado | Detalhes |
| :--- | :--- |
| **Gênero** | Endless Runner / Plataforma 2D |
| **Plataforma** | PC / WebGL / Mobile |
| **Engine** | Unity 2D |
| **Status do Projeto** | Em Desenvolvimento |

---

## 1. Visão Geral e Objetivo
**Neon Sprint** é um jogo arcade de ritmo acelerado onde o jogador controla um corredor que se desloca automaticamente em um cenário contínuo. O objetivo é desviar de obstáculos saltando ou agachando, acumulando pontuação progressiva antes de colidir.

---

## 2. Core Loop (Ciclo de Jogo)
* **Avançar:** Cenário em movimento contínuo via Parallax simulando velocidade constante.
* **Reagir:** Tomada de decisão instantânea para pular barreiras baixas ou agachar sob obstáculos altos.
* **Pontuar:** Incremento proporcional de pontos baseado no tempo de vida e distância percorrida.
* **Falhar / Reiniciar:** Colisão imediata com obstáculo aciona tela de Game Over e salva o recorde.

---

## 3. Mecânicas Principais e Controles
* **Movimentação Automática:** A velocidade do mundo aumenta progressivamente a cada 15 segundos.
* **Pulo (Jump):** Tecla `Espaço` ou `Seta para Cima` (com suporte a pulo duplo opcional).
* **Agachamento (Slide/Duck):** Tecla `Ctrl` ou `Seta para Baixo`, reduzindo a hitbox do `BoxCollider2D`.
* **Persistência:** Registro local da maior pontuação atingida através de `PlayerPrefs`.

---

## 4. Roadmap de Desenvolvimento & Checklist de Conclusão

### Fase 1: Configuração Inicial e Cenário (Dias 1 e 2)
| Tarefa | Descrição Detalhada | Status | Concluído em |
| :--- | :--- | :---: | :---: |
| **Setup do Projeto Unity 2D** | Configurar resolução padrão (1920x1080), tags, layers e estrutura de pastas (`Scripts`, `Sprites`, `Prefabs`, `Scenes`). | [ ] Finalizado | ____/____/2026 |
| **Cenário Parallax (Fundo)** | Implementar camadas de background com scripts de repetição e velocidades diferenciadas para profundidade. | [ ] Finalizado | ____/____/2026 |
| **Piso e Colisores Base** | Criar Tilemap ou sprites para a plataforma de chão com `BoxCollider2D` e tag `"Ground"`. | [ ] Finalizado | ____/____/2026 |

### Fase 2: Personagem e Controles (Dias 3 e 4)
| Tarefa | Descrição Detalhada | Status | Concluído em |
| :--- | :--- | :---: | :---: |
| **Setup do Player GameObject** | Adicionar componentes `SpriteRenderer`, `Rigidbody2D` (Freeze Rotation Z) e `BoxCollider2D`. | [ ] Finalizado | ____/____/2026 |
| **Script de Pulo e GroundCheck** | Implementar força vertical e detecção precisa de contato com o chão via `Physics2D.OverlapCircle` ou Raycast. | [ ] Finalizado | ____/____/2026 |
| **Mecânica de Agachamento (Slide)** | Reduzir dinamicamente a altura/offset do `BoxCollider2D` ao acionar a tecla de agachar. | [ ] Finalizado | ____/____/2026 |

### Fase 3: Obstáculos e Sistema de Jogo (Dias 5 e 6)
| Tarefa | Descrição Detalhada | Status | Concluído em |
| :--- | :--- | :---: | :---: |
| **Prefabs de Obstáculos** | Criar variações de obstáculos rasteiros e aéreos com seus respectivos `BoxCollider2D` configurados como Trigger. | [ ] Finalizado | ____/____/2026 |
| **Spawner & Object Pooling** | Implementar rotina em loop para instanciar ou reaproveitar obstáculos em intervalos de tempo randômicos. | [ ] Finalizado | ____/____/2026 |
| **Detecção de Colisão e Morte** | Programar gatilho `OnTriggerEnter2D` para pausar o jogo e disparar o evento de derrota (*Game Over*). | [ ] Finalizado | ____/____/2026 |

### Fase 4: UI, Pontuação e Polimento (Dia 7)
| Tarefa | Descrição Detalhada | Status | Concluído em |
| :--- | :--- | :---: | :---: |
| **Interface de Pontuação (HUD)** | Integrar TextMeshPro para contagem de tempo/distância em tempo real e salvar Recorde com `PlayerPrefs`. | [ ] Finalizado | ____/____/2026 |
| **Painel de Game Over & Restart** | Criar tela com score final, recorde atual e botão de reinício recarregando a cena via `SceneManager`. | [ ] Finalizado | ____/____/2026 |
| **Ajustes Finais e Game Feel** | Calibrar velocidade de aceleração do mundo, gravidade e feedback sonoro/partículas ao saltar e colidir. | [ ] Finalizado | ____/____/2026 |
