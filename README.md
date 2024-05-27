# APIM Learning Demo

## Steps to Provision

### Resource Group
```pwsh
az group create --name rg-apimlearn --location westeurope
```
### Log Analytics Workspace
```pwsh
az monitor log-analytics workspace create --resource-group rg-apimlearn --name log-apimlearn --location westeurope
```
### APIM
Used portal so far
### Container Apps Environment
```pwsh
az containerapp env create -n cae-apimlearn -g rg-apimlearn --location westeurope --logs-workspace-id myLogsWorkspaceID --logs-workspace-key myLogsWorkspaceKey 
```
### Container App From Local Code (it created the Azure Container Registry)
```pwsh
az containerapp up --name ca-apimlearn --source . --resource-group rg-apimlearn --environment cae-apimlearn 
```