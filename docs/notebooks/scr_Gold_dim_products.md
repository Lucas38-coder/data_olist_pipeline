Notebook: scr/Gold/dim_products.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define source `products_silver.parquet` e `OUTPUT` em `data_lake/gold/dimensions/dim_products.parquet`.
- Célula 3: executa `COPY` para criar dimensão de produtos com colunas selecionadas.

Observações:
- Dimensão enxuta com atributos necessários para análises e joins.