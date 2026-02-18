# Custom ELT Data Pipeline Project

A professional Python-based solution for automated entity resolution and analytical modeling across disparate datasets.

## 📁 Project Structure

- `dags/`: **Orchestration Layer** containing Airflow Directed Acyclic Graphs that define the pipeline workflow.
- `dbt/`: **Transformation Layer** featuring dbt models, schemas, and business logic for modular data modeling.
- `scripts/`: **Ingestion Engine** with Python-based logic for initial data extraction and loading.
- `docker-compose.yml`: **Infrastructure Manifest** orchestrating the interaction between Airflow, PostgreSQL, and dbt.

## 🛠 Modern ELT Architecture (Core Pipeline)

Unlike traditional ETL, this tool follows a **Load-then-Transform** approach to ensure data lineage and flexibility:

1. **Phase 1: Extract & Load (Python)**
    - Raw CSV datasets (Spotify & Airbnb) are ingested into a dedicated "raw" schema within the PostgreSQL data warehouse.
2. **Phase 2: Orchestration (Apache Airflow)**
    - Automated scheduling and monitoring of the entire workflow, ensuring dependency management between tasks.
3. **Phase 3: Transformation (dbt)**
    - Applies tiered business logic to raw data, generating optimized **Dimensional (dim)** and **Fact (fact)** tables for downstream analytics.

## 🔍 Data Quality & Engineering Features

- **Automated Schema Control**: Enforces consistency when moving data from raw files into structured warehouse tables.
- **Containerized Environment**: The entire stack is isolated via Docker for 1:1 parity between development and production.
- **Data Integrity**: Integrated dbt tests to ensure high-quality data and schema consistency across the pipeline.
- **Source Diversity**: Automates the processing of Spotify and Airbnb datasets into a unified warehouse.

## 📊 Performance Metrics (Current Run)

The latest pipeline execution achieved a high-quality linkage with the following breakdown:

- **Automation Level**: **100%** (Zero manual intervention required from raw data to final models).
- **Scalability**: High-fidelity containerized approach allows for easy deployment to cloud environments.
- **Environment**: Fully reproducible stack via Docker & Docker Compose.
- **Data Modeling**: Clean, structured (dim/fact) tables ready for business analysis.

## 🚀 Installation & Usage

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/Inx1992/custom-elt-project.git](https://github.com/Inx1992/custom-elt-project.git)
   cd custom-elt-project
   ```

2. **Spin up the environment**:
   ```bash
   docker-compose up --build
   ```

3. **Access the services**:
   - **Airflow UI**: `http://localhost:8080` (Default: `admin/admin`)
   - **Postgres DB**: `localhost:5432`

## ⚙️ Tech Stack Configuration (Tuning)

**The sensitivity and performance are controlled by the interaction of the following components**:

- **Orchestration**: Apache Airflow (Manages task dependencies and scheduling).
- **Transformation**: dbt (Handles SQL-based modeling, versioning, and testing).
- **Database**: PostgreSQL (Serves as the central Data Warehouse).
- **Language**: Python (Used for custom extraction and loading scripts).

## 📝 Technical Notes

- **The pipeline is considered Highly Reliable if**:
    - The Airflow DAG execution finishes with a **Success** status for all tasks.
    - **OR** the dbt test suite confirms data quality across all "dim" and "fact" models without failures.
