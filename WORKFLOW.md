# Fluxo de Trabalho (Workflow) do M.E.A.

Este documento descreve o processo diário e o fluxo de trabalho da equipe de QA usando a metodologia M.E.A.

## Fase 1: Refinamento Técnico (Planning / Refinement)

O processo de QA **começa aqui**, junto com os DEVs.

1. **Discussão da Feature:** O Time (PO, DEVs, QAs) discute a nova feature (que geralmente é um `Épico` ou uma `História`).
2. **Criação do MCT:** Assim que os critérios de aceite são definidos, o QA já pode criar sua estrutura de teste.
3. **Ação do QA:**
    * O QA cria uma nova **Task** (filha do `Épico`) e a nomeia `[MCT] - {Nome da Funcionalidade}`.
    * Dentro do MCT, o QA já cria as duas sub-tarefas filhas: `[ECT] - {Nome da Funcionalidade}` e `[ACT] - {Nome da Funcionalidade}`.
4. **Modelagem:** Durante a Sprint (enquanto o DEV está codificando), o QA trabalha no MCT, movendo-o para "MODELANDO".
5. **Entrega do QA:** O QA preenche todo o template do MCT (escopo, pré-reqs, script Gherkin). Ao terminar, o QA move o MCT para **"PRONTO PARA EXECUÇÃO"**.

**Resultado da Fase 1:** O "gargalo" de planejamento de testes foi eliminado. Quando o DEV terminar de codificar, o plano de testes já está 100% pronto.

## Fase 2: Execução (Sprint em Andamento)

1. **DEV Entrega a Feature:** O DEV move sua tarefa para "Pronto para QA" (ou similar).
2. **Ação do QA:**
    * O QA pega a sub-tarefa `[ECT]` correspondente.
    * Move o `[ECT]` para "EXECUTANDO".
    * Segue o script Gherkin (definido no MCT) para executar o teste.
3. **Resultados da Execução:**
    * **Se o teste passar:** O QA anexa as evidências (prints, vídeos) no `[ECT]` e o move para **"PASSOU"**.
    * **Se o teste falhar:** O QA anexa as evidências, move o `[ECT]` para **"FALHOU"**, e cria uma nova issue de `Bug`, linkando-a ao `[ECT]` ou ao `MCT`.

## Fase 3: Automação (Pós-Execução)

1. **Priorização da Automação:** A sub-tarefa `[ACT]` (que estava em "Backlog de Automação") é puxada pelo time de QA (seja na mesma sprint ou na S+1, dependendo da capacidade).
2. **Ação do QA (Automação):**
    * O QA move o `[ACT]` para "AUTOMATIZANDO".
    * Desenvolve o script de automação (Cypress, Selenium, etc.) baseado no script Gherkin que já está documentado no `MCT` (pai).
    * Ao concluir e integrar na pipeline, o QA move o `[ACT]` para **"CONCLUÍDO"**.

**Resultado Final:** O `MCT` só é movido para "CONCLUÍDO" quando seus dois filhos (`ECT` e `ACT`) também estão concluídos (ou definidos como "Não Automatizável").
