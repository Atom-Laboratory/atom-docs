<!-- 

Nome do arquivo deve seguir o padrão:

xth_weekly_minute.md

Exemplo:

4th_weekly_minute.md 

-->
# ATA DA 22ª REUNIÃO DO GRUPO DE INICIAÇÃO CIENTÍFICA – BRAÇO ROBÓTICO

**Data da Reunião:** 07 de dezembro de 2025

**Membros Presentes:**
- Enzo Rocha Leite Diniz Ribas

---

## Pautas Discutidas

1. Organização da Reunião e Presença  
    - Observado que vários membros não estavam presentes na chamada.  
    - Discussão sobre pontualidade e comprometimento nas reuniões semanais.

2. Planejamento da Documentação  
    - Necessidade de assistir à gravação desta reunião (cobrança enfática).
    - Relatórios de participação:
        - Envio obrigatório por todos os membros.
        - Ausência de entrega resultará em contribuição registrada como nula.
    - Status das tarefas (sem avanços significativos por meses):
        - Lucas: não realizou a pesquisa contextualizadora.
        - Carlos: não entregou a introdução e a parte em Python.
        - Eduardo: tarefas de documentação pendentes.
        - Nicolas: não entregou a parte do YOLO.
        - Pedro: iniciou detecção de celular em Python, sem continuidade.
    - Ajustes no cronograma e reforço da estrutura dos relatórios internos.
    - Plano de ação: cada membro deve retomar atividades, registrar progresso e atualizar documentação no repositório.

3. Alteração do Escopo do Artigo (Pivotagem)

    - Artigo original (comparativo de bibliotecas para detecção de mãos) cancelado.
    - Motivo: Haar Cascade não performou adequadamente frente à variabilidade do dataset de mãos.
    - Novo tópico: Detecção de placas de carro.
    - Título provisório: “O custo da abstração no OpenCV: análise de desempenho, estabilidade e usabilidade em C++, Java e Python”.
    - Objetivo: Comparar a mesma biblioteca (OpenCV) nas três linguagens, com escopo reduzido para viabilidade no prazo.

4. Metodologia e Implementação Técnica

    - Setup:
        - OpenCV 4.12 (Java/C++) e 4.11 (Python) para equivalência entre ambientes.
        - Repositório único no GitHub do Atom.
    - Algoritmo:
        - Código semanticamente idêntico nas três linguagens.
        - Fluxo: varredura recursiva de diretórios → validação de imagem → timer (início) → pré-processamento/detecção → timer (fim) → desenho dos retângulos → salvamento da imagem e dos dados em CSV.
    - Datasets:
        - Imagens do Kaggle (ex.: carros em Dubai).

5.  Análise de Dados e Resultados Preliminares

    - Execução: 3 rodadas por linguagem.
    - Tratamento estatístico: Pandas + IQR para remoção de outliers (variações do SO).

---

## Encaminhamentos

- Assistir à Gravação da Reunião  
    - Responsável: Todos os membros ausentes  
    - Prazo: Imediato  
    - Descrição: Estar ciente da mudança de escopo e das cobranças feitas.

- Envio dos Relatórios de Participação  
    - Responsável: Todos os membros  
    - Prazo: Imediato  
    - Descrição: Enviar relatórios para registro da contribuição no projeto ATÉ 31/12/2025 ou será considerado como nulo.

- Revisão da Metodologia com Professores  
    - Responsável: Enzo Ribas  
    - Prazo: 07/12 (Hoje)  
    - Descrição: Enviar e-mail com a metodologia atualizada para revisão dos orientadores.

- Escrita do Artigo (Sessões Pendentes)  
    - Responsável: Equipe/Enzo  (NECESSÁRIO ENVOLVIMENTO DE TODOS)
    - Prazo: Curto prazo (Urgente)  
    - Descrição: Escrever “Resultados Obtidos”, “Resultados Esperados”, concluir “Revisão Bibliográfica”, e redigir “Resumo” e “Introdução”.

- Disponibilização do Código  
    - Responsável: Enzo Ribas  
    - Prazo: A definir  
    - Descrição: Publicar o fork do projeto no GitHub da organização Atom.

- Reorganizar a Documentação  
    - Responsável: Todos os membros  
    - Prazo: 15/12/2025  
    - Descrição: Atualizar relatórios quinzenais e contribuir na documentação do repositório.

- Revisar Dados Utilizados  
    - Responsável: Todos os membros
    - Prazo: 20/12/2025  
    - Descrição: Avaliar qualidade dos dados e definir padrões para novos testes.

---

## Observações Finais

- A reunião foi conduzida exclusivamente por Enzo Ribas devido à ausência dos demais membros.

- O Enzo trabalhou na reestruturação do projeto e na coleta de dados durante as 3 horas e meia em que aguardou na sala de reunião.

- A metodologia já está quase toda escrita e documentada (Docstrings inclusas no código).


- Diagramas e gráficos de desempenho já foram gerados para inclusão no documento final.


---

📁 *Arquivo registrado em:* `meetings\plannings\22_meeting\22_weekly_minute.md.md`  
> ✍️ *Responsável por este Documento:* **Enzo Rocha Leite Diniz Ribas** – 07/12/2025
