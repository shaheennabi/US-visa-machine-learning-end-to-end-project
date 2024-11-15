# 🎇 US_VISA End-to-End Machine Learning Project with Evidently AI 🎇

In this project we have implemented end-to-end machine learning project named: US_VISA, we got the dataset from kaggle and we used MongoDB for storing and retreiving data, later we build entire pipeline like Data Ingestion, Data Validation, Data Transformation, Data Trainer, Data Evaluation, Data Pusher, Prediction pipeline etc, and we used EvidentlyAI to detect data drift and we used Github Actions to automate entire pipeline. We containerized the project with Docker and later used some AWS services like AWS S3 Bucket, AWS ECR, AWS EC2, for storing and retraining model, storing Docker image and running entire project respectively. 🎉🚀

---

## 🎉 How to Run

To run this project, keep the original content unchanged. 🌟


```bash
conda create -n visa python=3.8 -y

```
```bash
conda activate visa
```
```bash
pip install -r requirements.txt
```


### Export the  environment variable(git bash)

# Workflow
After creating project template
 * Update constants 
 * Update Entiry modules
 * Update respective component
 * Update pipeline

 # AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

With specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


## Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

* Policy:

	* AmazonEC2ContainerRegistryFullAccess

	* AmazonEC2FullAccess

    * AWSS3BucketFullAccess

	
## 3. Create ECR repo to store/save docker image
    - (example) Save the URI:  31586523395366.dkr.ecr.us-east-1.amazonaws.com/visarepo

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
* Copy the below command one-by-one and execute on EC2 Terminal

```bash
sudo apt-get update -y
```
	
```bash
sudo apt-get upgrade
```
	
* required

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
```

```bash
sudo sh get-docker.sh
```

```bash
sudo usermod -aG docker ubuntu
```

```bash
newgrp docker
```

	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os>

* then run command one by one on EC2 Terminal 


# 7. Setup github secrets:

   - AWS_ACCESS_KEY_ID
   - AWS_SECRET_ACCESS_KEY
   - AWS_DEFAULT_REGION
   - ECR_REPO (URI or repo name)



# Project Tree Structure
```bash
.
└── US-VISA-MACHINE-LEARNING-END-TO-END-PROJECT/
    ├── .github/workflows/
    │   └── aws.yaml
    ├── artifact/
    │   └── 10_05_2024_03_23_14 (or time Stamp)/
    │       ├── data_ingestion/
    │       │   ├── feature_store/
    │       │   │   └── EasyVisa.csv
    │       │   └── ingested/
    │       │       ├── test.csv
    │       │       └── train.csv
    │       ├── data_transformation/
    │       │   ├── transformed/
    │       │   │   ├── test.npy
    │       │   │   └── train.npy
    │       │   └── transformed_object/
    │       │       └── preprocessing.pkl
    │       ├── data_validation/
    │       │   └── drift.repot/
    │       │       └── report.yaml
    │       └── model_trainer/
    │           └── trained_model/
    │               └── model.pkl
    ├── config/
    │   ├── model.yaml
    │   └── schema.yaml
    ├── flowchat
    ├── logs
    ├── notebook/
    │   ├── caboost
    │   ├── boston_data_drift_report.html
    │   ├── data_drift_demo_evidently.ipynb
    │   ├── EasyVisa.csv
    │   ├── EDA_us_visa_ipynb
    │   ├── Feature_Engineering_and_Model_Training.ipynb
    │   └── mongodb_demo.ipynb
    ├── static/
    │   └── css/
    │       └── style.css
    ├── templates/
    │   └── usvisa.html
    ├── us_visa/
    │   ├── __init__.py
    │   ├── __pycache__/
    │   ├── cloud_storage/
    │   │   ├── __init__.py
    │   │   └── aws_stroage.py
    │   ├── components/
    │   │   ├── __pychache__/
    │   │   ├── __init__.py
    │   │   ├── data_ingestion.py
    │   │   ├── data_transformation.py
    │   │   ├── data_validation.py
    │   │   ├── model_evaluation.py
    │   │   ├── model_pusher.py
    │   │   └── model_trainer.py
    │   ├── configuration/
    │   │   ├── __pycache__
    │   │   ├── logs/
    │   │   ├── __init__.py
    │   │   ├── aws_connection.py
    │   │   └── mongo_db_connection.py
    │   ├── constants/
    │   │   ├── __pycache__/
    │   │   └── __init__.py
    │   ├── data_access/
    │   │   ├── __pycache__/
    │   │   ├── __init__.py
    │   │   └── usvisa_data.py
    │   ├── entity/
    │   │   ├── __pycache__/
    │   │   ├── __init__.py
    │   │   ├── artifact_entity.py
    │   │   ├── config_entity.py
    │   │   ├── estimator.py
    │   │   └── s3_estimator.py
    │   ├── exception/
    │   │   ├── __pycache__/
    │   │   └── __init__.py
    │   ├── logger/
    │   │   ├── __pycache__/
    │   │   └── __init__py
    │   ├── pipeline/
    │   │   ├── __pycache__/
    │   │   ├── __init__.py
    │   │   ├── prediction_pipeline.py
    │   │   └── training_pipeline.py
    │   └── utils/
    │       ├── __pycache__/
    │       ├── __init__.py
    │       └── main_utils.py
    ├── us_visa.egg-info
    ├── .dockerignore
    ├── .gitignore
    ├── app.py
    ├── demo.py
    ├── Dockerfile
    ├── LICENSE
    ├── README.md
    ├── requirements.txt
    ├── setup.py
    └── template.py
```













