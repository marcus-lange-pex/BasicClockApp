# Basic Clock

This is a fork of this clock app that includes deployments for Azure Kubernetes Service and Docker.


### App Service Deployment Method:

In Azure cloud shell:

```

git clone https://github.com/marcus-lange-pex/pexeda-BasicClockApp.git

az group create  --name $NAME --location eastus

az network vnet create --name $nameVNET --resource-group $NAME  --subnet-name default

az acr create --resource-group $NAME--name $NAMEacr --sku Basic --admin-enabled true

az acr build  --registry $NAMEacr --image react-clock-basic:v1 .
```

Go to portal in Azure, create a new app service, select your resource group, pick linux, pick docker container, create a new service plan, select dev/test - click Docker

Drop down source, select Azure Container Registry.  Click the registry you created above then select the image name and version.

Click Review and create.  