Notebook: scr/Silver/order_items.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define `BRONZE` path e `SILVER_DIR` + `OUTPUT`.
- Célula 3: cria diretório, executa query que filtra preços/frete negativos, faz cast dos timestamps e calcula `total_item_value` (price + freight_value), salva Parquet.

Observações:
- Pré-processamento simples garantindo dados válidos antes de salvar na camada Silver.