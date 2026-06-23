🚀 OLIST PIPELINE
End-to-end Data & ML Platform (Bronze → Silver → Gold → ML)

Pipeline completo de engenharia de dados e machine learning para previsão de atrasos logísticos no e-commerce Olist.

🧭 Overview

Este projeto implementa uma arquitetura moderna de dados com camadas bem definidas, desde ingestão bruta até modelagem preditiva.

O objetivo é transformar dados transacionais em insights acionáveis para redução de atrasos de entrega.

🎯 Business Problem

O e-commerce enfrenta atrasos logísticos que impactam:

Experiência do cliente
Custos operacionais
Eficiência da cadeia logística
Objetivo:

Prever pedidos com alta probabilidade de atraso (is_late_delivery) para permitir ação preventiva.

Métrica de sucesso:

Maximizar recall de atrasos, mantendo precision controlada para evitar alertas excessivos.

🏗️ Architecture
            ┌────────────────────┐
            │   OLIST RAW CSVs   │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │      BRONZE        │
            │ Ingestion (DuckDB) │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │      SILVER        │
            │ Cleaning & Models  │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │       GOLD         │
            │ Facts & Dimensions │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │        ML          │
            │ Feature + Models   │
            └────────────────────┘
🧱 Data Layers
🟤 Bronze (Raw Ingestion)
CSVs originais da Olist
Conversão para Parquet
Timestamp de ingestão
Implementação com DuckDB
⚪ Silver (Cleaning & Standardization)
Limpeza por domínio:
Customers
Sellers
Orders
Payments
Items
Reviews
Geolocation
Dados padronizados e prontos para modelagem
🟡 Gold (Analytics Layer)
Modelagem dimensional:
Facts (orders, reviews)
Dimensions (customers, products, date, sellers)
Base para análises e ML
🔵 ML Layer (Predictive Modeling)

Pipeline completo:

Feature engineering
Data validation
EDA
Model training
Evaluation & tuning

Modelos:

Logistic Regression
Random Forest
LightGBM
CatBoost (proposta)
⚙️ Tech Stack
Python 3.x
DuckDB
Pandas / NumPy
Scikit-Learn
LightGBM / CatBoost
SHAP (explainability)
Matplotlib

Storage:

Parquet (columnar format)
📊 Model Evaluation Strategy
Precision / Recall / F1
ROC-AUC
Precision-Recall curve
Threshold tuning (0.3 → 0.7)
Confusion Matrix analysis
Business focus:

Trade-off entre:

Detecção de atrasos (Recall)
Evitar falsos alarmes (Precision)
🔍 Key Insights
Variáveis logísticas são altamente preditivas:
distância (distance_km)
rota (route_*)
freight ratio
Transformações log melhoram estabilidade dos modelos
Certas rotas apresentam padrões consistentes de atraso
SHAP mostra forte contribuição de features logísticas vs financeiras
🧠 Explainability
SHAP utilizado para:
interpretação global do modelo
análise de decisões individuais
ranking de importância de features
🔁 Reproducibility
Pipeline baseado em DuckDB + Parquet
Execução determinística com seeds
Dados brutos não versionados (.gitignore)
Estrutura modular por camadas
🚀 Roadmap
CatBoost com tuning avançado
Class imbalance handling (SMOTE / weighting)
Model stacking
Pipeline automatizado (Makefile / DAG)
CI/CD com GitHub Actions
Dockerização do ambiente
Deploy de modelo (API simples)
📁 Project Structure
scr/
 ├── bronze/
 ├── Silver/
 ├── Gold/
 ├── ml/
docs/
 ├── architecture
 ├── data schema
 ├── notebooks summaries
📄 License

MIT License
