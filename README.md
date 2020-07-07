# Azure Orphaned Resources

This repository contains one single PowerShell script that is designed to serve as gentle intro to Azure Automation accounts. While many scripts out there focus on VM stop/restart, this script is more intended to do some housekeeping in the subscription, such as detect (and optionally delete) resources that are not used any more.

## How to use

1. Create an Azure Automation Account (see a quickstart [here](https://docs.microsoft.com/azure/automation/automation-quickstart-create-account))
2. Take note of the name of the automatically created connection (typically `AzureRunAsConnection`)
3. Find out your tenant's ID (for example, clicking on your user name in the top right corner of the Azure portal)
4. Create a new Powershell Runbook, and paste the code in the script in this repository
5. Replace the defaults with your tenant ID, and the name of the Run As connection (if it differs from `AzureRunAsConnection`)

## What the script does

It finds orphaned objects in Azures:

* Disks that are not connected to any VM
* NSGs not applied to a subnet or a NIC
* Public IP addresses not connected to a NIC
* NICs not connected to any VM

## Next steps

Enhance this script with other Azure housekeeping activities related to your organization
