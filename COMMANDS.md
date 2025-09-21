```bash
docker build -t pqhdistributedcomputelab .
docker run -it --name pqh_distlab_01 pqhdistributedcomputelab /bin/bash
#docker run -v ./:/mnt/datalake/instructor -it --name pqh_distlab_01 pqhdistributedcomputelab /bin/bash
```
## Push to Azure Container Registry

```bash
## Log into Azure
az login

## Set the default Azure Subscription (if not prompted)
# az account set --subscription b92ea061-7db2-40ee-ad4a-cee871832b64

## Log into the Azure Container Registry
#az acr login --name <REGISTRY_NAME>
az acr login --name crdsba6190deveastus001

## Tag the image with the container registry information
docker tag pqhdistributedcomputelab crdsba6190deveastus001.azurecr.io/pqhdistributedcomputelab:latest
# docker tag instructor_sklearn crdsba6190deveastus001.azurecr.io/instructor_sklearn:latest

## Push the image to the container registry
docker push crdsba6190deveastus001.azurecr.io/pqhdistributedcomputelab:latest
# docker push crdsba6190deveastus001.azurecr.io/instructor_sklearn:latest

#get the azure Kubernetes service credential for kubexctl to use
az aks get-credentials --resource-group rg-dsba6190-class-eastus-001 --name kub-dsba6190-class-dev-eastus-001 --overwrite-existing

#apply kubernetes Pod
kubectl apply -f pod.yml
# kubectl apply -f example_pod.yml

#remote into pod
kubectl exec -it pqhpod -- /bin/bash
# kubectl exec -it instructor-test-01 -- /bin/bash

#run script
python lungcancer.py
# python train.py

#delete pod
kubectl delete pod pqhpod
# kubectl delete pod instructor-test-01



