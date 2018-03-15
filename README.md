# azure-enterprise-usagedata
template for an logic app which fetches the Azure usage data of an Azure enrollment on a monthly recurrance and drops a CSV file into an Azure File Service account.

## Deploy to Azure

**Please note:** After you have deployed, before you run the logic app, a file share named "usage" must be manually created in the storage account which is included in this deployment:
1. In the resource group you deployed to, click on the storage account name
2. In the storage account overview blade, click on the tile 'Files'
3. In the file service blade, click the '+ File share'-button
4. In the 'name'-field type in 'usage' and click 'OK'

### via Azure Portal

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsimonschwingel%2Fazure-enterprise-usagedata%2Fmaster%2Ftemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

