Projeto: OLIST-PIPELINE-TURMA2

Resumo rápido:
- Pipeline ETL em camadas: `raw/` -> `bronze/` -> `silver/` -> `gold/` -> `ml/`.
- Processos implementados em notebooks dentro de `scr/` (ingestão, transformações, criação de dimensões/fatos, ML).
- Modelos baseline treinados em `scr/ml/05_train_baseline_model.ipynb` (LogisticRegression, DecisionTree, RandomForest, LightGBM).
- Novo notebook proposto em `scr/ml/06_train_catboost_proposal.ipynb` (CatBoost + stacking).

O que contém `docs/`:
- `notebooks/`: arquivos com comentários célula-a-célula para cada notebook do projeto.
- `data_schema.md`: esquema e amostras dos arquivos em `data_lake/raw`.

Próximos passos:
- Revisar os arquivos em `docs/notebooks/` e pedir ajustes se desejar comentários mais detalhados por célula.
- Posso também criar versões inline (célula-a-célula) diretamente dentro dos `.ipynb` se preferir (fica a sua escolha).