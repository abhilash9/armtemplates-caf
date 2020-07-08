# Deploy muliple VMs across resource groups/VNets/Subnets using inline deployments 
*By defining simple VM objects with several conditional properties.*


[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fabhilash9%2Farmtemplates-caf%2Fmaster%2FVM-Create-Objects-Inline%2Fazuredeploy.json)


By defining VM objects of the array parameter "VM Config", this templates will provision N number of virtual machines with custom VM Index:
- Across multiple existing resources groups of choice, any region of choice.
- Across multiple existing Virtual Networks and Subnets of choice.
- Deploy VMs using popular Windows and Linux marketplace images.
- Uses existing Key Vault secrets for Local Admin Credentials. 
- Creates Availability sets and conditionally add VMs to them.
- Creates boot diagnostics storage accounts and conditionally enable boot diagnostics logs for the VMs.
- Conditionally create public IP and it the VM Network interfaces. Options to make it a static public IP.
- Ability to chose managed disk type.
- Conditionally deploy multiple data disks with different sizes.
- Conditionally add the Windows VMs being deployed to exisiting AD domains.  

#### **Each VM Object can be used to deploy multiple instances of similar kind of VMs deployed to a Resource Group, VNET and Subnet - Each object will invoke a separate inline deployment (bydefault in serial mode)**

## Pre-requisites
- Existing Resource Group to deploy the VM and the required resources. 
- Existing Virtual Network and Subnets
- Existing KeyVault with predefined secrets for local admin and domain admin credentials.
- User deploying the templates is required to have access to keyvault secrets and atleast Contributor access to deploy the VMs.
- Optional - Existing domain to domain the VMs, with secrets defined in the same KeyVault with local admin secret.  

## CLI - Usage
*az deployment sub create -n NewDeploy -p azuredeploy.parameters.json -f azuredeploy.json -l eastus --debug --verbose*

![template deployments](VM-Create-Objects-Inline/images/Deployments.PNG "template resource objects")

![template resources](VM-Create-Objects-Inline/images/ResourceDeployed.PNG "template resource objects")

`Tags: Azure VMs, VM Objects, Inline Deployment, Copy Index, AVSets, Boot Diag Storage Account, Public IP, Managed Disks `

