Notebook: scr/Silver/orders.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb`, `os`, `pandas`.
- Célula 2: define paths do Bronze e saída Silver.
- Célula 3: SQL que transforma timestamps, extrai componentes de data (year, month, day), cria flags `is_delivered` e `is_late_delivery`, calcula `delivery_time_days`, e salva `orders_silver.parquet`.
- Célula 4: lê o Parquet resultante com `pandas` e exibe (modo de checagem).

Observações:
- `is_late_delivery` é o target usado no ML; notebooks posteriores dependem deste processamento.