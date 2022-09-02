[![CircleCI](https://dl.circleci.com/status-badge/img/gh/shegs2020/project4-ml-microservices-kubernetes/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/shegs2020/project4-ml-microservices-kubernetes/tree/main)

## Project Overview

In this project, I applied the skills I had acquired in Udacity-ALX Cloud DevOps course to operationalize a Machine Learning Microservice API. 

I was given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. This project tested my ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Objective

The goal of this project is to operationalize a working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project, I:
* Tested my project code using linting
* Completed a Dockerfile to containerize this application
* Deployed my containerized application using Docker and made a prediction
* Improved the log statements in the source code for this application
* Configured Kubernetes and created a Kubernetes cluster
* Deployed a container using Kubernetes and made a prediction
* Uploaded a complete Github repo with CircleCI to indicate that my code has been tested


---
## Instructions
**How to run the Python scripts and web app:**
### Setup the Environment
* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## About files in this repository

### Dockerfile
It is a simple text file that consists of instructions to build Docker images.

### Makefile
A Makefile is a way of automating software building procedure and other complex tasks with dependencies. This Makefile contains: dependency rules, macros used to build the app.

### app.py
The python application that serves out predictions about housing prices through API calls

### make_prediction.sh
This shell script sends some input data to your containerized application via the appropriate port

### run_docker.sh
This shell script builds the container docker image and gets Docker running locally

### upload_docker.sh
This shell script uploads the built image to dockerhub

### run_kubernetes.sh
This script deploys the application in kubernetes.

### requirements.txt
This text file contains a list of dependencies referenced for Makefile to run.

### model_data
The model_data is the directory housing 'boston_housing_prediction.joblib' and 'housing.csv' which are files containing the Machinne Learning trained data used for the application.

### output_txt_files
The output_txt_files is the directory housing 'docker_out.txt' and 'kubernetes_out.txt' which are files containing the Docker and Kubernetes output logs respectively.

### .circleci
The .circleci directory is houses the 'config.yml' file which is used to test this repository and run it in a pipeline with CircleCI