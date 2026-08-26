# Neon Sprint — Game Design Document (GDD)

> **Documento de Design de Jogo:** Endless Runner 2D (Foco em Simplicidade e Execução Rápida)

| Metadado | Detalhes |
| :--- | :--- |
| **Gênero** | Endless Runner / Plataforma 2D |
| **Plataforma** | PC / WebGL / Mobile |
| **Engine** | Unity 2D |
| **Escopo Estimado** | 1 Semana (Protótipo Funcional) |

---

## 1. Visão Geral e Objetivo

**Neon Sprint** é um jogo arcade de ritmo acelerado onde o jogador controla um corredor futurista que se desloca automaticamente em um ambiente cyberpunk. O objetivo é desviar de obstáculos saltando ou abaixando, acumulando a maior pontuação possível antes de colidir.

O foco deste projeto é manter a simplicidade técnica, utilizando controles responsivos e lógica direta sem sistemas complexos de física ou combate.

---

## 2. Core Loop (Ciclo de Jogo)

* **Avançar:** O cenário se move continuamente da direita para a esquerda, simulando corrida constante.
* **Reagir:** O jogador pressiona comandos para pular (obstáculos baixos) ou abaixar (obstáculos altos).
* **Pontuar:** O escore aumenta proporcionalmente ao tempo de sobrevivência e distância percorrida.
* **Falhar / Reiniciar:** A colisão com qualquer obstáculo resulta em tela de Game Over instantânea com exibição de recorde.

---

## 3. Mecânicas Principais e Controles

* **Movimento Automático:** A velocidade do mundo aumenta progressivamente a cada 15 segundos.
* **Pulo (Jump):** Tecla `Espaço` ou `Seta para Cima`. Permite transpor barreiras rasteiras. *(Opcional: Salto duplo para flexibilidade)*.
* **Agachamento (Slide/Duck):** Tecla `Ctrl` ou `Seta para Baixo`. Reduz temporariamente a altura do colisor do personagem para passar sob barreiras aéreas.
* **Persistência:** Registro automático do recorde máximo local via `PlayerPrefs`.

---

## 4. Roadmap de Desenvolvimento & Checklist

Cronograma estruturado para entrega do protótipo funcional em até 7 dias:

### Fase 1: Configuração Inicial e Cenário (Dias 1 e 2)
- [ ] **Criar Projeto Unity 2D:** Configurar resolução padrão (ex: 1920x1080) e pastas organizadas (`Scripts`, `Sprites`, `Prefabs`).
- [ ] **Cenário de Fundo (Parallax):** Configurar camadas de fundo (céu, prédios distantes, chão) movendo-se em velocidades diferentes.
- [ ] **Configurar o Chão (Ground):** Adicionar Tilemap ou sprite de chão com `BoxCollider2D` e tag `"Ground"`.

### Fase 2: Personagem e Controles (Dias 3 e 4)
- [ ] **Setup do Player:** Criar GameObject com `SpriteRenderer`, `Rigidbody2D` e `BoxCollider2D`.
- [ ] **Script de Movimento e Pulo:** Programar detecção de tecla de espaço e aplicação de força vertical com verificação de solo.
- [ ] **Mecânica de Agachamento:** Ajustar escala ou tamanho do `BoxCollider2D` ao segurar a tecla para baixo.

### Fase 3: Obstáculos e Sistema de Jogo (Dias 5 e 6)
- [ ] **Prefabs de Obstáculos:** Criar variações de obstáculos rasteiros e altos. Transformá-los em Prefabs reutilizáveis.
- [ ] **Script Spawner (Gerador):** Criar rotina em loop para instanciar obstáculos à direita da tela em intervalos de tempo aleatórios.
- [ ] **Sistema de Colisão e Morte:** Detectar colisão do player com obstáculos para congelar o jogo e acionar a tela de Game Over.

### Fase 4: UI, Pontuação e Polimento (Dia 7)
- [ ] **Interface de Pontuação (UI):** Adicionar TextMeshPro na tela mostrando o score atual e salvar recorde com `PlayerPrefs`.
- [ ] **Menu de Game Over:** Criar tela simples com botão de "Reiniciar" e pontuação final.
- [ ] **Testes e Ajustes Finais:** Ajustar gravidade, velocidade de corrida e hitbox para garantir fluidez e diversão.
