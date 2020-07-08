# Muliple VMs using inline deployments


[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F201-vm-copy-managed-disks%2Fazuredeploy.json)  [![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F201-vm-copy-managed-disks%2Fazuredeploy.json)  


This templates will provision N number of virtual machines with custom VM Index:
- Across multiple existing resources groups of choice.
- Across multiple existing Virtual Networks and Subnets of choice.
- Deploy VMs using popular Windows and Linux marketplace images.
- Uses existing Key Vault secrets for Local Admin Credentials. 
- Creates Availability sets and conditionally add VMs to them.
- Creates boot diagnostics storage accounts and conditionally enable boot diagnostics logs for the VMs.
    - Defaults: StorageV2 and Standard_LRS account.
- Conditionally create public IP and it the VM Network interfaces. Options to make it a static public IP.
- Ability to chose managed disk type.
- Conditionally deploy multiple data disks with different sizes.
- Conditionally add the Windows VMs being deployed to exisiting AD domains.  


![template resources](images/resources.png "template resource objects")

`Tags:Managed Disks, Azure VMs, Copy Index`