# GLOBAL_TRUST_BANK
🔵 Bank fraud detection project using Machine Learning. The XGBoost model with extended features (Time and Amount) achieved high accuracy (0.9994) and precision (0.9550).

Abrir o CSV que está no repositório: 'Base_M43_Pratique_CREDIT_CARD_FRAUD.csv'

# 🔵💳 Detecção de Transações Bancárias Fraudulentas – Banco Global Trust

Este projeto tem como objetivo detectar **transações bancárias fraudulentas** em dados sintéticos do **Banco Global Trust**, utilizando técnicas avançadas de **Machine Learning supervisionado**.  
O foco principal foi a **maximização da acurácia e da precisão**, métricas essenciais para reduzir falsos positivos e garantir a eficácia na identificação de fraudes.

---

## 🧭 Análise Exploratória

Foi conduzida uma **análise exploratória detalhada** para compreender o comportamento das transações em relação ao **tempo (`Time`)** e ao **valor (`Amount`)**.  
A coluna `Amount` foi **padronizada com o StandardScaler**, garantindo consistência na escala dos valores monetários.  
A variável `Time` representa o **delta de variação temporal entre as transações**, permitindo identificar picos suspeitos de movimentação em intervalos curtos.

### 🔹 Sobre as Features:

- **Time:** Delta de variância de tempo entre as transações.  
- **V1:V28:** Features transformadas via PCA (redução de dimensionalidade).  
- **Amount:** Valor real da transação.  
- **Class:** Indicador binário — *1* para fraude e *0* para transações legítimas.

---

## 🧮 Seleção de Features e Modelagem

A seleção de variáveis foi feita com base na **Mutual Information**, que identificou as **10 features mais relevantes** para o modelo:

`['V17', 'V14', 'V12', 'V10', 'V11', 'V16', 'V4', 'V3', 'V18', 'V9']`

Foram criados dois DataFrames principais:
- 🧾 **df_top_features.csv** → Contém apenas as 10 features mais importantes.  
- 🧾 **df_top_features_extended.csv** → Inclui as 10 features + variáveis adicionais (`Time` e `Amount`).

---

## ⚡ Modelos e Otimização

### 💡⚡🚀 LightGBM  
O modelo **LightGBM (Light Gradient Boosting Machine)** foi otimizado via **RandomizedSearchCV**, com validação cruzada e balanceamento entre *precision* e *recall*.  
A divisão dos dados foi feita em **70% para treino e 30% para teste**, garantindo robustez na avaliação do modelo.

---

### 💡🔵✨ XGBoost  
O modelo **XGBoost (Extreme Gradient Boosting)** também foi otimizado com **RandomizedSearchCV** e apresentou o **melhor desempenho geral** entre todos os modelos testados.  
Quando treinado com o **DataFrame estendido** (incluindo `Time` e `Amount`), o modelo atingiu resultados excepcionais:

- 🎯 **Acurácia:** 0.9994  
- 🔍 **Precisão (Precision):** 0.9550  

Esses resultados demonstram que as **variáveis temporais e monetárias** têm forte impacto na detecção de padrões de fraude, tornando o modelo altamente confiável e eficiente para uso em contextos bancários reais.

---

## 📊 Conclusão

O **modelo XGBoost**, combinado com a seleção de features mais relevantes e a inclusão das variáveis de tempo e valor, mostrou-se o mais eficaz para detectar **fraudes em transações bancárias**.  
A abordagem utilizada equilibra **desempenho, interpretabilidade e eficiência**, sendo um exemplo sólido de aplicação prática de *Machine Learning* na área financeira.

---

### 🧠 Tecnologias Utilizadas
- Python  
- Pandas  
- Scikit-learn  
- LightGBM  
- XGBoost  
- Matplotlib / Seaborn  
- Jupyter / Google Colab  

---

✨ Desenvolvido para fins educacionais e de pesquisa, simulando o ambiente de detecção de fraudes do **Banco Global Trust**.
