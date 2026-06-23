Notebook: scr/Silver/customers.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define paths do Bronze (`customers.parquet`) e diretório Silver de saída.
- Célula 3: cria diretório Silver, conecta em DuckDB e executa query:
  - Seleciona colunas relevantes, faz cast do zip_code_prefix, lower() na cidade e salva Parquet final `customers_silver.parquet`.

Observações:
- Remove duplicatas via `SELECT DISTINCT` no SQL.
- Mantém `ingestion_timestamp` para rastreabilidade.