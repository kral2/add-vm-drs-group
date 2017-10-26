# Author Details

Workflow Developed by: Sid Smith - http://www.dailyhypervisor.com  
Product Documentation available at:   

# Workflow Description

The workflow add a virtual machine to a pre-created vCenter VM DRS group during machine provisioning.  

# Workflow Type, and what it does

This is a State Transtion Event workflow that executes at the Machine Provisioned state.
This workflow will add the following objects to your vRA environment :

- a properties group with 3 properties :
	- sdset.addVirtualMachine.DRS.Group.Execute,
	- Extensibility.Lifecycke.Properties.VMPSMasterWorkflow32.MachineProvisionned,
	- sdeset.addVirtualMachine.DRS.Group <-- you will have to adjust this one to your particular DRS group name,
- a subcription event, to be used with the EBS.

# Workflow Installation

1. Import Package in to vRO
2. Run "Install Custom vCenter Folder" located under VMware -> SDE-SET -> vRealize Automation -> Custom vCenter Folder -> Configuration
3. In vRA edit property group created by installer

# Workflow customization and basic tshoot

You have to adjust the configuration file with the correct vraHost regarding your environment and set a meaningful value for the DRS Group name.

If you have authentication problems, check if you are using a vRA account with enough rights (inventory section). administrator@vsphere.local on default tenant will not be able to execute correctly the preparation workflows.

# Tested Product Versions

  vRA 7.0 / 7.0.1 / 7.3
  vCenter 6.0  
  
# Disclaimer


This workflow and it’s components are provided for informational purposes only without warrant and support .  
Included workflow and components are not intended for production use cases and should be used at your one risk.
