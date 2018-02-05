# Azure Container Instance

# Start with ACI
```
#Create the resource group
az group create --name cloud-shell-storage-edith-eastus --location eastus

#Short mode
az group create -n cloud-shell-storage-edith-eastus -l eastus

#Asign cpu and memory
az container create -g cloud-shell-storage-edith-eastus --name nginx --image library/nginx --ip-address public --cpu 1 --memory 5

#Create the azure container instance
az container create --resource-group cloud-shell-storage-edith-eastus --name demo --image microsoft/aci-helloworld --ip-address public --ports 80

#Show instans
az container show --resource-group cloud-shell-storage-edith-eastus --name demo

#Show Logs
az container logs --resource-group cloud-shell-storage-edith-eastus --name demo

#Delete de instance
az container delete --resource-group cloud-shell-storage-edith-eastus  --name demo

#Show the details in a lits aci
az container list --resource-group cloud-shell-storage-edith-eastus --output table

```

```
# Jenkins in ACI
az container create --image jenkins/jenkins:lts-alpine --name jenkins --resource-group cloud-shell-storage-edith-eastus --ip-address public --port 8080
az container list
```