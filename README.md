# Customer_Intelligence_Pipeline
This is a real time Intelligence Platform built for analysing the Customer Reviews with real time LLM reasoning using Azure Open AI and databricks.This project implements a production-grade Medallion Architecture using Azure Databricks, ADLS Gen2, and Azure OpenAI (GPT-4o). It processes over 1GB of synthetic customer feedback data,transforming raw, unstructured text into actionable business insights through Large Scale Reasoning (LLM integration).

Tech Stack & Architecture
Compute: Azure Databricks (Spark SQL & PySpark)

Storage: Azure Data Lake Storage (ADLS Gen2) with Delta Lake format

AI/ML: Azure OpenAI (GPT-4o) for Sentiment Analysis & Entity Extraction

Security: Azure Key Vault with Databricks Secret Scopes (Zero-Trust Architecture)

Orchestration: Databricks Workflows (Scheduled Jobs)

DevOps: GitHub integration via Databricks Repos

Data Pipeline Stages
Ingestion (Bronze): Automated ingestion of 5M+ records (1GB+) of raw parquet data into ADLS Gen2.

Transformation (Silver): Data cleaning, schema enforcement, and audit logging using Delta Lake ACID transactions.

Intelligence (Gold): Distributed Spark UDF integration calling Azure OpenAI API to categorize customer sentiment and identify operational bottlenecks (e.g., "Wait Time," "Food Quality").

Serving: Aggregated business metrics ready for Power BI/Tableau visualization.

Security & Scalability Features
Secret Management: No hardcoded API keys; all credentials fetched dynamically from Azure Key Vault.

Cost Optimization: Implemented Single-Node Cluster configurations with auto-termination to stay within Azure Free Tier limits.

Modular Design: Codebase is split into functional modules (Ingestion, Transformation, AI) for maintainability and CI/CD readiness.

How to Run
Configure Azure Key Vault with your OpenAI API Key.

Link your Databricks Workspace to this repository.

Execute the 00_Data_Generator to seed the Data Lake.

Run the Customer_Intelligence_Pipeline_PROD Workflow.

Key Learnings
Handling big data volumes (1GB+) in a distributed spark environment.

Configuring RBAC (Role-Based Access Control) between Databricks and Key Vault.

Integrating LLMs into data pipelines at scale using parallel processing.
