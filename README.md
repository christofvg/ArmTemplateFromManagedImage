# ArmTemplateFromManagedImage
Demo ARM template to deploy a Managed Image using ARM templates

# Introduction

This template is based on the 101-vm-simple-windows quickstart template, available [here](https://github.com/Azure/azure-quickstart-templates/tree/master/101-vm-simple-windows).

Following parameters need to be passed at least:

* [string]adminUsername
* [securestring]adminPassword

These parameters can be passed optionally:

* [string]windowsOSVersion
* [string]location

## How to deploy

```powershell
#Create credential object
$Credential = Get-Credential

#Create resource group
New-AzureRmResourceGroup <ResourceGroupName> -Location <Location>

#Deploy ARM template
New-AzureRmResourceGroupDeployment -ResourceGroupName <ResourceGroupName> -TemplateFile .\deployM
anagedImage.json -Verbose -adminUsername $credential.UserName -adminPassword $credential.Password
```