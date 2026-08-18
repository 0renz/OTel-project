# Microsserviços com OpenTelemetry

Projeto baseado em uma arquitetura de **microsserviços Python** com instrumentação utilizando **OpenTelemetry** e uma stack de observabilidade para **métricas, traces e logs**.

## Tecnologias utilizadas

* **Python 3.10**
* **FastAPI** — framework para construção das APIs.
* **Uvicorn** — servidor ASGI utilizado para executar as aplicações FastAPI.
* **Docker** — containerização dos microsserviços e ferramentas de observabilidade.
* **Docker Compose** — orquestração dos containers.
* **OpenTelemetry (OTel)** — instrumentação e coleta de telemetria.
* **OpenTelemetry Collector** — centralização e processamento dos dados de telemetria.
* **Prometheus** — armazenamento e consulta de métricas.
* **Grafana Tempo** — armazenamento e consulta de traces distribuídos.
* **Grafana Loki** — armazenamento e consulta de logs.
* **Grafana** — visualização e criação de dashboards de observabilidade.
* **OTLP gRPC** — protocolo utilizado para envio da telemetria ao OpenTelemetry Collector.

## Arquitetura

O projeto é composto por dois microsserviços:

* **Service A** (`localhost:8000`) — realiza requisições ao Service B.
* **Service B** (`localhost:8001`) — disponibiliza os dados consumidos pelo Service A.

## Endpoints

Após iniciar o projeto, os principais serviços estarão disponíveis em:

| Serviço        | URL                     | Função          |
| -------------- | ----------------------- | --------------- |
| Service A      | `http://localhost:8000` | Microsserviço A |
| Service B      | `http://localhost:8001` | Microsserviço B |
| Grafana        | `http://localhost:3000` | Dashboards      |
| Prometheus     | `http://localhost:9090` | Métricas        |
| Tempo          | `http://localhost:3200` | Traces          |
| Loki           | `http://localhost:3100` | Logs            |
| OTel Collector | `localhost:4317`        | OTLP gRPC       |

## Objetivo

O objetivo do projeto é demonstrar, de forma prática, a utilização de **observabilidade em uma arquitetura de microsserviços**, permitindo acompanhar:

* **Logs** das aplicações;
* **Métricas** de execução;
* **Traces distribuídos** entre os microsserviços;
* Comunicação entre serviços;
* Visualização centralizada dos dados através do Grafana.

## Licença

Este projeto é destinado a fins educacionais e experimentais.
