# Distributed Computing Lab

## Overview

This repository contains a distributed computing lab completed as part of a Cloud Computing course.  
The objective of this project was to deploy and execute a data-processing workload inside a containerized and distributed environment using modern cloud-native tools.

The lab demonstrates how machine learning workloads can be packaged, deployed, and executed using container orchestration concepts commonly used in production cloud systems.

---

## Project Objectives

- Understand distributed computing fundamentals
- Containerize applications using Docker
- Deploy workloads using Kubernetes pods
- Execute Python-based data workloads in a distributed environment
- Practice reproducible cloud-native deployments

---

## Technologies Used

- **Python**
- **Docker** (containerization)
- **Kubernetes** (pod deployment)
- YAML configuration files
- CLI-based cloud workflow

---

## Repository Structure

```text
.
├── dockerfile                 # Container definition for application environment
├── pod.yml                    # Kubernetes pod configuration
├── lungcancer.py              # Python workload executed in container
├── lung_cancer_dataset.csv    # Dataset used for computation
├── COMMANDS.md                # Deployment and execution commands
└── README.md

```
### Distributed Computing Workflow

This project follows a typical cloud-native execution pipeline:

1. Package application and dependencies into a Docker container

2. Define infrastructure and runtime configuration using Kubernetes YAML

3. Deploy containerized workload as a pod

4. Execute data-processing script within distributed compute environment

This mirrors real-world distributed ML and data engineering deployments.

### Running the Project
Prerequisites:
  - Docker installed
  - Kubernetes cluster (local or cloud)
  - kubectl CLI configured

```bash
#Build Docker Image
docker build -t lungcancer-app .

#Deploy Kubernetes Pod
kubectl apply -f pod.yml

#Verify Pod Status
kubectl get pods

#View Logs
kubectl logs <pod-name>

#Cleanup
kubectl delete -f pod.yml
```

## Key Concepts Demonstrated
  - Containerized computation
  - Distributed workload execution
  - Kubernetes pod orchestration
  - Infrastructure configuration via YAML
  - Reproducible compute environments

## Learning Outcomes

Through this lab, I gained hands-on experience with:
  - Deploying Python workloads in containerized environments
  - Understanding how distributed systems execute compute jobs
  - Using Kubernetes to manage application lifecycle
  - Applying DevOps principles to data science workloads
  - Bridging machine learning workflows with cloud infrastructure

