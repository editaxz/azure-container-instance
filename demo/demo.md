# Azure Container Instance

# Start with ACI

## List the resource group
```
az group list --o table
```

## Delete a resource gtroup
```
az group delete -n demo01
```

## Create the resource group en el este de eeuu
```
az group create --name demo01 --location eastus
```

## Create a container instamce in azure - short mode (docker hub microsoft)
```
az container create --resource-group demo01 --name helloworld --image microsoft/aci-helloworld --ip-address public --ports 8082
```

## Create a container instance in azure - asign cpu and memory (docker hub nginx)
```
az container create -g demo01 --name nginx --image library/nginx --ip-address public --cpu 1 --memory 5
```

## Create a container instance in azure from azure registry (acr microsoft)
```
az container create --name acrhelloworld04 --image fisica3.azurecr.io/fisica3/helperconfig --registry-password 88GYVMmQ9Qqq8sM+1GQ2FHnq0PTSb/Ja --ip-address public -g demoACIViernesto --ports 5000
```

## Create the container in azure - windows (docker hub microsoft)
```
az container create --name helloworld --image microsoft/iis:nonoserver -g acidemog --ports 8083 --ip-address public --cpu 2 --memory 3.5 --os-type windows
```

#Consultas

## Show instances
```
az container show --resource-group demo01 --name helloworld
```

## show logs
```
az container logs --resource-group demo01 --name helloworld
```
## Delete instance
```
az container delete --resource-group demo01 --name helloworld
```
## Show the container details in a lits aci
```
az container list --resource-group cloud-shell-storage-edith-eastus --output table
```

## helloworld imagen
```
https://github.com/Azure-Samples/aci-helloworld
```

# Optional
## Jenkins in ACI
```
az container create --image jenkins/jenkins:lts-alpine --name jenkins --resource-group demo01 --ip-address public --port 8080
```

## list all containers
```
az container list
```


