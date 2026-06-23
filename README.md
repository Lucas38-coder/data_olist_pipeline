# 🚀 OLIST PIPELINE TURMA2
### End-to-end Data & ML Pipeline (Bronze → Silver → Gold → ML)

Pipeline completo de engenharia de dados e machine learning para previsão de atrasos logísticos no e-commerce Olist.

---

## 🧭 Overview

Este projeto implementa uma arquitetura de dados em camadas, desde ingestão bruta até modelagem preditiva.

O objetivo é transformar dados transacionais em insights acionáveis para redução de atrasos de entrega.

---

## 🎯 Business Problem

O e-commerce enfrenta atrasos logísticos que impactam:

- Experiência do cliente  
- Custos operacionais  
- Eficiência logística  

### Objetivo
Prever pedidos com alta probabilidade de atraso (`is_late_delivery`) para permitir ações preventivas.

### Métrica de sucesso
- Maximizar **recall de atrasos**
- Manter **precision controlada**

---

## 🏗️ Architecture

OLIST RAW CSVs
↓
BRONZE (Ingestion - DuckDB)
↓
SILVER (Cleaning & Standardization)
↓
GOLD (Facts & Dimensions)
↓
ML LAYER (Feature Engineering + Models)


---

## 🧱 Data Layers

### 🟤 Bronze
- Ingestão dos CSVs originais
- Conversão para Parquet
- Timestamp de ingestão
- DuckDB como engine de processamento

---

### ⚪ Silver
- Limpeza e padronização
- Entidades:
  - customers
  - sellers
  - orders
  - payments
  - order_items
  - reviews
  - geolocation

---

### 🟡 Gold
- Modelagem dimensional:
  - Facts (orders, reviews)
  - Dimensions (customers, products, date, sellers)

---

### 🔵 ML Layer
Pipeline de machine learning:

- Feature engineering
- Data validation
- EDA
- Treinamento de modelos
- Avaliação

Modelos:
- Logistic Regression
- Random Forest
- LightGBM
- CatBoost (proposta)

---

## ⚙️ Tech Stack

- Python 3.x
- DuckDB
- Pandas / NumPy
- Scikit-Learn
- LightGBM / CatBoost
- SHAP
- Matplotlib / Seaborn
- Parquet

---

## 📊 Model Evaluation

Métricas utilizadas:

- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

### Estratégia
- Threshold tuning (0.3 → 0.7)
- Trade-off entre recall e precision

---

## 🔍 Key Insights

- Variáveis logísticas são altamente preditivas:
  - distance_km
  - route_*
  - freight_ratio

- Transformações log melhoram performance

- Certas rotas apresentam padrão consistente de atraso

- SHAP usado para interpretabilidade

---

## 🧠 Explainability

- SHAP para:
  - importância global de features
  - explicação de predições individuais

---

## 🔁 Reproducibility

- Pipeline baseado em DuckDB + Parquet
- Dados brutos não versionados (.gitignore)
- Execução determinística com seeds
- Estrutura modular por camadas

---

## 🚀 Roadmap

- CatBoost tuning completo
- Tratamento de desbalanceamento
- Model stacking
- Pipeline automatizado (Makefile / DAG)
- CI/CD com GitHub Actions
- Dockerização
- Deploy de modelo (API)

---

## 📁 Project Structure

scr/
├── bronze/
├── Silver/
├── Gold/
├── ml/

docs/
├── architecture
├── data_schema
├── notebooks


---

## 📄 License

MIT License
