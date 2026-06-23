Notebook: scr/Silver/order_payments.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define paths para Bronze e Silver.
- Célula 3: executa agregação por `order_id`: soma `payment_value`, conta pagamentos, calcula max/min parcelas e salva Parquet.

Observações:
- Resultado usado para enriquecer o fato de pedidos (total de pagamento por pedido).