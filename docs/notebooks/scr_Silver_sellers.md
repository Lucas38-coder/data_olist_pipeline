Notebook: scr/Silver/sellers.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define paths Bronze -> Silver -> OUTPUT.
- Célula 3: transforma colunas (cast zip, lower city), salva `sellers_silver.parquet`.

Observações:
- Estrutura simples para padronizar dados de sellers antes de joins com fatos.