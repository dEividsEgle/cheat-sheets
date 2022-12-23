## Terraform Folder Structure

It is best practice to put each Terraform configuration files into seperate folder. This can be sperated by environments (staing, developing, production.) In adition to that each environment can have a different back end configured for it. This can be either in different subscription, storage container or similar. This will also help to separate the state files.

* Stage
	An environment for pre-production workloads (testing phase).
*  Mgmt
	An environment for DevOps tooling
* Global
	An environment where to store resources that are usec across all environments

Within each environment there can can be folders for each componenet.

- vnet
	Network topology, including subnets, asg, nsg, etc.
- services 
	Apps and microservices located within the environment.
- data-storage
	Data stores that are running within the environemnt. If multiple data stores are to be used, each could be put in it's own folder to further isolate them from each other.

Each component containes the Terraform configuration files.

- variables.tf
	Input variables.
- main.tf
	Reacources and data sources. If the *main.tf* starts to get very long, which it most likely will, it might be helpful to break it into smaller files that could group particualr resources in any prefered way. 
- outputs.tf
	Output variables.
- providers.tf
	Provider blocks and required authentication methods.
- dependencies.tf
	Data sources could also be put within the *dependencies.tf* file for better visibility in regard to any external dependencies.

