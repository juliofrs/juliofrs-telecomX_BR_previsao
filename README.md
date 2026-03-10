# telecomX_BR_previsao
Este projeto teve como objetivo desenvolver um pipeline de Machine Learning capaz de prever a evasão de clientes (Churn) da Telecom X e, mais importante, identificar as raízes desse problema para embasar ações de retenção.

# ☎️ Telecom X: Previsão de Evasão de Clientes (Churn) - Machine Learning

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

## 📌 Sobre o Projeto
Este é o segundo módulo do desafio de dados da **Telecom X**, focado inteiramente em **Machine Learning e Inteligência Preditiva**. 

Após a limpeza de dados e Análise Exploratória (EDA) realizadas na primeira fase, a missão agora foi construir um pipeline robusto capaz de prever quais clientes têm maior probabilidade de cancelar seus serviços (Churn). Além da previsão matemática, o objetivo central foi extrair os "porquês" por trás do comportamento do cliente para embasar estratégias de retenção da companhia.

## ⚙️ Pipeline de Dados e Pré-processamento
Para garantir que os modelos aprendessem de forma justa e eficiente, os dados (já limpos) passaram pelas seguintes transformações:
- **Remoção de Identificadores:** Exclusão da coluna `ID_Cliente` para evitar *overfitting*.
- **One-Hot Encoding:** Transformação de variáveis categóricas (como *Tipo de Contrato* e *Método de Pagamento*) em colunas binárias numéricas.
- **Balanceamento de Classes (SMOTE):** Geração de dados sintéticos nos dados de treino para equilibrar a base, que originalmente possuía 73% de retenção e apenas 27% de evasão.
- **Padronização (StandardScaler):** Normalização das variáveis contínuas numéricas (ex: *Cobrança Total* e *Meses de Contrato*) para a mesma escala.

## 🏆 Modelos e Desempenho
Foram treinados e comparados dois modelos de classificação. O conjunto de dados foi dividido em 70% para treino e 30% para teste (*holdout* com estratificação).

1. **Regressão Logística:**
   - O modelo demonstrou alta sensibilidade às transformações combinadas (SMOTE + Padronização), resultando em *underfitting*. 

2. **Random Forest (Modelo Vencedor 🥇):**
   - O algoritmo de árvores de decisão lidou perfeitamente com a complexidade dos dados.
   - **Acurácia:** 75,49%
   - **F1-Score:** 0.49
   - **Precisão:** 54% | **Recall:** 45%
   - *Conclusão:* Modelo escolhido para produção, demonstrando capacidade sólida de prever cancelamentos sem gerar um volume excessivo de "falsos alarmes".

## 💡 Principais Insights (Feature Importance)
Abrindo a "caixa preta" do Random Forest, identificamos as variáveis que mais influenciam a evasão:
* 💰 **Fator Financeiro:** O valor da fatura (`Cobranca_Total` e `Cobranca_Mensal`) é o principal gatilho.
* ⏳ **Fator Lealdade:** Os primeiros 10 meses (`Meses_Contrato`) são críticos. Clientes que passam do primeiro ano raramente cancelam.
* 🔓 **Fator Flexibilidade:** Contratos "Mês a Mês" (`Month-to-month`) impulsionam drasticamente as saídas.
* 🌐 **Fator Produto:** O serviço de internet por Fibra Ótica apresentou uma taxa de evasão preocupante.

> **Dica Visual:** *(Adicione aqui a imagem do gráfico de barras da "Importância das Variáveis" gerado no notebook usando o formato `![Feature Importance](caminho_da_imagem.png)`)*

## 🎯 Recomendações Estratégicas
Com base nas previsões da IA, a Telecom X deve adotar as seguintes medidas:
1. **Campanhas de Upsell:** Focar em converter clientes do plano mensal para contratos anuais.
2. **Revisão da Fibra Ótica:** Investigar problemas técnicos ou de precificação do serviço de Fibra.
3. **Customer Success Preventivo:** Atuar ativamente nos primeiros 10 meses de vida do cliente.
4. **Alerta de Churn:** Utilizar o *score* gerado pelo Random Forest para que a equipe de retenção aborde clientes em risco antes de efetuarem o cancelamento.

## 📈 Visualizações

<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/bfb8f495-dd21-4f41-b2dd-738e8df9ea05" />

<img width="1790" height="590" alt="image" src="https://github.com/user-attachments/assets/4210a913-b418-40b4-aac3-9e46eae5393c" />

<img width="690" height="490" alt="image" src="https://github.com/user-attachments/assets/235ea97f-f5e1-4157-bfc6-7f59d8b8a7be" />

<img width="690" height="490" alt="image" src="https://github.com/user-attachments/assets/ae07d020-395b-4e3c-921d-74b29795341e" />

<img width="1190" height="790" alt="image" src="https://github.com/user-attachments/assets/759f2bc9-27a9-4c03-976b-a115d6325b8d" />

<img width="1191" height="790" alt="image" src="https://github.com/user-attachments/assets/8f55e765-ec12-428c-87c3-6ebdfecbfb4c" />

## 🙋‍♂️ Autor

Feito por Julio Freitas.
Entre em contato!

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/juliofrs) 
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:juliofreitaspro@gmail.com)
