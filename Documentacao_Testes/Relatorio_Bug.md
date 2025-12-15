# 🐞 Relatório de Bug: Falha na Validação de Borda do CEP

Este bug foi reportado no Jira como parte do ciclo de testes da US-02 (Validação de Erros).

| Campo do Bug           | Detalhes                                                   |
| :--------------------- | :--------------------------------------------------------- |
| **Prioridade**         | Média                                                      |
| **Status Atual**       | To Do (Reportado ao Desenvolvedor)                         |
| **Componente Afetado** | Finalização (Checkout - Step One)                          |
| **Requisito Violado**  | US-02 (Regra de que o CEP não deve exceder 10 caracteres). |

### 🛑 Título do Bug

Validação de Borda Falha: Formulário de Checkout aceita CEP com mais de 10 caracteres e avança.

### 📝 Passos para Reprodução (Steps to Reproduce)

1.  Navegar até a página de Informações do Checkout.
2.  Preencher os campos `First Name` e `Last Name` com dados válidos.
3.  No campo `Zip/Postal Code`, inserir **11 caracteres** (Ex: `12345678901`).
4.  Clicar no botão **`Continue`**.

### 🔍 Resultados

| Resultado Esperado                                                                               | Resultado Encontrado (Real)                                                                                                                                               |
| :----------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| O sistema deve bloquear a submissão e exibir uma mensagem de erro clara, permanecendo na página. | O sistema **redireciona** o usuário para a página de _Overview_ (`/checkout-step-two.html`), aceitando o valor inválido, o que pode causar erros em sistemas de back-end. |
