# ETL com Python + Duckdb

## Arquitetura do projeto

![Arquitetura](image/arquitetura_workshop.png)

## Configuração ambiente Python

```bash
pyenv local 3.12.5
poetry init
poetry env activate
```

## Pacotes para instalar

```bash
poetry add gdown # instalar para baixar dados google drive
poetry add duckdb
poetry add streamlit
poetry add psycopg2-binary # trabalhar com postgres
poetry add python-dotenv # variável de ambiente
poetry add sqlalchemy
```

## Dockerfile para deploy no render.com ou outro serviço

```dockerfile
FROM python:3.12
RUN pip install poetry
COPY . /src
WORKDIR /src
RUN poetry install --no-root --only main
EXPOSE 8501
ENTRYPOINT ["poetry","run", "streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```