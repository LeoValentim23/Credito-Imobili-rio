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

###3️⃣  Scenario: Apresentar a descrição da tela Dados do imovel  

**Descrição:**
Valida que, ao clicar em “Continuar” na tela de etapas, o sistema carregue a tela “Dados do Imóvel” com a descrição informativa “Preencha os campos para iniciar a simulação”, orientando o usuário sobre o próximo passo.
**Pré-requisito:**
Usuário deve estar na tela de etapas do crédito imobiliário e clicar em “Continuar”.

```gherkin
Given que o usuário clique no Botão continuar na tela das etapas do Crédito Imobiliário
When está na tela de "Dados do Imovel" 
Then o sistema deve exibir a  descrição  "Preencha os campos para iniciar a simulação"
```



### 4️⃣ Scenario: Usuário realiza simulação com dados do imovel validos (Comercial)

**Descrição:**
Garante que, ao preencher o tipo de imóvel como “Comercial” e valor de R$200.000, o campo “Situação” não seja exibido e que o sistema redirecione corretamente à tela “Dados do Financiamento”.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
And preenche o campo "Tipo de imóvel" com "Comercial"
And nao deve exibir o campo "Situação" por ser Comercial 
And preenche o campo "Valor do imóvel" com "200000"
When clicar no botão "Avançar"
Then o sistema deve redirecionar para a tela "Dados do Financiamento"
```



 





### 5️⃣ Scenario:  Usuário realiza simulação com dados do imovel validos (Residencial - Usado) 
**Descrição:**
Valida o fluxo quando o tipo de imóvel é “Residencial” e a situação “Compra de imóvel usado”. Após inserir valor válido, o sistema deve seguir para “Dados do Financiamento”. 
**Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
And preenche o campo "Tipo de imóvel" com "Residencial"
And preenche o campo "Situação" com "Compra de imóvel usado"
And preenche o campo "Valor do imóvel" com "200000"
When clicar no botão "Avançar"
Then o sistema deve redirecionar para a tela "Dados do Financiamento"
```




 






### 6️⃣ Scenario:  Usuário realiza simulação com dados do imovel validos (Residencial -Novo) 
**Descrição:**
Valida o mesmo fluxo para imóveis residenciais novos, confirmando o redirecionamento correto após o preenchimento dos campos.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
And preenche o campo "Tipo de imóvel" com "Residencial"
And preenche o campo "Situação" com "Compra de imóvel Novo"
And preenche o campo "Valor do imóvel" com "200000"
When clicar no botão "Avançar"
Then o sistema deve redirecionar para a tela "Dados do Financiamento"
```


 






### 7️⃣ Scenario : Apresentar erro na tela de dados do imovel ao não preencher os campos necessários 
**Descrição:**
Garante que, ao tentar avançar sem preencher os campos necessários, o sistema apresente a mensagem de erro “Preencha todos os campos obrigatórios” e mantenha o usuário na mesma tela.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
When clicar no botão "Avançar" sem preencher os campos  necessários 
Then o sistema deve exibir a mensagem de erro "Preencha todos os campos obrigatórios"
And permanecer na mesma tela 
```


 





### 8️⃣ Scenario : Limite máximo do Valor do imovel não pode ultrapassar a 100.000.000,00 (Residencial) 
**Descrição:**
Valida que o sistema bloqueie valores superiores a R$100.000.000,00 para imóveis residenciais, exibindo mensagem de erro informando o limite.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
When  preenche o campo "Tipo de imóvel" com "Residencial"
And preenche o campo Valor do imovel e ultrapassar a 100.000.000,00
Then o sistema não deve permitir 
And informar erro, informando que não pode ultrapassar a 100.000.000,00
```


 





### 9️⃣ Scenario : Limite máximo do Valor do imovel não pode ultrapassar a 240.000.000,00(Comercial) 
**Descrição:**
Garante que o valor máximo permitido para imóveis comerciais (R$240.000.000,00) seja respeitado, e o sistema informe erro ao ultrapassar esse limite.
** Pré-requisito:**
Usuário deve estar na tela “Dados do Imóvel”.

```gherkin
Given que o usuário está na tela "Dados do Imovel"
When  preenche o campo "Tipo de imóvel" com "Residencial"
And preenche o campo Valor do imovel e ultrapassar a 240.000.000,00
Then o sistema não deve permitir 
And informar erro, informando que não pode ultrapassar a 240.000.000,00
```




 







### 🔟 Scenario : Limite máximo do Valor do financiamento não pode ultrapassar a 20% do valor total (Residencial)
**Descrição:**
Confirma que o sistema não permita valor de financiamento superior a 80% (limite de 160.000,00) do valor total do imóvel residencial.
** Pré-requisito:**
Usuário deve ter preenchido os dados do imóvel e avançado para “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Imovel" 
When preenche o campo Valor do imovel a 200.000,00
And continuar para tela  "Dados do financiamento"
Then o sistema deve exibir uma mensagem informando o valor máximo  
And preencher o campo com valor superior a 200.000,00
And informar erro, informando que não pode ultrapassar a 160.000,00 ( 20% do valor total)
```



### 1️⃣1️⃣ Scenario : Limite máximo do Valor do financiamento não pode ultrapassar a 25% do valor total (Comercial)
**Descrição:**
Garante que o sistema bloqueie valores de financiamento acima de 75% (limite de 140.000,00) do valor total do imóvel comercial.
**Pré-requisito:**
Usuário deve ter preenchido os dados do imóvel comercial e avançado para “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Imovel" 
When preenche o campo Valor do imovel a 200.000,00
And preenche o campo "Tipo de imóvel" com "Comercial"
And continuar para tela  "Dados do financiamento"
Then o sistema deve exibir uma mensagem informando o valor máximo  
And preencher o campo com valor superior a 200.000,00
And informar erro, informando que não pode ultrapassar a 140.000,00 ( 25% do valor total) 
```





 


Bug encontrado não está sendo exibido o valor máximo .

### 1️⃣2️⃣    Scenario: Apresentar a descrição da tela Dados do financiamento 
**Descrição:**
Valida a presença da mensagem “Preencha os campos e faça uma simulação” ao acessar a tela “Dados do Financiamento”, orientando o usuário para o preenchimento correto.
**Pré-requisito:**
Usuário deve ter concluído a etapa “Dados do Imóvel”.

```gherkin
Given que o usuário clique no Botão continuar na tela "Dados do Imovel" 
When está na tela de "Dados do financiamento" 
Then o sistema deve exibir a  descrição  "Preencha os campos e faça uma simulação"
```



 




### 1️⃣3️⃣ Scenario: Nao exibir a pergunta Quer financiar com taxa + remuneração da poupança para tipo de imovel comercial 
**Descrição:**
Verifica que, para imóveis comerciais, o sistema não exiba a pergunta “Quer financiar com taxa + remuneração da poupança”.
** Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento” com tipo de imóvel “Comercial”.

```gherkin
Given que o usuário está na tela "Dados do Imovel" 
When preenche o campo "Tipo de imóvel" com "Comercial"
And continuar para tela  "Dados do financiamento"
Then nao exibir a pergunta "Quer financiar com taxa + remuneração da poupança"
```



 




### 1️⃣4️⃣ Scenario: Exibir a pergunta Quer financiar com taxa + remuneração da poupança para tipo de imovel residencial
**Descrição:**
Valida que, para imóveis residenciais, a pergunta “Quer financiar com taxa + remuneração da poupança” seja exibida.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento” com tipo de imóvel “Residencial”.

```gherkin
Given que o usuário está na tela "Dados do Imovel" 
When preenche o campo "Tipo de imóvel" com "residencial"
And continuar para tela  "Dados do financiamento"
Then exibir a pergunta "Quer financiar com taxa + remuneração da poupança"\
```

 





###1️⃣5️⃣ Scenario: Habilitar pergunta "Valor das despesas com ITBI e registro"
**Descrição:**
Garante que, ao selecionar “Sim” para financiar despesas com ITBI e registro, o sistema exiba o campo para informar o valor dessas despesas.
** Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Financiamento" 
When preenche o campo Sim para a pergunta  "Quer Financiar despesas com  ITBI e registro"
Then exibir a pergunta "Valor das despesas com ITBI e registro"
```



 



###1️⃣6️⃣Scenario: Não habilitar pergunta "Valor das despesas com ITBI e registro"

**Descrição:**
Valida que, ao selecionar “Não”, o campo de valor de despesas não seja exibido, mantendo o formulário limpo.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Financiamento" 
When preenche o campo Não para a pergunta  "Quer Financiar despesas com  ITBI e registro"
Then não exiba a pergunta "Valor das despesas com ITBI e registro".
```


 




###1️⃣7️⃣ Scenario : Limite máximo do Prazo do financiamento não pode ultrapassar ao valor
**Descrição:**
 Verifica se o sistema impede o preenchimento de prazo superior ao limite permitido (prazo máximo configurado pela política do banco).
** Pré-requisito:**
 Usuário deve estar na tela “Dados do Financiamento”.

 ```gherkin
Given que o usuário está na tela "Dados do Financiamento" 
When preenche o campo Valor do imovel a 200.000,00
And preenche o valor superior a maximo 
And informar erro, informando que não pode ultrapassar ao valor maximo
```



 






###1️⃣8️⃣ Scenario: Habilitar pergunta "Data de nascimento do 2 comprador" e   "Cpf do 2 comprador " 

**Descrição:**
Valida que, ao marcar “Sim” em “Somar a renda de outro comprador”, o sistema exiba os campos “Data de nascimento do 2º comprador” e “CPF do 2º comprador”.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Financiamento" 
When preenche o campo Sim para a pergunta  "Somar a renda de outro comprador"
Then exibir a pergunta "Data de nascimento do 2 comprador" e   "Cpf do 2 comprador "
```




 





###1️⃣9️⃣ Scenario: Não habilitar pergunta "Data de nascimento do 2 comprador" e   "Cpf do 2 comprador " 
**Descrição:**
Verifica que, ao marcar “Não”, os campos referentes ao segundo comprador não sejam exibidos, mantendo apenas os dados do comprador principal.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento”.

```gherkin
Given que o usuário está na tela "Dados do Financiamento" 
When preenche o campo Não para a pergunta  "Somar a renda de outro comprador"
Then não exiba a pergunta "Data de nascimento do 2 comprador" e   "Cpf do 2 comprador "
```




 




### 2️⃣0️⃣Scenario: Simular um Crédito imobiliário 
**Descrição:**
Garante que, ao preencher todos os campos necessários e clicar em “Simular”, o sistema gere uma simulação com base nos dados informados e apresente o resultado ao usuário.
**Pré-requisito:**
Usuário deve estar na tela “Dados do Financiamento” com todos os campos obrigatórios preenchidos

```gherkin
Given que o usuário está na tela "Dados do Financiamento"
And tenha preenchido os campos necessário
When clicar no botão simular 
Then o sistema deve apresentar a simulação
```


### 🚀 As Is ###


### 🚀 Melhorias Para o To be###

### ⚙️ Simplificação do fluxo###


**Reduzir o número de decisões manuais que o usuário precisa fazer.**


**Consolidar etapas repetitivas, por exemplo:**


**Ao invés de separar "Novo" e "Usado" e depois pedir valores e dados de financiamento, oferecer um formulário único adaptativo que muda conforme o tipo de imóvel.**


**Evitar bifurcações desnecessárias, como “Somar a renda de outro comprador” separadamente; integrar ao cálculo automático.**


### 🤖 Automação e integração###


**Pré-preenchimento de dados com base no login do cliente ou histórico de crédito.**


**Cálculo automático do valor do financiamento e parcelas, incluindo ITBI e registro.**


**Integração com sistemas de autorização e seguradora para validação imediata.**


### 💡 Melhoria da experiência do usuário###


**Usar uma interface mais visual, talvez um wizard passo-a-passo com progresso.**


**Mostrar feedback imediato após cada entrada, como simulação parcial de financiamento.**


**Oferecer comparativos automáticos de financiamento: “25% de entrada vs 20% de entrada”.**


### 🔍 Validação inteligente###


**Validar CPF e data de nascimento do segundo comprador automaticamente.**


**Detectar se os documentos estão corretos ou se algum dado está faltando antes de avançar.**


**Sugestão de alertas ou recomendações, como “Você poderia reduzir o prazo de pagamento para economizar X”.**


### 🎯 Personalização e recomendações###


**Sugestão de produtos complementares, como seguros ou planos de proteção.**


**Recomendações de financiamento mais vantajoso de acordo com perfil do cliente.**


### 📊 Relatórios e histórico###


**Salvar simulações anteriores do usuário.**


**Permitir download de PDF ou envio por e-mail com os detalhes da simulação.**
