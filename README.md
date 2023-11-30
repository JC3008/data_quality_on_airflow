
# Project Overview
========
This project aims to extract data from Kaggle and turn it available on GCP Big Query.
chosen technologies set is described bellow:
* Orquestration: Astro-Python-SDK
* Data Quality: SODA
* Data Transformations: DBT
* Storage DataLake: GCP
* Storage Data WareHouse: Big Query 

# Project Status
========
Containerization Docker:                Done
Python Script for extracting data:      Pending
Orquestration Extracting from source:   Pending
Orquestration Upload into GCS Datalake: Done
Orquestration Data Quality:             Done
Orquestration Transforming:             Pending

## Considerations about handy previous knowledge.
For this project it is nice to have previous experience with Python development, Docker CLI and Airflow practices. The Airflow enviroment is builded by performing Astro-Python-SDK. This appoach provides speed on building process and takes away some possible issues on setting up the dependencies.
It will be great if you are familiar with configuration files, as the SODA application uses it a lot for stablish connections and perform data quality assurance.
I intend to describe in detail all the requirements for making it as easier as possible.


## GCP enviroment setup
* Create an account if you don't have one.
* Create a bucket
* Create a Service Account with these privilegies:
    Storage Admin
    Bigquery Admin

* For this Service Account, create a new key.
    click on the service account name and look for the Keys menu.
    Create a new key and save it as Json inside include/GCP directory

Reestart or Start your astro dev

In the Airflow UI, add a new Connnection.

## SODA configuration:
* It is required to fill up the include\soda\configuration.yml with your credentials. 


Astro-SDK Overview
========

Welcome to Astronomer! This project was generated after you ran 'astro dev init' using the Astronomer CLI. This readme describes the contents of the project, as well as how to run Apache Airflow on your local machine.

Project Contents
================

Your Astro project contains the following files and folders:

- dags: This folder contains the Python files for your Airflow DAGs. By default, this directory includes two example DAGs:
    - `example_dag_basic`: This DAG shows a simple ETL data pipeline example with three TaskFlow API tasks that run daily.
    - `example_dag_advanced`: This advanced DAG showcases a variety of Airflow features like branching, Jinja templates, task groups and several Airflow operators.
- Dockerfile: This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.
- include: This folder contains any additional files that you want to include as part of your project. It is empty by default.
- packages.txt: Install OS-level packages needed for your project by adding them to this file. It is empty by default.
- requirements.txt: Install Python packages needed for your project by adding them to this file. It is empty by default.
- plugins: Add custom or community plugins for your project to this file. It is empty by default.
- airflow_settings.yaml: Use this local-only file to specify Airflow Connections, Variables, and Pools instead of entering them in the Airflow UI as you develop DAGs in this project.

Deploy Your Project Locally
===========================

1. Start Airflow on your local machine by running 'astro dev start'.

This command will spin up 4 Docker containers on your machine, each for a different Airflow component:

- Postgres: Airflow's Metadata Database
- Webserver: The Airflow component responsible for rendering the Airflow UI
- Scheduler: The Airflow component responsible for monitoring and triggering tasks
- Triggerer: The Airflow component responsible for triggering deferred tasks

2. Verify that all 4 Docker containers were created by running 'docker ps'.

Note: Running 'astro dev start' will start your project with the Airflow Webserver exposed at port 8080 and Postgres exposed at port 5432. If you already have either of those ports allocated, you can either [stop your existing Docker containers or change the port](https://docs.astronomer.io/astro/test-and-troubleshoot-locally#ports-are-not-available).

3. Access the Airflow UI for your local Airflow project. To do so, go to http://localhost:8080/ and log in with 'admin' for both your Username and Password.

You should also be able to access your Postgres Database at 'localhost:5432/postgres'.

Deploy Your Project to Astronomer
=================================

If you have an Astronomer account, pushing code to a Deployment on Astronomer is simple. For deploying instructions, refer to Astronomer documentation: https://docs.astronomer.io/cloud/deploy-code/

Contact
=======

The Astronomer CLI is maintained with love by the Astronomer team. To report a bug or suggest a change, reach out to our support.




