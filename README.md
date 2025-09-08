# Who Was the Attacker? 🔐  
_Classificação de atacantes em incidentes de cibersegurança (2015–2024)_

## 📌 Contexto
O dataset **Global Cybersecurity Threats (2015–2024)** reúne incidentes digitais em diversos países e setores.  
Cada registro descreve um ataque: tipo, indústria-alvo, prejuízo financeiro, número de usuários afetados, vulnerabilidade explorada, mecanismos de defesa e tempo de resolução.

Este projeto segue a metodologia **CRISP-DM** para responder a uma questão central de negócio:

👉 **Quem foi o atacante?**  
*(Hacker Group, Insider, Nation-state ou Unknown)*

---

## 🛠️ Tecnologias utilizadas
- **Linguagem:** Python 3  
- **Bibliotecas de análise e visualização:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`  
- **Machine Learning:** `scikit-learn` (RandomForest, ExtraTrees, HistGradientBoosting)  
- **Validação temporal:** `TimeSeriesSplit`  
- **Otimização de hiperparâmetros:** `RandomizedSearchCV`, `scipy.stats`  

---

## ⚙️ Metodologia (CRISP-DM)

- **Business Understanding:**  
  Definição do problema de negócio e métricas.  
  - Métrica principal: **Log Loss** (probabilidades úteis para investigação)  
  - Métrica auxiliar: **F1-Macro** (equilíbrio entre classes)  
  - Baselines: moda e distribuição empírica (priors).  

- **Data Understanding:**  
  Análise exploratória (tipos de ataque, setores, prejuízos, vulnerabilidades).  
  Identificação de **missing values**, **dup values** e padrões temporais.  

- **Data Preparation:**  
  - Encoding de variáveis categóricas (`OrdinalEncoder`, `LabelEncoder`)  
  - Pipeline com `ColumnTransformer`  

- **Modeling:**  
  - Algoritmos: **RandomForest**, **ExtraTrees**, **HistGradientBoosting**  
  - Otimização com `RandomizedSearchCV`  
  - Validação via **TimeSeriesSplit** (sem shuffle).  

- **Evaluation:**  
  - **Log Loss** e **F1-Macro**  
  - Matrizes de confusão  
  - Comparação com baselines  

- **Deployment / Próximos Passos:**  
  - Publicação do notebook no Kaggle  
  - Modelagem de **tempo de resolução** e **custo financeiro** (regressão multioutput)  
  - Monitoramento de drift e análise de robustez  

---

## 📊 Resultados iniciais
- Modelos de árvores de decisão alcançaram ligera melhora em relação aos baselines.  

---

## 🚀 Próximas etapas
- Previsão de **tempo de resolução** (Incident Resolution Time) e **custo financeiro**.  
- Testes com modelos adicionais.  
- Exploração de técnicas de explicabilidade (SHAP, feature importance).  

---

## 🔗 Acesso
- [Notebook no Kaggle](https://www.kaggle.com/code/diogonoglima/who-was-the-attacker)  

---
