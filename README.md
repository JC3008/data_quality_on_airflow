
Project Overview
========
This project aims to extract data from Kaggle and turn it available on GCP Big Query.
chosen technologies set is described bellow:
* Orquestration: Astro-Python-SDK
* Data Quality: SODA
* Data Transformations: DBT
* Storage DataLake: GCP
* Storage Data WareHouse: Big Query 

Project Status
========
* Containerization Docker:                Done
* Python Script for extracting data:      Pending
* Orquestration Extracting from source:   Pending
* Orquestration Upload into GCS Datalake: Done
* Orquestration Data Quality:             Done
* Orquestration Transforming:             Pending

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



