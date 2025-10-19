# Guia de Configuração (Setup) do M.E.A.

Para implementar a metodologia M.E.A., um Administrador do Jira precisa realizar algumas configurações iniciais no projeto.

## Passo 1: Garantir os Tipos de Issue

O M.E.A. funciona com os tipos de issue padrão do Jira. Você precisa garantir que seu projeto tenha os seguintes tipos habilitados:

* `Epic`
* `Task` (Será usado para o **MCT**)
* `Sub-task` (Será usado para o **ECT** e **ACT**)

Se seu projeto não os utiliza (ex: usa "História" no lugar de "Task"), você pode adaptar a metodologia, mas o padrão recomendado é este.

## Passo 2: Configurar um Workflow (Opcional, mas Recomendado)

Para obter o máximo de rastreabilidade, recomendamos criar fluxos de trabalho (workflows) específicos para seus itens de teste.

### Workflow do MCT (Tipo: Task)

Crie um workflow simples para a `Task` [MCT]:

* **A FAZER (To Do):** O QA ainda não iniciou a modelagem.
* **MODELANDO (Modeling):** O QA está escrevendo o escopo, pré-requisitos e script Gherkin.
* **PRONTO PARA EXECUÇÃO (Ready for Execution):** A modelagem está concluída e aguardando a feature do DEV para ser executada.
* **CONCLUÍDO (Done):** O teste foi executado e automatizado (ou considerado "Não Automatizável").

### Workflow do ECT (Tipo: Sub-task)

Crie um workflow simples para a `Sub-task` [ECT]:

* **AGUARDANDO (Pending):** Aguardando a feature ser entregue pelo DEV.
* **EXECUTANDO (Executing):** QA está realizando o teste manual.
* **PASSOU (Passed):** O teste foi executado e passou.
* **FALHOU (Failed):** O teste falhou (anexar evidências e criar um Bug).
* **BLOQUEADO (Blocked):** Não é possível executar o teste.

### Workflow do ACT (Tipo: Sub-task)

Crie um workflow simples para a `Sub-task` [ACT]:

* **BACKLOG DE AUTOMAÇÃO (Automation Backlog):** Aguardando para ser priorizado pelo time de automação.
* **AUTOMATIZANDO (Automating):** O script de automação está sendo desenvolvido.
* **CONCLUÍDO (Done):** O teste está automatizado e rodando na pipeline.
* **NÃO AUTOMATIZÁVEL (Won't Automate):** O time decidiu que este teste não será automatizado.

## Passo 3: Configurar Dashboards de Métricas

Use os gadgets nativos do Jira para criar um Dashboard de QA.

1. Crie um **Filtro** JQL para cada estado:

    * **Cobertura de Modelagem:** `project = "SEU PROJETO" AND issuetype = "Task" AND "Epic Link" = "SEU-ÉPICO-ATUAL"`
    * **Testes Executados (ECT):** `project = "SEU PROJETO" AND issuetype = "Sub-task" AND summary ~ "[ECT]" AND parent = "MCT-DA-FEATURE"`
    * **Débito de Automação (ACT):** `project = "SEU PROJETO" AND issuetype = "Sub-task" AND summary ~ "[ACT]" AND status = "Backlog de Automação"`

2. Adicione **Gadgets** ao seu Dashboard:

    * **Gráfico de Pizza (Pie Chart):** Use para ver o status dos ECTs (Passed, Failed, Pending).
    * **Filtro de Issues:** Use para listar todos os ACTs que estão no "Backlog de Automação".
    * **Gráfico de Duas Dimensões:** Use para cruzar o "Responsável" com o "Status" dos MCTs.

Com essa configuração, seu projeto está pronto para usar a metodologia M.E.A.
