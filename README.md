# azure-enterprise-usagedata
template for an logic app which fetches the Azure usage data of an Azure enrollment on a monthly recurrance and drops a CSV file into an Azure File Service account. 
To access the files with the Azure usage data:
1. in Azure portal go to the resource group you deployed to
2. click on the name of the storage account
3. in the storage account overview blade, click on the tile 'Files'
4. In the file service blade, click on the file share named 'usage'
5. click on the file you want to download and select download from the context menu

## Deploy to Azure

**Please note:** After you have deployed, before you run the logic app, a file share named "usage" must be manually created in the storage account which is included in this deployment:
1. In the resource group you deployed to, click on the storage account name
2. In the storage account overview blade, click on the tile 'Files'
3. In the file service blade, click the '+ File share'-button
4. In the 'name'-field type in 'usage' and click 'OK'

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsimonschwingel%2Fazure-enterprise-usagedata%2Fmaster%2Ftemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

### Deployment Parameters

| Name          | Description                             |
| ------------- | ------------- | 
| Workflow_name | Will be used as name for your logic app |
| Storage Name Prefix | will be used as prefix of your storage name. To ensure that the name is unique, an alphanumeric sequence will be | | appended to the prefix for your final storage account name. |
| API_access_key | This is the API access key from your enterprise portal (https://ea.azure.com). You can copy the key under Reports > Download Usage > API Access Key > expand key > Copy . You can use either the primary or secondary key. The key will be automatically revoked every 5 months at the latest. In case your logic app stops working, please make suer that your key is still valid and update the key if necessary. |
| Azure_enrollment_number | This is the identifier of your Azure enrollment. You can find this id number i.e. in your enterprise portal (https://ea.azure.com) in the top left corner below the windows icon |
