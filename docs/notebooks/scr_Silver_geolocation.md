Notebook: scr/Silver/geolocation.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os`.
- Célula 2: define `BRONZE` path e `SILVER_DIR` com `OUTPUT` final.
- Célula 3: cria diretório, conecta e executa query que agrega geolocalizações:
  - Calcula `AVG(geolocation_lat)` e `AVG(geolocation_lng)` por `geolocation_zip_code_prefix`, `city`, `state` e salva `geolocation_silver.parquet`.

Observações:
- Agregação torna a tabela mais leve para joins com clientes/vendedores (usa prefixo de CEP combinando com city/state).