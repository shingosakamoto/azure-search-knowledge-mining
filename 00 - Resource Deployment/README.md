
# Pre-Requisites for Knowledge Mining Workshop
Please make sure you fulfill the following pre-requisites before starting the workshop.

1. Have your own Azure account
2. Install the [Az PowerShell Module](https://docs.microsoft.com/powershell/azure/install-az-ps)
3. Make sure you can create Azure resources in your subscription (including paid resources).
Note, if your organizations policy prohibits you from creating resources in the subscription, you can use a free subscription for the purposes of this lab.


# Resource Deployment

There are two options for deploying the resources to Azure for this solution accelerator:

## **1. Quick Solution Deployment with PowerShell Script**: `deploy.ps1`

> If you're new to PowerShell, you can follow the instructions on [How to run PowerShell script file on Windows 10](https://www.windowscentral.com/how-create-and-run-your-first-powershell-script-file-windows-10) to help you get started.


To run the [PowerShell script](./deploy.ps1):

1-1. Open PowerShell and navigate to this folder.

```
cd "00 - Resource Deployment"
```

1-2. Run the following command:

```
./deploy.ps1
```
    
1-3. After running the script, you'll be prompted to login and provide additional information.

This script is the fastest way to get your solution up and running and will perform the following actions:

1. Provision the required Azure resources
2. Upload sample data to your storage account
3. Create a search index
4. Print out the values and keys needed for the web app's *appsettings.json*

If you choose to run this script, **you can skip the Search Index Creation** in the next folder.

<img src="2020-11-27 12_14_13-Photos.png"/>

## **2. Confirm Resources are Deployed in your Azure Subscription**

The PowerShell script will provision the following resources to your Azure subscription:

| Resource              | Usage                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------|
| [Azure Search Service](https://azure.microsoft.com/en-us/services/search/)  | The hosting service for the Search Index, Cognitive Skillset, and Search Indexer          |
| [Azure Cognitive Services](https://docs.microsoft.com/en-us/azure/search/cognitive-search-attach-cognitive-services)	| Used by the Cognitive Skills pipeline to process unstructured data	|
|[Azure Storage Account](https://azure.microsoft.com/en-us/services/storage/?v=18.24) | Data source where raw files are stored                                                     |
| [Web App](https://azure.microsoft.com/en-us/services/app-service/web/)               | The hosting service for the Search UI                                                     |
| [Application Insights](https://azure.microsoft.com/en-us/services/monitor/)  | Telemetry monitoring service for the Search UI (*Optional*)									|

By default, this PowerShell script will provision a Basic Search service for your solution. See [Azure Search Pricing](https://azure.microsoft.com/en-us/pricing/details/search/) for information on sizing limits, scaling limits and pricing and choose your desired tier. 

Depending on your custom skill development needs, additional Azure resources may be required.  See the README in the [03 - Data Science & Custom Skills](../03%20-%20Data%20Science%20and%20Custom%20Skills/README.md) folder for additional information.

## Notes

We recommend building an initial prototype solution leveraging a representative subset of data to estimate the size of your final search index.  When you are ready to build your final solution, you will want to size and provision your resources to meet your estimated scale and performance needs.

Please see [Azure Service Limits](https://docs.microsoft.com/en-us/azure/search/search-limits-quotas-capacity) for additional information and best practices on sizing.
