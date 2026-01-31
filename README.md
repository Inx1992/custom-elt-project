Custom ELT Data Pipeline Project
📊 Project Overview
This project implements a modern ELT (Extract, Load, Transform) pipeline using the industry-standard data engineering stack. It automates the processing of Spotify and Airbnb datasets, moving them from raw files into a structured PostgreSQL data warehouse, with transformations handled by dbt and orchestration managed by Airflow.

🛠 Tech Stack
Orchestration: Apache Airflow

Transformation: dbt (Data Build Tool)

Containerization: Docker & Docker Compose

Database: PostgreSQL

Language: Python 

Version Control: Git

🏗 Architecture
Extract & Load: Python scripts move raw CSV data into a PostgreSQL "raw" schema.

Orchestrate: Airflow DAGs schedule and monitor the entire workflow.

Transform: dbt takes the raw data and applies business logic, creating clean, modeled tables (dim/fact) for analysis.

Environment: The entire stack is containerized using Docker for easy deployment and reproducibility.

🚀 Getting Started
To get this project running locally, ensure you have Docker and Docker Compose installed.

Clone the repository:

Bash
git clone https://github.com/Inx1992/custom-elt-project.git
cd custom-elt-project
Spin up the environment:

Bash
docker-compose up --build
Access the services:

Airflow UI: http://localhost:8080 (Default: admin/admin)

Postgres DB: localhost:5432

📂 Project Structure
/dbt: Contains dbt models, schemas, and transformation logic.

/dags: Airflow Directed Acyclic Graphs defining the pipeline workflow.

/scripts: Python scripts for initial data ingestion.

docker-compose.yml: Defines the interaction between Airflow, Postgres, and dbt.

📈 Key Results
Full Automation: Zero manual intervention required from raw data to final models.

Data Integrity: Implemented dbt tests to ensure data quality and schema consistency.

Scalability: The containerized approach allows for easy scaling and deployment to cloud environments.
