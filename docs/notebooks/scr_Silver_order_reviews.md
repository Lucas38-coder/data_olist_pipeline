Notebook: scr/Silver/order_reviews.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define paths de Bronze e Silver.
- Célula 3: seleciona colunas relevantes (review_id, order_id, review_score), converte datas para timestamp, cria `low_score_flag` (review_score <= 2) e filtra reviews com score entre 1 e 5; salva Parquet.

Observações:
- `low_score_flag` é útil para análises de qualidade e integração em features ML.