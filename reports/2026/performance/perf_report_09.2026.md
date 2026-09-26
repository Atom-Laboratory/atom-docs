# Relatório Executivo de Status — ATOM Chess

**Data:** 26/09/2026  
**Objetivo:** apresentar a situação atual do desenvolvimento do ATOM Chess, o avanço em direção ao MVP, os principais bloqueios e o nível de participação observado dos membros no ciclo atual.

## Visão geral

O ATOM Chess possui atualmente uma quantidade relevante de funcionalidades desenvolvidas ou em fase de revisão nos três principais eixos do projeto: **Visão Computacional, Chess Core e Movimento/Robótica**.

No entanto, o principal problema neste momento deixou de ser a ausência de desenvolvimento isolado. O gargalo está na **conclusão, integração e merge das funcionalidades já implementadas**.

Atualmente existem **10 Pull Requests abertos**, vários deles desde julho e agosto. Não houve novo PR nem merge na última semana analisada. Além disso, os PRs não possuem uma rotina de CI no GitHub executando automaticamente build e testes.

Isso significa que o projeto possui trabalho técnico produzido, porém uma parcela significativa ainda não chegou à branch `main`.

### Situação geral do MVP

**Desenvolvimento de componentes:** 🟡 Em andamento  
**Integração entre componentes:** 🔴 Atrasada  
**Testes automatizados/CI:** 🔴 Insuficiente  
**Visão Computacional:** 🟡 Parcialmente implementada  
**Chess Core:** 🟡 Avançado, mas bloqueado por PRs pendentes  
**Movimento/Robótica:** 🟡 Em desenvolvimento  
**Pipeline completo Vision → Chess → Stockfish → Motion:** 🔴 Ainda não consolidado

O risco principal para o cronograma é o crescimento de dependências entre PRs ainda não integrados.

---

## 1. Chess Core

A parte de Chess Core apresenta um dos maiores volumes de desenvolvimento, mas também concentra dependências importantes.

O **PR #85, de Gabriel Augusto**, centraliza o estado oficial do tabuleiro dentro de `acchess`, incluindo `Board`, `Piece`, `Square`, `Move`, comparação entre estados e aplicação de movimentos.

Esse PR é atualmente uma peça central da arquitetura e deveria ser tratado como prioridade de integração, pois outras implementações estão sendo construídas sobre ele.

**Carlos Caetano** desenvolveu o **PR #105**, responsável pela validação de movimentos. O trabalho possui uma quantidade significativa de testes, mas precisa ser alinhado ao estado completo da partida, principalmente para regras dependentes de histórico como roque e en passant.

**João** desenvolveu o **PR #114**, expandindo o `FenGenerator` para produzir os seis campos completos do padrão FEN. A implementação é importante para a integração correta com Stockfish, porém ainda precisa ser conectada à atualização automática do estado após cada movimento.

Em resumo, o Chess Core está tecnicamente próximo de formar uma base consistente, mas precisa que #85, #105 e #114 sejam consolidados em uma única linha arquitetural.

---

## 2. Visão Computacional

A equipe de visão possui diversas iniciativas em paralelo.

**Gabriel Augusto** é atualmente o principal responsável por várias dessas frentes, com os PRs:

- **#110:** dataset e infraestrutura de benchmark do PieceDetector;
- **#112:** separação entre `BoardObservation` da visão e o estado oficial do Chess Core;
- **#113:** calibração opcional das cores das peças.

O PR #112 segue uma direção arquitetural importante: a visão deve apenas informar o que foi observado, enquanto o Chess Core mantém o estado oficial da partida.

O PR #110 adicionou um dataset com **57 imagens reais**, o que é um avanço relevante para validação experimental. Entretanto, o benchmark ainda não executa efetivamente o `PieceDetector`: a saída atualmente utiliza uma FEN fixa para testar a infraestrutura de comparação. Portanto, ainda não existem métricas confiáveis de acurácia da visão.

O PR #113 introduz calibração em HSV, porém a calibração ainda não é persistida para utilização posterior pela pipeline.

**João**, através do **PR #116**, também está corrigindo o tratamento de intensidade de imagens da câmera e adicionando testes sem dependência direta do hardware.

A prioridade nesta frente deve ser transformar o dataset já construído em um benchmark real e mensurável.

---

## 3. Movimento e Robótica

Na frente de movimento existem duas implementações importantes aguardando consolidação.

**Marcio Otavio** está responsável pelo **PR #107**, relacionado ao sistema de `Graveyard` para armazenamento das peças capturadas. A nova implementação passou a organizar as peças considerando cor e tipo, aproximando o sistema do comportamento físico necessário para o robô.

Durante a revisão foi encontrada uma regressão na trajetória de captura: a nova implementação fecha a garra antes de atingir corretamente a peça. Esse comportamento precisa ser corrigido antes do teste em hardware.

**Pedro Lucas** desenvolveu o **PR #109**, responsável pelo `CoordinateMapper`, que converte casas como `E2` em coordenadas físicas do robô.

A ideia matemática está adequada ao problema, mas a implementação precisa ser movida da área de visão para o módulo de movimento e integrada diretamente com o sistema de coordenadas físico do SCARA e do Graveyard.

A Issue **#56 — Controle de Motores**, atribuída a **Eduardo**, continua sendo uma etapa importante para que o planejamento deixe de ser apenas computacional e resulte em movimento físico.

Ainda falta consolidar a cadeia:

`Move → posição física → trajetória → cinemática → controle dos motores`.

---

## 4. Engenharia, testes e integração

**Carlos Caetano**, através do **PR #106**, está trabalhando na integração dos testes ao CTest e na possibilidade de executar os módulos em ambiente headless.

Esse trabalho é especialmente importante porque atualmente os PRs não possuem CI automatizado reportando status no GitHub.

A recomendação é utilizar o PR #106 como base para estabelecer imediatamente uma pipeline de CI executando:

`configure → build → unit tests → integration tests`.

Sem isso, cada PR depende de validação manual do desenvolvedor ou reviewer, aumentando o risco de regressões entre módulos.

Também existem mais de 30 branches no repositório, enquanto apenas 10 possuem PR aberto. Parte delas corresponde a trabalho antigo ou já integrado e deve ser revisada e removida para reduzir ruído operacional.

---

## 5. Participação observada da equipe

Para acompanhamento gerencial, foi adotado o seguinte indicador:

**🟢 Alta:** atuação frequente com entregas e/ou reviews relevantes.  
**🟡 Moderada:** existe responsabilidade ou entrega ativa, mas com baixa frequência recente ou pendências relevantes.  
**🔴 Baixa no período:** pouca atividade observável recente no GitHub em relação às responsabilidades atribuídas.  
**⚪ Sem dados suficientes:** não há evidência suficiente no GitHub para avaliação do período.

O indicador considera apenas atividade verificável no repositório e não deve ser interpretado isoladamente como avaliação acadêmica ou profissional.

| Membro | Participação observada | Situação atual |
|---|---|---|
| **Enzo Ribas** | 🟢 Alta | Forte atuação em arquitetura, coordenação e code review. É atualmente um dos principais pontos de decisão e aprovação dos PRs, mas isso também concentra parte do fluxo de integração. |
| **Gabriel Augusto de Sousa Lima** | 🟢 Alta | Maior volume recente de PRs abertos: #85, #110, #112 e #113. Atua principalmente em Chess Core e Visão. O próximo passo é converter volume de implementação em PRs efetivamente integrados. |
| **Carlos Caetano** | 🟢 Alta | Responsável por #105 e #106, duas frentes estruturalmente importantes: validação de movimentos e infraestrutura de testes. Possui pendências de review a resolver antes da integração. |
| **João (`Joaoavr`)** | 🟢 Alta | Responsável por #114 e #116, além de participação em reviews. Atua diretamente em FEN/estado do jogo e câmera. |
| **Marcio Otavio** | 🟢 Alta | Responsável pelo #107 e também realizou revisão de outros PRs. A entrega do Graveyard é importante para o MVP físico, mas precisa corrigir a regressão identificada na trajetória. |
| **Pedro Lucas** | 🟡 Moderada/Alta | Responsável pelo CoordinateMapper (#109) e participou de reviews. Existe entrega concreta, mas o PR precisa de reorganização arquitetural e testes antes de avançar. |
| **Rafael Alves** | 🟡 Moderada | Participação recente observável principalmente através de revisão e aprovação do PR #112. |
| **Paulo (`pmmc026`)** | 🟡 Moderada/Baixa no período | Está solicitado como reviewer em PRs importantes, incluindo #105, #107 e #114, mas há reviews pendentes. Pode contribuir diretamente para reduzir o backlog de revisão. |
| **Eduardo (`Edudx890`)** | 🟡 Moderada/Baixa no período | Possui responsabilidade relevante em Controle de Motores (#56) e revisão do #107, porém há pouca atividade recente observável no GitHub nessas frentes. |
| **MojoRoot** | 🔴 Baixa no período | Está envolvido em tarefas de movimento e solicitado em review, mas ainda há pouca movimentação observável nas responsabilidades. |
| **Walenkildely** | 🔴 Baixa no período | Está atribuído à execução de movimento (#58), mas não foi identificada atividade recente significativa no