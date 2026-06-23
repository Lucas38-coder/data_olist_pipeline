# OLIST-PIPELINE-TURMA2 — Apresentação

Este projeto implementa um pipeline end-to-end para o dataset Olist, incluindo:

- Ingestão dos CSVs brutos para `data_lake/bronze` usando DuckDB.
- Transformações e limpeza para `data_lake/silver` (normalização, agregações).
- Criação de dimensões e fatos na camada `data_lake/gold`.
- Geração de dataset para ML e experimentos em `data_lake/ml` e `scr/ml`.

Objetivos do repositório:
- Servir como pipeline reprodutível para extração de features e treinamento de modelos.
- Disponibilizar notebooks com documentação célula-a-célula em `docs/notebooks/`.

Links rápidos:
- Documentação detalhada: `docs/README.md`
- Notebooks comentados: `docs/notebooks/`
- Schema dos dados: `docs/data_schema.md`

Como usar (resumo):
1. Obtenha os arquivos brutos (Kaggle or local) em `data_lake/raw`
2. Execute o notebook `scr/bronze/bronze_loader.ipynb` para criar Parquets na camada Bronze
3. Execute notebooks em `scr/Silver/` e `scr/Gold/` na ordem para construir as camadas intermediárias
4. Em `scr/ml/` execute `01_build_feature_table.ipynb` -> `02_data_validation.ipynb` -> `03_eda_analysis.ipynb` -> `04_feature_enginering.ipynb` -> `05_train_baseline_model.ipynb`

Contato: Lucas (autor do repositório local)
