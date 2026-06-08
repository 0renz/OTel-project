FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
# Instala as bibliotecas de auto-instrumentação do OTel baseadas no ambiente
RUN opentelemetry-bootstrap -a install
COPY main.py .
# O comando de inicialização empacota a aplicação com o agente do OTel
CMD opentelemetry-instrument \
    --logs_exporter otlp \
    uvicorn main:app --host 0.0.0.0 --port ${PORT}