# 🏦 Crédito Imobiliário

### 🧪 Teste Técnico - Leonardo Valentim de Souza  

---

## 📋 Cenários de Teste (Gherkin)

---

### 1️⃣ Scenario: Exibir o card de Crédito Imobiliário após login bem-sucedido  
**Descrição:**  
Valida se, após um login bem-sucedido no site ou app do banco, o usuário consegue visualizar corretamente o card “Crédito Imobiliário” dentro da seção “Serviços”.  

**Pré-requisito:**  
Usuário deve possuir credenciais válidas e acesso ativo à conta.  

```gherkin
Given que o usuário acessa o site/app do banco
And realize o login com credenciais válidas
When o usuário navega até a seção "Serviços"
Then o sistema deve exibir o card "Crédito Imobiliário"
````

###2️⃣ Scenario: Exibir as etapas do Crédito Imobiliário

**Descrição:**
Após o usuário clicar no card “Crédito Imobiliário”, o sistema deve exibir a tela com as 4 etapas do processo e um botão “Continuar”.

**Pré-requisito:**
Usuário deve estar logado e ter acesso ao card “Crédito Imobiliário”.

```gherkin
  Given que o usuário clique no card "Crédito Imobiliário"
  When está na tela de Crédito Imobiliário
  Then o sistema deve exibir as 4 etapas e o botão "Continuar"
```  
