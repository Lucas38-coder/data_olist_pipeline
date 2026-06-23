Data lake — Raw files (amostras e esquema)

Arquivo: olist_orders_dataset.csv
- Colunas: order_id, customer_id, order_status, order_purchase_timestamp, order_approved_at, order_delivered_carrier_date, order_delivered_customer_date, order_estimated_delivery_date
- Observação: contém timestamps; usado para criar indicadores de entrega e `is_late_delivery`.
- Amostra: linhas iniciais incluídas no repositório (valores de timestamps e status como 'delivered', 'shipped', 'invoiced').

Arquivo: olist_customers_dataset.csv
- Colunas: customer_id, customer_unique_id, customer_zip_code_prefix, customer_city, customer_state
- Observação: zip_code_prefix usado para juntar com geolocation; city/state são lowercased nos scripts.

Arquivo: olist_order_items_dataset.csv
- Colunas: order_id, order_item_id, product_id, seller_id, shipping_limit_date, price, freight_value
- Observação: usado para calcular `total_item_value` e filtrar preços negativos.

Arquivo: olist_order_payments_dataset.csv
- Colunas: order_id, payment_sequential, payment_type, payment_installments, payment_value
- Observação: agregado por `order_id` nos notebooks de Silver (soma de pagamentos, contagem de parcelas).

Arquivo: olist_order_reviews_dataset.csv
- Colunas: review_id, order_id, review_score, review_comment_title, review_comment_message, review_creation_date, review_answer_timestamp
- Observação: `review_score` é transformado em flag `low_score_flag` nos notebooks de Silver.

Arquivo: olist_products_dataset.csv
- Colunas: product_id, product_category_name, product_name_lenght, product_description_lenght, product_photos_qty, product_weight_g, product_length_cm, product_height_cm, product_width_cm
- Observação: volume é calculado em Silver/Gold como `product_length_cm * product_height_cm * product_width_cm`.

Arquivo: olist_sellers_dataset.csv
- Colunas: seller_id, seller_zip_code_prefix, seller_city, seller_state

Arquivo: olist_geolocation_dataset.csv
- Observação: arquivo grande (>50MB) — não foi lido automaticamente aqui por limite de sincronização.
- Schema conhecido (usado nos notebooks): geolocation_zip_code_prefix, geolocation_lat, geolocation_lng, geolocation_city, geolocation_state
- Nota: geolocation é agregada (avg lat/lng por zip_code_prefix+city+state) no pipeline.

Arquivo: product_category_name_translation.csv
- Tabela de tradução para nomes de categoria em diferentes línguas (usado para mapear `product_category_name` quando necessário).

Observações gerais:
- Alguns arquivos brutos são grandes e por isso os notebooks usam DuckDB para leitura/transformação e salvam arquivos Parquet em `data_lake/bronze`, `silver`, e `gold`.
- Se quiser amostras maiores (primeiras 100 linhas) de arquivos grandes, posso gerar comandos `head -n` ou instruções em Python para você executar localmente e eu integrar os outputs à documentação.