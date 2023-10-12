# Lab 1

## Task

The Task was to create an ARM template.

- Create an ARM template that
    - Deploys an Azure Storage Account (Free Tier)
    - Deploys an Azure Web-App (Free Tier)
- Leverages Parameters
    - Name of the storage account, resource group, location, web-app name

I used this [Tutorial](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-cli) as a Guide.


## Steps

- Login with Azure CLI:
    ```bash
    az login
    ```

- choose the subscription:
    ```bash
    az account set --subscription "Azure for Students"
    ```

- create resource group:
    ```bash
    az group create \
    --name softwareDeploymentLab \
    --location 'Germany West Central'
    ```

- deploy template:
    ```bash
    templateFile="azuredeploy.json"
    az deployment group create \
        --name myTemplate \
        --resource-group softwareDeploymentLab \
        --template-file $templateFile
    ```