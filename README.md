# Maji Ndogo Data Pipeline

## Overview

The **Maji Ndogo Data Pipeline** is a modular ETL (Extract, Transform, Load) project that processes agricultural survey and weather datasets from the fictional nation of **Maji Ndogo**. Designed to reflect real-world agricultural systems across Africa, the project demonstrates how data engineering can improve data quality and support reliable, data-driven decision-making.

The pipeline automates data ingestion, cleaning, validation, and preparation while following software engineering best practices, including object-oriented programming (OOP), modular architecture, configuration-driven development, logging, and automated testing.

---

## Features

* Extracts farm survey data from a SQLite database.
* Loads weather data from CSV files hosted online.
* Cleans and standardizes agricultural and weather datasets.
* Corrects inconsistent and misspelled categorical values.
* Maps farm locations to their nearest weather stations.
* Performs automated data quality validation using **Pytest**.
* Validates data using statistical hypothesis testing with **SciPy**.
* Produces clean, analysis-ready Pandas DataFrames for Exploratory Data Analysis (EDA).

---

## Project Structure

```text
maji-ndogo-data-pipeline/
├── data/
│   └── Maji_Ndogo_farm_survey_small.db
├── notebooks/
│   └── eda.ipynb
├── src/
│   ├── __init__.py
│   ├── config_params.py
│   ├── data_ingestion.py
│   ├── data_field_processor.py
│   └── weather_data_processor.py
├── tests/
│   └── validate_data.py
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/CatherineNditu/Maji-Ndogo-Data-Pipeline.git
cd Maji-Ndogo-Data-Pipeline
```

### 2. Create a virtual environment

**Windows (Command Prompt)**

```bash
py -m venv venv
venv\Scripts\activate
```

**Windows (PowerShell)**

```powershell
py -m venv venv
venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

> **Note:** The SQLite database (`Maji_Ndogo_farm_survey_small.db`) is excluded from this repository via `.gitignore`. Place the database inside the `data/` folder before running the pipeline.

---

## Usage

```python
from src.config_params import config_params
from src.data_field_processor import FieldDataProcessor
from src.weather_data_processor import WeatherDataProcessor

# Process field survey data
field_processor = FieldDataProcessor(config_params)
field_processor.process()
field_df = field_processor.df

# Process weather data
weather_processor = WeatherDataProcessor(config_params)
weather_processor.process()
weather_df = weather_processor.weather_df
```

---

## Running Tests

Run the automated validation tests using:

```bash
pytest tests/validate_data.py -v
```

---

## Technology Stack

* Python
* Pandas
* SQLAlchemy
* SQLite
* SciPy
* Pytest
* Logging

---

## Skills Demonstrated

This project demonstrates practical experience in:

* ETL pipeline development
* Data ingestion and transformation
* Data cleaning and preprocessing
* Statistical data validation
* Object-Oriented Programming (OOP)
* Modular software architecture
* Configuration management
* Automated testing with Pytest
* Git and GitHub version control
* Exploratory Data Analysis (EDA)

---

## Future Improvements

* Add workflow orchestration with Apache Airflow.
* Containerize the pipeline using Docker.
* Implement CI/CD with GitHub Actions.
* Integrate cloud storage for scalable data processing.
* Add data quality monitoring and reporting.

---

## Project Status

**Work in Progress**

This project is part of my Data Engineering portfolio and demonstrates how to build production-inspired ETL pipelines using Python, SQL, testing, and software engineering best practices.

---

## Author

**Catherine Wairimu Nditu**

* GitHub: https://github.com/CatherineNditu
* LinkedIn: https://www.linkedin.com/in/catherine-wairimu-nditu/
