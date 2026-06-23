Notebook: scr/Gold/dim_customers.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define `CUSTOMERS` Silver e `OUTPUT_DIR` para dimensões.
- Célula 3: copia colunas chave (customer_id, unique_id, zip, city, state) para `dim_customers.parquet`.

Observações:
- Dimensão usada para análises e joins no fato de pedidos.