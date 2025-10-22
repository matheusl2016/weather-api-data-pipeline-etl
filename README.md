# Weather API Data Pipeline

## Descrição (Português)

O **Weather API Data Pipeline** é um projeto desenvolvido em **Python** que demonstra o processo completo de **extração, transformação e carregamento (ETL)** de dados climáticos em tempo real utilizando a **WeatherAPI**.

O objetivo é construir um **pipeline de dados automatizado**, capaz de:
- Coletar informações meteorológicas em tempo real da cidade de **Limeira/SP**;
- Tratar e organizar os dados de forma estruturada;
- Armazenar as informações em um banco de dados local (**SQLite**);
- Gerar visualizações analíticas (gráficos de temperatura).

Este projeto foi desenvolvido como uma aplicação prática para **Analistas de Dados Jr.** que desejam demonstrar domínio em **APIs, ETL, manipulação e visualização de dados.**

---

## Tecnologias Utilizadas

- Python 3.12+
- Pandas (tratamento e transformação de dados)
- Requests (integração com API)
- Matplotlib (visualização de dados)
- SQLite3 (armazenamento local)
- WeatherAPI (fonte de dados climáticos)

---

## Etapas do Pipeline ETL

### 1. Extração (Extract)
- Conecta-se à **WeatherAPI** utilizando uma **API Key**.
- Obtém dados meteorológicos em tempo real (`/current.json`) para Limeira/SP.
- Salva a resposta bruta (JSON) em `data/raw/weather_raw.json`.

### 2. Transformação (Transform)
- Seleciona campos relevantes: temperatura, condição, vento, umidade, data e hora da coleta.
- Converte os dados em um formato estruturado (DataFrame).
- Exporta para `data/processed/weather_processed.csv`.

### 3. Carga (Load)
- Insere os dados no banco **SQLite** (`data/weather_data.db`).
- Mantém o histórico das coletas sem sobrescrever registros anteriores.

---

## Visualização (Análise de Temperatura)

O pipeline gera automaticamente um gráfico de variação de temperatura com base nas coletas armazenadas no banco de dados.

O gráfico exibe apenas um ponto neste momento, pois até agora foi realizada uma única execução do script.  
Isso é intencional, já que o pipeline registra uma nova coleta a cada execução, simulando um sistema de monitoramento em tempo real.

Em um ambiente de produção, o script pode ser agendado para rodar periodicamente (por exemplo, de hora em hora), permitindo:
- Monitorar a variação real da temperatura ao longo do tempo;
- Criar dashboards de tendências e alertas climáticos;
- Aplicar análises preditivas com dados históricos.

---

## Próximas Melhorias

- Automatizar as coletas com **schedule** ou **cron jobs**  
- Adicionar o endpoint `history.json` da WeatherAPI para dados históricos  
- Implementar relatórios automáticos em **PDF**  
- Criar previsões com modelos de regressão  
- Publicar o pipeline na nuvem, como na AWS ou no GCP

---

# Version in English

# Weather API Data Pipeline

## Description

The **Weather API Data Pipeline** is a **Python** project that demonstrates the complete **Extract, Transform, and Load (ETL)** process using real-time weather data from the **WeatherAPI**.

The goal is to build an **automated data pipeline** capable of:
- Collecting real-time weather information for the city of **Limeira/SP, Brazil**;
- Cleaning and structuring the collected data;
- Storing the data in a local **SQLite** database;
- Generating analytical visualizations such as temperature charts.

This project was developed as a practical example for **Junior Data Analysts** who want to demonstrate proficiency in **APIs, ETL processes, data manipulation, and visualization**.

---

## Technologies Used

- Python 3.12+
- Pandas (data cleaning and transformation)
- Requests (API integration)
- Matplotlib (data visualization)
- SQLite3 (local database storage)
- WeatherAPI (weather data provider)

---

## ETL Pipeline Stages

### 1. Extract
- Connects to the **WeatherAPI** using a valid **API Key**.
- Retrieves real-time weather data (`/current.json`) for Limeira/SP.
- Saves the raw response (JSON) in `data/raw/weather_raw.json`.

### 2. Transform
- Selects relevant fields: temperature, condition, wind speed, humidity, and timestamp.
- Converts the JSON response into a structured format (Pandas DataFrame).
- Exports the cleaned data to `data/processed/weather_processed.csv`.

### 3. Load
- Inserts the processed data into a local **SQLite** database (`data/weather_data.db`).
- Maintains a historical record of all data collections without overwriting previous entries.

---

## Visualization (Temperature Analysis)

The pipeline automatically generates a temperature variation chart based on the data stored in the database.

Currently, the chart displays only one point because the script has been executed once.  
This is intentional, as each execution represents a new data collection, simulating a **real-time monitoring system**.

In a production environment, the script can be scheduled to run periodically (e.g., every hour), allowing:
- Monitoring of temperature variation over time;
- Creation of dashboards for trend analysis and weather alerts;
- Predictive analytics using historical data.

---

## Future Improvements

- Automate data collection using **schedule** or **cron jobs**  
- Add the `history.json` endpoint from WeatherAPI to retrieve historical weather data  
- Implement automatic **PDF reporting**  
- Add forecasting models using regression  
- Deploy the pipeline to the cloud (AWS or GCP)
