Notebook: scr/Gold/fact_reviews.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define source `order_reviews_silver.parquet` e `OUTPUT` para `fact_reviews.parquet`.
- Célula 3: seleciona colunas chave (review_id, order_id, review_score, low_score_flag, review_creation_ts) e grava fato.

Observações:
- Fato de reviews para análises transversais e qualidade do pedido.