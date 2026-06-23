Notebook: scr/Gold/dim_date.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define `ORDERS` Silver e `OUTPUT_DIR` para dimensões.
- Célula 3: cria `dim_date.parquet` com data, year, month, day, weekday via `SELECT DISTINCT`.

Observações:
- Dimensão de tempo para análises temporais e junções por data.