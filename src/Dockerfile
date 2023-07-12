FROM python:latest

# cria diretorio do projeto.
WORKDIR /app

# copia dos arquivos para diretorio atual "raiz" (".")
COPY requirements.txt .

# procura os pacotes de instalação
RUN pip install -r requirements.txt

#copia os arquivos restantes do projeto.
COPY . /app

#porta que o app ira trabalhar.
EXPOSE 5000

#comando para inicar os containers.
CMD ["gunicorn", "--workers=1", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]