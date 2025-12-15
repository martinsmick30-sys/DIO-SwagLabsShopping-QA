# 📝 Casos de Teste Manuais (4 TCs)

Estes Casos de Teste cobrem as User Stories SLS-2 (US-01) e SLS-3 (US-02), combinando os formatos Step-by-Step e BDD Gherkin conforme o requisito do desafio.

---

### 1. TC-SLS-001: Validação do Fluxo Principal de Checkout (Step-by-Step)

| Detalhe                      | Valor                                                     |
| :--------------------------- | :-------------------------------------------------------- |
| **Foco**                     | Caminho Feliz e Transição (US-01)                         |
| **Prioridade**               | Alta                                                      |
| **Resultado Esperado Final** | Redirecionamento para a página `/checkout-step-two.html`. |

| Passo | Ação                                               | Resultado Esperado                                       |
| :---- | :------------------------------------------------- | :------------------------------------------------------- |
| 1     | Navegar para a página de informações do Checkout.  | Página carregada.                                        |
| 2     | Inserir um `First Name` válido (Ex: "João").       | Campo aceita a entrada.                                  |
| 3     | Inserir um `Last Name` válido (Ex: "Silva").       | Campo aceita a entrada.                                  |
| 4     | Inserir um `Zip/Postal Code` válido (Ex: "12345"). | Campo aceita a entrada.                                  |
| 5     | Clicar no botão **`Continue`**.                    | A página redireciona para o _Overview_ sem exibir erros. |

---

### 2. TC-SLS-002: Boundary Testing - CEP Acima do Limite (Step-by-Step)

| Detalhe                      | Valor                                     |
| :--------------------------- | :---------------------------------------- |
| **Foco**                     | Teste Negativo (Borda Superior) (US-02)   |
| **Prioridade**               | Média                                     |
| **Resultado Esperado Final** | Mensagem de erro e permanência na página. |

| Passo | Ação                                                                                     | Resultado Esperado                                                                      |
| :---- | :--------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------- |
| 1     | Inserir `First Name` e `Last Name` válidos.                                              | Campos preenchidos.                                                                     |
| 2     | No campo `Zip/Postal Code`, inserir uma string de **11 caracteres** (Ex: "12345678901"). | O campo aceita a entrada.                                                               |
| 3     | Clicar no botão **`Continue`**.                                                          | O formulário **não** deve avançar. Mensagem de erro clara sobre o limite de caracteres. |

---

### 3. TC-SLS-003: Falha na Submissão - First Name Vazio (BDD Gherkin)

| Detalhe              | Valor                                       |
| :------------------- | :------------------------------------------ |
| **Foco**             | BDD: Validação de Campo Obrigatório (US-02) |
| **Prioridade**       | Média                                       |
| **Conteúdo Gherkin** |

Dado que o Cliente está na página de Checkout-Step One
E que o campo Last Name foi preenchido com dados válidos
E que o campo Zip/Postal Code foi preenchido com dados válidos
Quando o Cliente deixa o campo First Name vazio
E clica no botão Continue
Então o sistema não deve redirecionar para a próxima página
E uma mensagem de erro clara para First Name deve ser exibida. |

---

### 4. TC-SLS-004: Falha na Submissão - Last Name Vazio (BDD Gherkin)

| Detalhe              | Valor                                       |
| :------------------- | :------------------------------------------ |
| **Foco**             | BDD: Validação de Campo Obrigatório (US-02) |
| **Prioridade**       | Média                                       |
| **Conteúdo Gherkin** |

Dado que o Cliente está na página de Checkout-Step One
E que o campo First Name foi preenchido com dados válidos
E que o campo Zip/Postal Code foi preenchido com dados válidos
Quando o Cliente deixa o campo Last Name vazio
E clica no botão Continue
Então o sistema não deve redirecionar para a próxima página
E uma mensagem de erro clara para Last Name deve ser exibida. |
