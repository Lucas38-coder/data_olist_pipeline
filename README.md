# OLIST-PIPELINE-TURMA2

Pipeline ETL e ML para o dataset Olist (turma 2). Este repositório contém notebooks e scripts para ingestão, tratamento, criação de camadas Bronze/Silver/Gold e experimentos de machine learning.

Sumário rápido:
- `data_lake/` — camadas do data lake (raw, bronze, silver, gold, ml/datasets)
- `scr/` — notebooks de ingestão e transformação
  - `scr/bronze/bronze_loader.ipynb` — leitura CSV -> Parquet (DuckDB)
  - `scr/Silver/` — notebooks para criação da camada Silver
  - `scr/Gold/` — criação de dimensões e fatos
  - `scr/ml/` — notebooks de ML (feature build, validation, EDA, baseline, proposta CatBoost)
- `docs/` — documentação gerada (inclui resumos célula-a-célula)

Como publicar no GitHub (exemplo):

```bash
git init
git add .
git commit -m "Initial project import"
# criar repositório no GitHub e adicionar remote, por exemplo:
# git remote add origin git@github.com:SEU_USUARIO/olist-pipeline-turma2.git
git branch -M main
git push -u origin main
```

Recomendações:
- Não commitar arquivos em `data_lake/raw` (são grandes). Use `.gitignore` já presente.
- Para executar notebooks com full I/O, tenha `duckdb`, `pandas`, `scikit-learn`, `lightgbm` instalados.

Veja `docs/index.md` para a apresentação do projeto.