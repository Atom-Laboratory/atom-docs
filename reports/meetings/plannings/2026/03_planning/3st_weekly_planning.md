# ATA DA 1ª REUNIÃO DO GRUPO DE INICIAÇÃO CIENTÍFICA – BRAÇO ROBÓTICO

**Data da Reunião:** 08 de março de 2026

**Membros Presentes:**
- Eduardo do Amaral
- Pedro Lucas Vieira Ramalho
- Enzo Rocha Leite Diniz Ribas
- Paulo Macedo
- Carlos Caetano
- Yasmin Lourdes
- Moreno Jones
---

## Pautas Discutidas

### 1. **Overview do projeto**

- Overview do projeto Enzo apresentou o objetivo geral: em 2026 desenvolver um robô para jogar xadrez. O projeto tem duas partes principais — visão computacional para reconhecer o tabuleiro e peças e um braço robótico para executar as jogadas — usando o motor Stockfish como engine de decisão. O desenvolvimento será iterativo: começar com câmera fixa e robô parado, depois robô interagindo com o tabuleiro, e por fim câmera acoplada ao robô (mais complexo). Enzo mencionou que já vem trabalhando em modelagem CAD do braço e que essa reunião é a primeira após aprovação do projeto.

### 2. **Visão computacional (OpenCV) e integração com Stockfish**

- Visão computacional (OpenCV) e integração com Stockfish Discutiram usar OpenCV em C/C++ por conta do foco em embarcado e necessidade de otimização. A meta inicial é conectar uma câmera fixa ao OpenCV, detectar o tabuleiro, identificar peças e mudanças de posição e então enviar jogadas para o Stockfish. Há referências e implementações livres que podem ajudar; o time já tem códigos e o Guilherme esta fazendo benchmarks. Enzo destacou a importância de entender a teoria e não apenas copiar implementações prontas.

### 3. **Projeto e escolha do braço robótico (SCARA) — modelagem e modificações**

- Projeto e escolha do braço robótico (SCARA) — modelagem e modificações Enzo mostrou um modelo SCARA comprado na faixa dos R$60 e explicou por que escolheram SCARA (movimenta horizontalmente vindo de cima, evita derrubar peças e oferece precisão). Ele já está editando o CAD no Fusion, ajustando assemblies, limites de ângulo e planejando modificar a garra para adaptar câmera e componentes eletrônicos. Também planejam trocar cases e acomodar diferentes microcontroladores (ex.: S32, Banana Pi, Raspberry Pi) em vez do Arduino Uno.


### 4. **Simulação, equilíbrio e impressão 3D do braço**

- Simulação, equilíbrio e impressão 3D do braço Usando o software CAD/Simulação, Enzo mostrou o centro de massa e explicou que precisam ajustar contrapesos na base para evitar tombamento. A simulação ajudará a prever estabilidade para todos os movimentos. Algumas peças serão impressas; outras precisarão ser compradas. Enzo comentou já ter trabalhado no arquivo por mais de um mês e que Yasmin ajudou na modelagem.

### 5. **Hardware embarcado: benchmarks, dispositivos (Raspberry Pi / BananaPi) e otimização**

- Hardware embarcado: benchmarks, dispositivos (Raspberry Pi / BananaPi) e otimização Paulo trouxe preocupação sobre benchmarks usados e sugeriu rodar benchmarks específicos de CV em embarcados (papers/benchmarks que encontrou). Enzo disse que o time já tem três BananaPi e um Raspberry Pi e que Guilherme fez testes de benchmark (ainda não documentados). Discutiram otimizações para rodar OpenCV em embarcados (desabilitar módulos, rodar bare-bones, portar em C/C++), possibilidade de cluster improvisado e necessidade de rodar benchmarks contextualizados para decidir compra de hardware.

### 6. **Arquitetura do sistema e máquina de estados**

- Arquitetura do sistema e máquina de estados Enzo mencionou que há uma máquina de estados planejada para gerenciar decisões do robô e transições entre modos (por ex., reconhecimento, decisão, execução). Ainda não está definida a arquitetura completa do sistema; Guilherme deve contribuir com DevOps/integração. Paulo sugeriu pensar em arquitetura de soluções e integração contínua para testar comportamento em hardware.

### 7. **Planejamento por etapas (iterativo) e cronograma aproximado**

- Planejamento por etapas (iterativo) e cronograma aproximado O projeto está estruturado em etapas: (1) visão com câmera fixa e reconhecimento; (2) robô parado executando movimentos conforme decisões do OpenCV/Stockfish; (3) câmera acoplada ao robô (mais complexo). Enzo acha a etapa 1 a mais rápida; a etapa 2 será mais demorada devido ao braço. Propôs reuniões de planejamento mensais (último domingo do mês) e acompanhamento contínuo via grupo de chat.

### 8. **Distribuição de papéis, voluntariado e metodologia ágil (sprints/tarefas)**

- Distribuição de papéis, voluntariado e metodologia ágil (sprints/tarefas) Discutiram dividir funções por perfil (desenvolvedores OpenCV, modelagem CAD, montagem/print, DevOps/embarcados, QA, arquitetura). Paulo sugeriu uso de metodologia ágil: definir cargos/funcões, tarefas pequenas e sprints, com pessoas se voluntariando. Enzo listou interesses dos presentes (ex.: Yasmin e Ricardo em modelagem/impressão, Moreno interessado em desenvolvimento, Carlos interessado em Linux/DevOps, Paulo em arquitetura/QA). Também ficou a ideia de flexibilidade para as pessoas mudarem de função conforme demanda.

### 9. **Testes, QA e integração contínua **

- Foi enfatizado que testar em máquina desktop não garante desempenho no embarcado; é preciso validar no hardware real. Paulo sugeriu rodar benchmarks específicos e criar processos de QA que incluam testes frequentes no Raspberry/BananaPi. Enzo disse disponibilizar hardware na faculdade para que integrantes possam levar para casa e testar, e Guilherme lideraria questões de integração/DevOps.

### 10. **Testes, QA e integração contínua **

- Enzo comentou sobre experiência prévia com artigos e a intenção de produzir material acadêmico a partir do projeto (por exemplo, desenvolvimento do braço para xadrez e aplicação educacional). Paulo sugeriu estruturar planejamento para escrita. Moreno propôs também explorar aplicações em acessibilidade (por exemplo, permitir que pessoas com mobilidade usem o braço para jogar xadrez, até integrar com interfaces cérebro-computador futuramente). Enzo considerou essas ideias promissoras para artigos e apresentações em congresso.

---

## ENCAMINHAMENTOS
- **Documentar e compartilhar resultados dos benchmarks:**
   - Guilherme deve enviar os resultados e links das referências para validação.
   - Paulo e equipe rodar benchmarks específicos de CV em embarcados (Raspberry/BananaPi).
- **Configurar ambiente OpenCV em C/C++ para embarcado:**
  - Responsáveis voluntários (devs OpenCV) instalar, testar e compartilhar instruções (setup passo a passo).
- **Integração OpenCV ↔ Stockfish:**
  - Implementar protótipo com câmera fixa (etapa 1) e validar detecção de tabuleiro/peças e comunicação com a engine.
- **Divisão de tarefas e definição de papéis**
  - Mapear voluntários por área (OpenCV, CAD/impressão, embarcado/DevOps, QA, redação) e publicar lista no grupo até próxima semana.
- **Planejamento mensal:**
  - Agendar reunião de alinhamento mensal (proposta: último domingo do mês) e definir metas para o próximo mês (sprint mensal).
- **Modelagem e impressão do braço:**
  - Continuar ajustes no CAD, validar centro de massa e contrapesagem, imprimir primeiras peças e listar peças que precisam ser compradas.
- **Testes em hardware real e QA contínuo:**
  - Criar procedimento de QA para rodar no embarcado.
  - Disponibilizar dispositivos na faculdade para testes e criar rotina de integração contínua mínima.
- **Preparação para publicações:**
  - Montar esqueleto de artigos, designar responsáveis por redação e cronograma de submissão.
- **Explorar aplicações/impacto:**
  - Elaborar proposta conceitual para possível subartigo/aplicação e mapear potenciais parceiros.
- **Logística e recursos:**
  - Levantar orçamento aproximado para peças não imprimíveis e possíveis aquisições de hardware adicionais.
  - Listar itens prioritários.
  ---

## Observações Finais
- O grupo adotará uma abordagem iterativa: priorizar a prova de conceito com câmera fixa antes de integrar a câmera ao robô. Testes em hardware embarcado são essenciais — desempenho em desktop não garante comportamento real; benchmarks contextualizados devem orientar a escolha de placas e otimizações. A distribuição de funções será flexível, atribuída por interesse e disponibilidade, com possibilidade de rotatividade conforme as necessidades das etapas. É obrigatório manter documentação atualizada e compartilhada (código, resultados de benchmark, arquivos CAD) para replicação e suporte à escrita acadêmica. Deve-se priorizar a produção de publicações e explorar aplicações em educação e acessibilidade para aumentar visibilidade e chances de captação de recursos. Identificar e listar peças não imprimíveis e estimar orçamento; decisões de compra serão tomadas com base em testes. O sucesso do projeto depende do comprometimento regular dos membros oficialmente matriculados; colaboradores externos atuarão como suporte/backups.

📁 *Arquivo registrado em:* `reports\meetings\plannings\2026\03_meeting\3st_weekly_meeting.md`  
> ✍️ *Responsável por este Documento:* **Joao Augusto Vieira Ramalho** – 08/03/2026