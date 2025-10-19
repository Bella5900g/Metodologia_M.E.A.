# Metodologia M.E.A. - Gerenciamento Ágil de Testes no Jira

Uma metodologia gratuita e open-source para gerenciamento do ciclo de vida de QA (Modelagem, Execução e Automação) diretamente no Jira, focada em eliminar custos de ferramentas pagas (como Zephyr Scale) e otimizar o fluxo de trabalho ágil.

## O Problema que o M.E.A. Resolve

Muitas equipes de QA enfrentam dois problemas comuns:

1. **Custo:** Ferramentas de gerenciamento de testes (como Zephyr, Xray) possuem custos de licença por usuário, o que pode ser caro para a empresa.
2. **Gargalos:** O processo de QA tradicional muitas vezes espera o desenvolvimento terminar para então começar a *planejar* e *modelar* os testes, criando um gargalo no final da sprint.

## A Solução: M.E.A.

O **M.E.A.** (Modelagem, Execução, Automação) é um *framework de processo* que utiliza apenas os recursos nativos do Jira (Épicos, Tarefas e Sub-tarefas) para criar um sistema de gerenciamento de testes completo, rastreável e com custo zero.

### Os 3 Pilares do M.E.A.

A metodologia se baseia em uma hierarquia de issues clara e lógica:

* **M.E.A. (Plano de Teste):** O próprio **Épico** do Jira atua como o contêiner principal, representando o Plano de Teste para aquela funcionalidade.
* **MCT (Modelagem de Casos de Teste):**
    * **O que é:** Uma **Task** filha do Épico.
    * **Função:** É o "Caso de Teste" em si. Contém toda a documentação (escopo, pré-requisitos, script Gherkin) e é criada *durante os refinamentos*, **antes** do DEV entregar a feature.
* **ECT (Execução de Casos de Teste):**
    * **O que é:** Uma **Sub-task** filha do **MCT**.
    * **Função:** É a tarefa de *execução manual* do teste. É aqui que o QA anexa evidências (prints, vídeos, logs) e marca como "Passou" ou "Falhou".
* **ACT (Automação de Casos de Teste):**
    * **O que é:** Uma **Sub-task** filha do **MCT**.
    * **Função:** É a tarefa de *automação* daquele caso de teste. Ela é "irmã" do ECT, pois ambos os trabalhos (executar e automatizar) estão ligados ao mesmo MCT.

### Hierarquia Visual

```
Épico [M.E.A. - Plano de Teste da Feature]
│
└── Task [MCT - Modelagem do Caso de Teste 1]
    │
    ├── Sub-task [ECT - Execução Manual do Teste 1]
    └── Sub-task [ACT - Automação do Teste 1]
```

## Principais Benefícios

* **Custo Zero:** Utiliza 100% de recursos nativos do Jira.
* **Rastreabilidade Total:** Acompanhe o status do teste (Modelagem, Execução, Automação) diretamente pelo Épico.
* **Elimina Gargalos:** A Modelagem (MCT) é feita em paralelo com o desenvolvimento, não depois. Quando o DEV entrega, o QA já tem o script pronto, precisando apenas *executar*.
* **Gera Métricas:** Usando Dashboards nativos do Jira, você pode medir o progresso de cobertura de testes, débitos de automação, etc.
* **Fácil de Adotar:** Não requer instalação de plugins, apenas configuração de tipos de issue e fluxos de trabalho.

## Como Começar

1. **Configuração:** Siga nosso [Guia de Configuração (SETUP.md)](SETUP.md) para preparar seu projeto Jira.
2. **Fluxo de Trabalho:** Entenda o dia a dia da equipe com o [Guia de Fluxo de Trabalho (WORKFLOW.md)](WORKFLOW.md).
3. **Modelos:** Use nossos [Modelos (TEMPLATES.md)](TEMPLATES.md) para acelerar a escrita dos seus MCTs.

## 🌐 Página Web Interativa

Este repositório também inclui uma página web moderna e interativa que explica detalhadamente a metodologia M.E.A.:

- **URL da Página:** [https://bella5900g.github.io/Metodologia_M.E.A./](https://bella5900g.github.io/Metodologia_M.E.A./)
- **Design:** Interface moderna, responsiva e acessível
- **Conteúdo:** História completa da metodologia, estrutura visual e benefícios
- **Tecnologias:** HTML5, CSS3, JavaScript vanilla

### Como Hospedar no GitHub Pages

1. **Ative o GitHub Pages:**
   - Vá para Settings > Pages
   - Selecione "Deploy from a branch"
   - Escolha a branch "main" e pasta "/ (root)"

2. **Adicione sua foto:**
   - Coloque sua foto de perfil na pasta `img/`
   - Renomeie para `isabella-profile.jpg`

3. **Acesse sua página:**
   - URL será: `https://seu-usuario.github.io/Metodologia_M.E.A./`

## 📁 Estrutura do Projeto

```
Metodologia_M.E.A./
├── README.md              # Documentação principal
├── LICENSE                # Licença MIT
├── SETUP.md              # Guia de configuração
├── WORKFLOW.md           # Fluxo de trabalho
├── TEMPLATES.md          # Modelos de descrição
├── index.html            # Página web principal
├── styles.css            # Estilos CSS
├── script.js             # JavaScript interativo
└── img/                  # Pasta de imagens
    └── README.md         # Instruções para imagens
```

## Licença

Este projeto é licenciado sob a [Licença MIT](LICENSE). Sinta-se à vontade para usar, copiar, modificar e distribuir.
