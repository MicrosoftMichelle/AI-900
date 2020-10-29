# AI-900
This repository contains ARM templates to automate AI-900 Lab deployments. 

## Lab 1: Azure Machine Learning

Start by signing into your Azure portal: 

![Azure Portal](images/azure-portal.png)

In the top bar, click on the cloud shell icon to open up Azure cloud shell. 

<i>Note: You may need to provision storage for your cloud shell if you are opening up Azure cloud shell for the very first time.</i>

![Azure Cloud Shell Icon](images/cloud-shell.png)

Alternatively, you can open up a separate tab and type into your browser: *shell.azure.com*. This will also open up an instance of Azure cloud shell that does not overlay on top of the Azure portal:

![shell.azure.com](images/alternative-shell.png)

Now, from this repository, download a compressed (zip) version of all the folder and files in this repository: 

![Download a zip file from this repository](images/download-zip.png)

Unzip the AI-900 folder: 

![Unzip the AI-900 folder](images/unzip-AI-900-folder.png)

Back in your Azure cloud shell, go ahead and upload the ml-template.json file to your cloud shell: 

![Upload ml-template json file to Azure cloud shell](images/upload-aml-file-to-cloud-shell.png)

Once the upload has completed (it should only take a second or two), execute the following commands in your Azure cloud shell: 

```azurecli
az group create --name AI-900 --location "East US"
```

![Create a resource group using Azure CLI](images/create-resource-group.png)
That command creates a resource group called 'AI-900' which is where you will provision all your Azure resources for this lab. We have specified the Azure region to use one of the 'East US' datacentres but you are more than welcome to change this if you want. 

Then, execute this command next: 

```azurecli
az deployment group create --name ml-template --resource-group AI-900 --template-file ml-template.json
```

![Deploy the Azure Machine Learning ARM template](images/execute-aml-template-command.png)

There are a couple of resources that needs to be spun up here so this will take a few minutes. While you wait, this will be a good time to go give your instructors a thumbs up or gif in the chat or make a new batch of tea or coffee or pop off for a quick bathroom break (but not too long)!

Once your resources have deployed, navigate back to your Azure portal and you should see something like this: 

![View provisioned Azure Machine Learning resources in the Azure portal](images/provisioned-aml-resources.png)

Now, all you have to do is open up Azure Machine Learning Studio and you can go ahead and follow the rest of the Azure Machine Learning lab by accessing the [instructions here](https://docs.microsoft.com/en-us/learn/modules/use-automated-machine-learning/create-compute). Good luck, if you get stuck, remember to let your instructors know!

![Open up Azure Machine Learning Studio](images/open-up-aml-studio.png).

