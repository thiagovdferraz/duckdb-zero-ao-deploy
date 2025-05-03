# ETL com Python + Duckdb

## Arquitetura do projeto

![Arquitetura](image/arquitetura_workshop.png)

## Configuração ambiente Python

```bash
pyenv local 3.12.5
poetry init
poetry env activate
```

Pacotes para instalar:

```bash
poetry add gdown # instalar para baixar dados google drive
poetry add duckdb
poetry add streamlit
poetry add psycopg2-binary # trabalhar com postgres
poetry add python-dotenv # variável de ambiente
poetry add sqlalchemy
```