Notebook: scr/Silver/products.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define paths Bronze -> Silver -> OUTPUT.
- Célula 3: seleciona colunas do produto e calcula `product_volume_cm3`, salva `products_silver.parquet`.

Observações:
- Mantém atributos relevantes de produtos para joins e features de ML (peso, volume, categoria).