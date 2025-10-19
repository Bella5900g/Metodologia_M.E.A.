# Modelos (Templates) de Descrição

Use estes modelos para padronizar a criação das suas issues M.E.A.

---

## Modelo de Descrição para [MCT] (Tipo: Task)

Copie e cole este código na descrição da sua Task de **MCT**.

```markdown
h2. 🚀 Escopo
(Descreva em poucas linhas o que este caso de teste específico cobre. Ex: "Validar o login de usuário com credenciais corretas".)

---

h2. 📋 Pré-Requisitos
(Liste as condições ou dados necessários para que este teste possa ser executado.)
* Ex: Usuário `qa-teste@empresa.com` deve existir no banco de dados.
* Ex: Estar na página de login.
* Ex: Cache do navegador deve estar limpo.

---

h2. 🧠 Contexto (Script Gherkin)
(Escreva o script do teste em formato BDD/Gherkin.)

*Funcionalidade:* {Nome da Funcionalidade}
*Cenário:* {Nome do Cenário de Teste}

*Dado* que o usuário está na página de login
*E* ele insere um e-mail válido
*E* ele insere uma senha válida
*Quando* ele clicar no botão "Entrar"
*Então* ele deve ser redirecionado para o dashboard
*E* deve ver a mensagem "Bem-vindo, [Nome do Usuário]".

---

h2. 📎 Links Úteis
* [Link para o protótipo no Figma](http://figma.com/...)
* [Link para a documentação relacionada](http://confluence.com/...)
```

---

## Modelo de Descrição para [ECT] (Tipo: Sub-task)

Geralmente o ECT não precisa de descrição, pois ela já está no MCT. O foco do ECT são os Comentários e Anexos com as evidências.

---

## Modelo de Descrição para [ACT] (Tipo: Sub-task)

Copie e cole este código na descrição da sua Sub-task de ACT.

```markdown
h2. 🎯 Objetivo da Automação
* Automatizar o cenário descrito no MCT pai.

h2. 📎 Referência do MCT
* Link para o MCT (Pai): {Cole o Link do MCT aqui}

h2. 🛠️ Ferramentas
* {Ex: Cypress, Playwright, Selenium}

h2. ⚙️ Dados de Teste (Massa de Dados)
* Usuário: `usuario.automacao@teste.com`
* Senha: `(Ver no Vault)`

h2. ✅ Critérios de Aceite
* [ ] Script de automação desenvolvido.
* [ ] Script rodando com sucesso no ambiente de QA.
* [ ] Script integrado à pipeline de CI/CD.
```
