
# End-to-end Machine Learning Project with MLflow

This project demonstrates a comprehensive end-to-end machine learning workflow using MLflow for experiment tracking, model management, and deployment. It includes a structured approach to updating configuration files, components, and pipelines, as well as integration with AWS for CI/CD deployment.

## Key Features

- MLflow integration for experiment tracking and model management
- Modular project structure with separate configuration files
- AWS ECR and EC2 deployment pipeline using GitHub Actions
- DagsHub integration for remote MLflow tracking

## Workflow

1. Update configuration files (config.yaml, schema.yaml, params.yaml)
2. Modify entity definitions
3. Update configuration manager in src/config
4. Revise components and pipeline
5. Update main.py and app.py

## How to run?

### STEPS:

### Step 01 - Clone the repository

```bash
https://github.com/imakaash/end-To-EndMLOPSDataScienceProjectImplementationWithDeployment
```

### Step 02 - Create a conda environment after opening the repository

```bash
conda create  -n  mlproj  python=3.8  -y
```
```bash
conda activate  mlproj
```

### Step 03 - Install the requirements

```bash
pip install  -r  requirements.txt
```
```bash
# Finally run the following command
python app.py
```
Now, open up you local host and port.

## MLflow [Documentation](https://mlflow.org/docs/latest/index.html)

This project leverages MLflow for:

- Production-grade experiment tracking
- Comprehensive logging of all experiments
- Model versioning and tagging

  

### About [dagshub](https://dagshub.com/)

  

MLFLOW_TRACKING_URI=https://dagshub.com/imakaash/end-To-EndMLOPSDataScienceProjectImplementationWithDeployment.mlflow \

MLFLOW_TRACKING_USERNAME = imakaash \

MLFLOW_TRACKING_PASSWORD = 80952260f080c49d439bff85e27e3d3ab106779f \

python script.py

To use DagsHub for remote MLflow tracking, set the following environment variables:

```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/imakaash/end-To-EndMLOPSDataScienceProjectImplementationWithDeployment.mlflow

export MLFLOW_TRACKING_USERNAME=imakaash

export MLFLOW_TRACKING_PASSWORD=80952260f080c49d439bff85e27e3d3ab106779f
```

## AWS-CICD-Deployment-with-Github-Actions

The deployment process involves building a Docker image, pushing it to ECR, and launching it on an EC2 instance.

### 1. Login to AWS console.

### 2. Create IAM user for deployment

1. EC2 access : It is virtual machine
2. ECR: Elastic Container registry to save your docker image in aws

### 3. Description: About the deployment

1. Build docker image of the source code
2. Push your docker image to ECR
3. Launch Your EC2
4. Pull Your image from ECR in EC2
5. Lauch your docker image in EC2

### 4. Policy:

1. AmazonEC2ContainerRegistryFullAccess
2. AmazonEC2FullAccess

### 5. Create ECR repo to store/save docker image

Save the URI: 940482407040.dkr.ecr.eu-north-1.amazonaws.com/mlproj

### 6. Create EC2 machine (Ubuntu)

### 7. Open EC2 and Install docker in EC2 Machine:

```bash
#optional

sudo apt-get update -y

sudo apt-get upgrade


#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

### 8. Configure EC2 as self-hosted runner:

setting>actions>runner>new self hosted runner> choose os> then run command one by one

### 9. Setup github secrets:

```bash
AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = eu-north-1

AWS_ECR_LOGIN_URI = demo>> 940482407040.dkr.ecr.eu-north-1.amazonaws.com

ECR_REPOSITORY_NAME = mlproj
```

This project showcases best practices in MLOps, combining robust ML workflows with efficient cloud deployment strategies.