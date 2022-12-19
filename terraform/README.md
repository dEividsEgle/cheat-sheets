
- Validation
	- You can add validation block to any input variable to ensure that the values the user passes in -are one of the specified allowed values. For example, this could accept only specific type of -----SKU when deploying VM's.
- Precondititon and postconditions
	- Precondition and postcondition blocks can be added to resources, data sources, and outputs to perform dynamic checks. This is to catch errors before you run apply. 
- Provisioners
	- Provisioners are used to execute scripts either on local machine or remote machine. Provisioners can be added to a resource using *provisioner* block.

## Terraform files ##

- *.terraform.lock.hcl* records the following information
	- The exact version of provider used. 
		- If you run *terraform init* on this or any other computer, terraform will download the exact same version of each provider.
	-  The checksum for each provider
		- Terraform will record checksum of each provider it downloads, and on subsequent runs of terraform init. This is a security measure to ensure that someone cannot swap out provider code with malicious code.
		- Terraform only records checksum for the platform you ran *terraform init* on; you must run *terraform providers lock* command to record the checksum for every platform that is being used.

