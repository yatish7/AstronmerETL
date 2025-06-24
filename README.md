🚀 Overview

Welcome to my Driver Safety Data Pipeline Project with Apache Airflow! This project was built using the Astronomer CLI to run and orchestrate workflows locally using Apache Airflow. It demonstrates how to use Airflow for scheduling and executing real-time or batch data pipelines — a key part of any production-grade AI or analytics system.
📁 Project Structure

This Airflow project contains the following files and directories:
dags/ – Contains all the DAGs (Directed Acyclic Graphs) that define workflows.
example_astronauts.py – A sample ETL pipeline that fetches astronaut data from the Open Notify API and dynamically prints details using TaskFlow API and dynamic task mapping. This DAG was used as a base for testing and learning.
Dockerfile – Defines a versioned Astro Runtime image. This file can be customized to add OS-level packages or Python dependencies at runtime.
include/ – Placeholder for any additional files or scripts (e.g., SQL scripts, configs) I may want to include in my pipeline.
packages.txt – Used to list OS-level dependencies required by the project. Empty for now.
requirements.txt – Used to add Python libraries (e.g., requests, pandas, etc.) required in my DAGs. Custom dependencies can be added here.
plugins/ – A directory to store custom Airflow plugins, operators, or macros.
airflow_settings.yaml – A convenient local-only config to define Airflow Connections, Variables, and Pools, without needing to input them manually via the UI.
🧪 How to Run It Locally

1. Start Airflow
Start the local Airflow environment using Astronomer CLI:
astro dev start
This command starts the following Airflow components in Docker containers:
Postgres – Stores all Airflow metadata
Webserver – Powers the Airflow UI (accessible via browser)
Scheduler – Triggers and monitors DAG runs
Triggerer – Executes deferred tasks (e.g., sensors, async tasks)
2. Check Running Containers
Verify everything’s up and running with:
docker ps
Webserver should be available on http://localhost:8080.
Default login: Username: admin | Password: admin
Postgres should be running on: localhost:5432/postgres
3. Modify or Create Your Own DAGs
You can create your own DAGs inside the dags/ folder.
Restart the scheduler or webserver to pick up changes using:
astro dev restart
🚀 Deployment to Astronomer Cloud (Optional)

If you have access to Astronomer Cloud, you can deploy this project by linking it to a remote Deployment using:
astro deploy
See full instructions in Astronomer's Deployment Guide

💡 Use Case
This setup serves as a foundation for future projects involving:
ETL for driver behavior logs
Data validation pipelines for sensor inputs (e.g., GPS, emotion, distractions)
Preprocessing and aggregating data for ML training
Alert pipelines triggering push notifications based on event rules
