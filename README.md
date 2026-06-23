🚀 OLIST PIPELINE TURMA2

Pipeline end-to-end de dados e machine learning utilizando o dataset da Olist, com arquitetura em camadas (Bronze → Silver → Gold) e pipeline de modelagem para previsão de atrasos de entrega.

🎯 Problema de Negócio

O objetivo do projeto é prever atrasos de entrega (is_late_delivery), permitindo:

Identificação antecipada de pedidos com risco de atraso
Redução de custos operacionais logísticos
Ações preventivas (alertas e priorização de pedidos)

📌 Métrica de negócio principal:
Maximizar recall de atrasos sem degradar excessivamente a precision.

🧱 Arquitetura do Pipeline
🔹 Bronze (Ingestão)
Leitura dos CSVs brutos (Kaggle Olist)
Persistência em Parquet com timestamp de ingestão
Implementado com DuckDB

📂 scr/bronze/bronze_loader.ipynb

🔹 Silver (Tratamento)
Limpeza e padronização por domínio:
customers
sellers
orders
payments
order_items
reviews
geolocation
Saída em Parquet estruturado

📂 scr/Silver/*

🔹 Gold (Modelagem Analítica)
Criação de:
Dimensões (customers, products, date, sellers)
Fatos (orders, reviews)
Dataset pronto para analytics e ML

📂 scr/Gold/*

🔹 ML (Machine Learning)

Pipeline completo de experimentação:

Feature engineering (build_feature_table)
Validação de dados
EDA analítica
Feature engineering avançado
Modelos baseline
Proposta de modelo avançado (CatBoost)

📂 scr/ml/*

🧰 Stack Técnico
Python 3.x
DuckDB (SQL + ingestão)
Pandas / NumPy
Scikit-Learn
LightGBM / CatBoost
SHAP (explicabilidade)
Matplotlib / Seaborn
Parquet (formato de armazenamento)
▶️ Como Executar
1. Pré-requisitos
Python 3.8+
Git
DuckDB
Ambiente virtual recomendado (venv)
2. Pipeline de execução

Ordem recomendada:

Bronze

bronze_loader.ipynb

Silver

Notebooks em scr/Silver/

Gold

Notebooks em scr/Gold/

ML

01_build_feature_table.ipynb
02_data_validation.ipynb
03_eda_analysis.ipynb
04_feature_enginering.ipynb
05_train_baseline_model.ipynb
06_train_catboost_proposal.ipynb
3. Execução automatizada (opcional)
jupyter nbconvert --to notebook --execute notebook.ipynb

ou

papermill notebook.ipynb output.ipynb
🤖 Modelos e Avaliação

Modelos testados:

Logistic Regression
Decision Tree
Random Forest
LightGBM
CatBoost (proposta)
Métricas:
Precision
Recall
F1-score
AUC-ROC
Matriz de confusão

📌 Também analisado por threshold tuning (0.3 a 0.7)

🔍 Principais Insights
Variáveis de rota e logística (route_*, distance_km) são altamente preditivas
freight_ratio é um forte indicador de atraso
Transformações log melhoram estabilidade dos modelos
Certas rotas possuem padrões consistentes de atraso
Trade-off precision vs recall é crítico para decisão de negócio

📌 SHAP utilizado para explicabilidade global e local

📊 Governança e Reprodutibilidade
Dados brutos não versionados (ignorado via .gitignore)
Parquet usado para consistência entre camadas
Execução determinística com seeds nos modelos
Artefatos de ML podem ser salvos (model.pkl, metrics.csv)
🚀 Próximos Passos
Implementar CatBoost com tuning completo
Testar oversampling / class weighting
Avaliar stacking de modelos
Adicionar pipeline automatizado (Makefile ou DAG)
Criar CI/CD (GitHub Actions)
Adicionar Docker para replicação do ambiente
📁 Estrutura do Projeto
scr/bronze/ → ingestão
scr/Silver/ → transformação
scr/Gold/ → modelagem analítica
scr/ml/ → machine learning
docs/ → documentação técnica
📄 Licença

MIT License
