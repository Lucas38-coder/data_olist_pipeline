Notebook: scr/bronze/bronze_loader.ipynb

Resumo célula-a-célula:
- Célula 1: importa `duckdb` e `os` (conexão SQL leve + manipulação de arquivos).
- Célula 2: define `RAW_PATH` e `BRONZE_PATH` (paths relativos para entrada e saída).
- Célula 3: dicionário `TABLES` mapeando nomes lógicos para arquivos CSV brutos.
- Célula 4: função `create_bronze_tables(table_name, file_name)`:
  - Conecta ao DuckDB, monta caminhos, cria pasta de saída.
  - Usa `read_csv_auto` do DuckDB para ler CSV e `COPY ... TO ... (FORMAT 'parquet')` para salvar Parquet com `ingestion_timestamp` e `source_file`.
- Célula 5: bloco `if __name__ == "__main__"` que itera sobre `TABLES` e chama a função para cada arquivo.

Observações:
- Pipeline de ingestão para camada bronze usando DuckDB; registra `ingestion_timestamp`.
- Boa prática para reprodutibilidade: arquivos Parquet por tabela em `data_lake/bronze/{table}`.