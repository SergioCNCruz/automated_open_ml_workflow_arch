# Automated OpenML Workflow Arch

## Challenge
ML Life cycle: The same way all others software solutions ML models also become deprecated sometimes: Sometimes the data do not reflect the users behaviors anymore or the technologies in the capitiation is better now them in the last time the models was created. So this indicate's for us that we need to have way to mesure and version data and trac the evolution of parameters and metrics obtained during the ml model trainning. Thinking in this cenario we have a lot of tools and tecnics that can help us to automate that proccess. This arch has the targt in to solve these and other problems around ML workflow   

![ML Workflow](./images/ml_workflow.svg)
## What it is:
This architecture is designed to enable the training of machine learning models, as well as the versioning of experiments, data, and code. It utilizes a series of services and tools to achieve this goal:

## How it works:
...

## Components:
- **Git**: Git is a distributed version control system used to track changes in the source code during software development. It is used in this project to version the source code of the machine learning models and training scripts.

- **DVC (Data Version Control)**: DVC is an open-source tool that allows versioning data and tracking changes over time. It works similarly to Git but is optimized for large files and datasets. DVC stores versioned data in a storage, such as MinIO, and maintains references in the remote Git repository. This allows precise control of data versions and reproducibility of experiments.

- **Azure DevOps Repo**: Azure DevOps Repo is a Git-based version control service provided by Microsoft as part of Azure DevOps. It is used as a code repository, where the source code of the machine learning models and training scripts are stored. Azure DevOps Repo integrates with other Azure DevOps services, such as CI/CD pipelines.

- **Azure DevOps Pipelines**: Azure DevOps Pipelines is a CI/CD service that allows automating the build, test, and deployment of applications. It is used in this project to create CI/CD pipelines that automate the training and deployment of machine learning models.

- **Azure Container Registry**: Azure Container Registry is an Azure service that allows storing and managing Docker container images. It is used in this project to store the Docker container images used to run the machine learning training.

- **Airflow**: Apache Airflow is a workflow automation and scheduling platform. In the context of this architecture, Airflow is used to execute machine learning training tasks automatically. It uses Directed Acyclic Graphs (DAGs) to define the execution logic of the training, creating Docker pods that run the training code. Airflow connects to the MLflow server to store the artifacts generated during training.

  - **DAG**: Airflow's Directed Acyclic Graph (DAG) is a visual representation of the steps the training pipeline will follow. Each DAG consists of a series of tasks that will be executed according to the logic defined in the DAG.

    - **Task**: Each task in a DAG represents a specific step in the training pipeline. Tasks can be executed in parallel or in series, depending on the pipeline requirements.

- **MLflow**: MLflow is an open-source platform for managing the machine learning lifecycle. It is used to register and track training experiments, as well as store artifacts generated during training, such as models, metrics, and logs. MLflow allows for experiment reproducibility and comparison between different model iterations.

- **MinIO**: MinIO is an open-source object storage server compatible with Amazon S3. It is used as a storage for artifacts generated during training, such as models, metrics, and MLflow logs, as well as the data versioned by DVC. MinIO allows scalable and secure storage of artifacts, ensuring data availability and integrity.

- **JupyterHub**: JupyterHub is a web application that allows the creation, management, and sharing of Jupyter notebooks. It is used in this project to provide a collaborative development environment for data scientists and machine learning engineers.

## How to Use

...