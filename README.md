# 📊 TelecomX (Parte 2): Previsão de Evasão de Clientes (Churn) com Machine Learning

🔗 **Repositório Atual:** [telecomX_2](https://github.com/souleosantos/telecomX_2)
🔙 **Parte 1 (Análise e Tratamento):** [telecomX_analise_evasao_clientes](https://github.com/souleosantos/telecomX_analise_evasao_clientes)

**Autor:** Leonardo Santos  
**Projeto:** Desenvolvido como parte do programa Oracle Next Education (ONE) em parceria com a Alura.

> **⚠️ IMPORTANTE:** Este repositório foca na etapa de Modelagem Preditiva. O dataset utilizado aqui (`dados_tratados.csv`) já foi previamente limpo, analisado e preparado para Machine Learning na **Parte 1** do projeto.

---

## 📌 1. Introdução

O objetivo deste estudo foi prever a evasão de clientes (churn) em uma empresa de telecomunicações e identificar os principais fatores de risco. A base de dados contém **7.043 clientes** e a variável alvo analisada foi **Churn** (Yes/No).

---

## 🤖 2. Técnicas de Machine Learning Utilizadas

Para realizar a previsão de evasão e lidar com o desbalanceamento dos dados (73% retidos vs 26% evadidos), foram aplicadas as seguintes técnicas e modelos:

* **Regressão Logística (Logistic Regression):** Utilizada como modelo base (baseline).
* **Random Forest Classifier:** Algoritmo baseado em árvores de decisão para capturar relações não-lineares.
* **Regressão Logística Balanceada:** Aplicação do hiperparâmetro `class_weight="balanced"` para penalizar erros na classe minoritária (Churn = Yes), priorizando o aumento do *Recall*.
* **Testes Estatísticos (Chi-Quadrado):** Para seleção de features e validação da significância estatística das variáveis categóricas.
* **Métricas de Avaliação:** Foco em *Recall*, *Precision*, *F1-Score* e *Accuracy*.

---

## 🚀 3. Como Executar o Projeto (Google Colab)

Para reproduzir este projeto e rodar os modelos na sua máquina, siga os passos abaixo:

1. Recomendamos o uso do **Google Colab** para facilitar a execução, pois ele já possui as principais bibliotecas instaladas.
2. Faça o download do arquivo de dados `dados_tratados.csv` disponível neste repositório.
3. Abra o notebook do projeto (`.ipynb`) no seu ambiente do [Google Colab](https://colab.research.google.com/).
4. No menu lateral esquerdo do Colab, clique no ícone de pasta (Arquivos).
5. Faça o **upload** do arquivo `dados_tratados.csv`.
6. Execute as células do notebook sequencialmente.

---

## 🔍 4. Análise Exploratória e Fatores de Risco

### Principais Fatores de Evasão Identificados:

🔥 **1. Tipo de Contrato (Contract)**
| Tipo | % Churn |
| :--- | :--- |
| Month-to-month | **42,7%** |
| One year | 11,2% |
| Two year | 2,8% |
*Principal fator de evasão. Clientes com contrato mensal têm probabilidade extremamente maior de cancelar.*

🔥 **2. Serviço de Internet e Pagamento**
* Clientes com fibra óptica evadem mais (**41,9%**).
* Pagamento via **boleto eletrônico (Electronic check)** está fortemente associado à evasão (**45,2%**).

🔥 **3. Serviços de Segurança e Suporte**
Clientes que **não possuem** serviços como *OnlineSecurity*, *TechSupport*, *Dependents* e *Partner* apresentam taxas de churn superiores a **31%**.

---

## 📈 5. Desempenho dos Modelos Preditivos

Testamos três abordagens focando na identificação da classe "Yes" (evasão):

1. **Regressão Logística (Padrão):** Recall de 0.52
2. **Random Forest:** Recall de 0.48
3. **Regressão Logística Balanceada 🏆:** Recall de **0.79** (Melhor Modelo)

> **Por que a Regressão Logística Balanceada venceu?** > Apesar da acurácia geral ligeiramente menor (74%), o modelo conseguiu identificar **79% dos clientes que realmente iriam cancelar**. Em problemas de churn, minimizar os Falsos Negativos (ter um Recall alto) é a métrica de negócio mais importante.

---

## 💡 6. Estratégias de Retenção Propostas

Com base nos resultados do Machine Learning, sugerimos as seguintes ações táticas:

* 🎯 **Contrato Mensal:** Oferecer descontos para migração para planos anuais ou programas de fidelidade.
* 💳 **Boleto Eletrônico:** Incentivo financeiro (cashback/desconto) para adesão ao débito automático.
* 🛡️ **Upsell de Segurança:** Ofertas personalizadas de pacotes promocionais para clientes sem *OnlineSecurity* e *TechSupport*.
* 👴 **SeniorCitizen:** Criação de um canal de atendimento dedicado e simplificado.
* 📅 **Novos Clientes:** Programa de *onboarding* proativo nos primeiros 90 dias.

---

## 🛠️ 7. Tecnologias e Bibliotecas

* **Python**
* **Pandas / NumPy** (Manipulação de dados)
* **Matplotlib / Seaborn** (Visualização)
* **Scikit-Learn** (Machine Learning e Métricas)

---

## 🤝 8. Como Contribuir

Contribuições são sempre bem-vindas! Se você deseja melhorar as análises, testar novos algoritmos (como XGBoost ou LightGBM) ou otimizar o código:

1. Faça um **Fork** do projeto
2. Crie uma branch para sua modificação (`git checkout -b feature/NovoModelo`)
3. Faça o commit das suas alterações (`git commit -m 'Adicionando modelo XGBoost'`)
4. Faça o push para a branch (`git push origin feature/NovoModelo`)
5. Abra um **Pull Request** detalhando as melhorias implementadas.

---

<p align="center">
  Desenvolvido com dedicação por Leonardo Santos.
</p>
