## Table of Contents ##
----
## [General](#General) ##
* #### [Subscriptions](#Subscriptions)####
* #### [Resource Group](#Resource Group)####
- - - -
## [Resources](#Resources) ##




## General ##

| Resource Type | Prefix | Name |
| --- | ---  | ---|
| App Service (Web App) | app | {Customer}-app-{App Name}-{Environment}-{###} |
| App Service plan | plan- | {Customer}-plan-{App Name}-{Environment} |
| Azure Cognitive Search | srch- | {Customer}-srch-{App Name}-{Environment} |
| Azure SQL Database server | sql- | {Customer}-sql-{App Name}-{Environment} |
| Azure SQL database | sqldb- | {Customer}-sqldb-{Database Name}-{Environment} |
| Backup Vault | bvault- | {Customer}-bvault-{Environment} |
| Cosmos DB database | cosmos- | {Customer}-cosmos-{App Name}-{Environment} |
| Function app | func- | {Customer}-func-{App Name}-{Environment} |
| Event hub | evh- | {Customer}-evh-{App Name}-{Environment} |
| Recovery Services Vault | rsvault | {Customer}rsvault{Region}{Environment} |
| Resource group | rg- | {Customer}-rg-{App Name}-{Environment} |
| Service Bus | sb- | {Customer}-sb-{App Name}-{Environment} |
| Service Bus queue | sbq- | sbq-{query descriptor} |
| Service Bus topic | sbt- | sbt-{query descriptor} |
| Storage account (general use) | st- | {Customer}st{storage name}{###} |
| Virtual Machine | vm | {Customer}vm{App Name}{###} |
| Virtual network | vnet | {Customer}-vnet-{App Name}-{Environment} |
   

| Asset type | Resource provider namespace/Entity |  Abbreviation |
| --- | --- | --- |
| API management service instance | Microsoft.ApiManagement/service | apim- | 
| Managed Identity | Microsoft.ManagedIdentity/userAssignedIdentities | id- |
| Management group | Microsoft.Management/managementGroups | mg- |
| Policy definition | Microsoft.Authorization/policyDefinitions | policy- |
| Resource group | Microsoft.Resources/resourceGroups | rg- |

#### Subscriptions ####
| Asset type | Scope | Format | Example |
| --- | --- | --- | --- |
| Subscription | Account/Enterprise Agreement | \<Business Unit>-\<Subscription type>-\<###> | mktg-prod-001 |

#### Resource Group ####
| Asset type | Scope | Format | Example |
| --- | --- | --- | --- |
| Resource Group | Subscription | rg-\<app  /  Service name>-\<Subscription type>-\<###> | rg sharepoint-prod-001 |


## Resources ##

#### Subscriptions ####
| Service | Resource Name | Environment | Scope | Format |
| --- | --- | --- | --- | --- |
| Subscriptions | corp-dev-001 | Development | Account/Enterprise Agreement | \<Business Unit>-\<Subscription Type>-\<###> |
| Subscriptions | corp-stage-001 | Staging | Account/Enterprise Agreement | \<Business Unit>-\<Subscription Type>-\<###> |
| Subscriptions | corp-prod-001 | Production | Account/Enterprise Agreement | \<Business Unit>-\<Subscription Type>-\<###> |
| Directory | deividsegle.com | Global | Account/Enterprise Agreement | Active Directory |

#### Resource Groups ####
| Service | Resource Name | Environment | Scope | Format |
| --- | --- | --- | --- | --- |
| Resource Group | rg-azdave-dev-001 | Development | Subscription | rg-\<App / Service Name>-\<Subscription Type>-\<###> |
| Resource Group | rg-azdave-stage-001 | Staging | Subscription | rg-\<App / Service Name>-\<Subscription Type>-\<###> |
| Resource Group | rg-azdave-prod-001 | Production | Subscription | rg-\<App / Service Name>-\<Subscription Type>-\<###> |

#### Virtual Networking #####
| Service | Resource Name | Environment | Scope | Format |
| --- | --- | --- | --- | --- |
| Virtual Network | vnet-dev-uksouth-001 | Dev | Resource Group | vnet-\<Subscription type>-\<Region>-\<###> |
| Subnet | snet-appgtw-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |
| Subnet | snet-webapp-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |
| Subnet | snet-apim-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |
| Subnet | snet-apiapp-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |
| Subnet | snet-storage-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |
| Subnet | snet-database-001 | Dev | Virtual Network | snet-\<Subscription type>-\<Sub-region>-\<###> |

| Service | Resource Name | Environment | Scope | Format |
| --- | --- | --- | --- | --- |
| NSG | nsg-appgtw-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| NSG | nsg-webapp-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| NSG | nsg-apim-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| NSG | nsg-apiapp-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| NSG | nsg-storage-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| NSG | nsg-database-allow-001 | Dev | Subnet or NIC | nsg-\<app name>-\<policy name>-\<###> |
| Public IP | pip-azdave-dev-ncus-001 | Dev | Resource Group | pip-\<Subscription type>-\<region>-\<###> |

#### Virtual Machine ####
| Service | Resource Name | Environment | Scope | Format |
| --- | --- | --- | --- | --- |
| Virtual Machine | vmisstestserver001 | Dev | Resource Group | vm-\<policy name or appname>-<###> |
| VM Storage Account | stvmstcoreuksouth001 | Dev | Global | stvm\<performance type>\<app name or prod name>\<region>\<###> |
| DNS Label | web1.ncus.cloudapp.azure.com | Dev | Global | \<A record of vm>.\[\<region>.cloudapp.azure.com] |
| Load Balancer | lb-sharepoint-dev-001 | Dev | Resource Group | lb-\<app name or role>-\<environment>-\<###> |
| NIC | nic-01-vm-prod-001 | Dev | Resource Group | nic-\<##>-\<vmname>-\<subscription>-\<###> |

## Components ##

#### Resource type prefixes ####
| Resource type                       | Resource name prefix |
|-------------------------------------|----------------------|
| Resource group                      | rg-                  |
| Virtual network                     | vnet-                |
| Virtual network gateway             | vnet-gw-             |
| Gateway connection                  | cn-                  |
| Subnet                              | snet-                |
| NSG                                 | nsg-                 |
| Virtual machines                    | vm-                  |
| VM storage account                  | stvm                 |
| Public IP                           | pip-                 |
| Load balancer                       | lb-                  |
| NIC                                 | nic-                 |
| Service Bus                         | sb-                  |
| Service Bus queues                  | sbq-                 |
| App services                        | azapp-               |
| Function apps                       | azfun-               |
| Cloud Services                      | azcs-                |
| Azure SQL Database                  | sqldb-               |
| Azure Cosmos DB (Document Database) | cosdb-               |
| Azure Cache for Redis               | redis-               |
| Azure Database for MySQL            | mysql-               |
| SQL Data Warehouse                  | sqldw-               |
| SQL Server Stretch Database         | sqlstrdb-            |
| Azure Storage                       | stor                 |
| StorSimple                          | ssimp                |
| Azure Search                        | srch-                |
| Cognitive Services                  | cs-                  |
| Azure Machine Learning workspace    | aml-                 |
| Azure Data Lake Storage             | dls                  |
| Azure Data Lake Analytics           | dla                  |
| HDInsight - Spark                   | hdis-                |
| HDInsight - Hadoop                  | hdihd-               |
| HDInsight - R server                | hdir-                |
| HDInsight - HBase                   | hdihb-               |
| Proximity Placement Group           | ppg-                 |
| Power BI Embedded                   | pbiemb               |
| Stream analytics                    | asa-                 |
| Data Factory                        | df-                  |
| Event Hub                           | evh-                 |
| Azure IoT Hub                       | aih-                 |
| Notification Hubs                   | anh-                 |
| Notification Hub Namespace          | anhns-               |

## Networking ##

#### Virtual Networking ####
| Asset type                                       | Resource provider namespace/Entity                        | Abbreviation |
|--------------------------------------------------|-----------------------------------------------------------|--------------|
| Application gateway                              | Microsoft.Network/applicationGateways                     | agw-         |
| Application security group (ASG)                 | Microsoft.Network/applicationSecurityGroups               | asg-         |
| Bastion                                          | Microsoft.Network/bastionHosts                            | bas-         |
| CDN profile                                      | Microsoft.Cdn/profiles                                    | cdnp-        |
| CDN endpoint                                     | Microsoft.Cdn/profiles/endpoints                          | cdne-        |
| Connections                                      | Microsoft.Network/connections                             | con-         |
| DNS                                              | Microsoft.Network/dnsZones                                | dnsz-        |
| DNS zone                                         | Microsoft.Network/privateDnsZones                         | pdnsz-       |
| Firewall                                         | Microsoft.Network/azureFirewalls                          | afw-         |
| Firewall policy                                  | Microsoft.Network/firewallPolicies                        | afwp-        |
| ExpressRoute circuit                             | Microsoft.Network/expressRouteCircuits                    | erc-         |
| Front Door instance                              | Microsoft.Network/frontDoors                              | fd-          |
| Front Door firewall policy                       | Microsoft.Network/frontdoorWebApplicationFirewallPolicies | fdfp-        |
| Load balancer (internal)                         | Microsoft.Network/loadBalancers                           | lbi-         |
| Load balancer (external)                         | Microsoft.Network/loadBalancers                           | lbe-         |
| Load balancer rule                               | Microsoft.Network/loadBalancers/inboundNatRules           | rule-        |
| Local network gateway                            | Microsoft.Network/localNetworkGateways                    | lgw-         |
| NAT gateway                                      | Microsoft.Network/natGateways                             | ng-          |
| Network interface (NIC)                          | Microsoft.Network/networkInterfaces                       | nic-         |
| Network security group (NSG)                     | Microsoft.Network/networkSecurityGroups                   | nsg-         |
| Network security group (NSG) security rules      | Microsoft.Network/networkSecurityGroups/securityRules     | nsgsr-       |
| Network Watcher                                  | Microsoft.Network/networkWatchers                         | nw-          |
| Private Link                                     | "Microsoft.Network/privateLinkServices                    | pl-          |
| Public IP address                                | Microsoft.Network/publicIPAddresses                       | pip-         |
| Public IP address prefix                         | Microsoft.Network/publicIPPrefixes                        | ippre-       |
| Route filter                                     | Microsoft.Network/routeFilters                            | rf-          |
| Route table                                      | Microsoft.Network/routeTables                             | rt-          |
| Service endpoint                                 | Microsoft.serviceEndPointPolicies                         | se-          |
| Traffic Manager profile                          | Microsoft.Network/trafficManagerProfiles                  | traf-        |
| User defined route (UDR)                         | Microsoft.Network/routeTables/routes                      | udr-         |
| Virtual network                                  | Microsoft.Network/virtualNetworks                         | vnet-        |
| Virtual network peering                          | Microsoft.Network/virtualNetworks/virtualNetworkPeerings  | peer-        |
| Virtual network subnet                           | Microsoft.Network/virtualNetworks/subnets                 | snet-        |
| Virtual WAN                                      | Microsoft.Network/virtualWans                             | vwan-        |
| VPN Gateway                                      | Microsoft.Network/vpnGateways                             | vpng-        |
| VPN connection                                   | Microsoft.Network/vpnGateways/vpnConnections              | vcn-         |
| VPN site                                         | Microsoft.Network/vpnGateways/vpnSites                    | vst-         |
| Virtual network gateway                          | Microsoft.Network/virtualNetworkGateways                  | vgw-         |
| Web Application Firewall (WAF) policy            | Microsoft.Network/firewallPolicies                        | waf          |
| Web Application Firewall (WAF) policy rule group | Microsoft.Network/firewallPolicies/ruleGroups             | wafrg        |
| Network Virtual Appliance                        |                                                           | nva-         |

| Asset type               | Scope           | Format                                                     | Example                                               |
|--------------------------|-----------------|------------------------------------------------------------|-------------------------------------------------------|
| Virtual Network          | Resource group  | vnet-\<Subscription type>-\<Region>-\<###>                    | vnet-shared-eastus2-001                               |
| Vnet virtual gateway     | Virtual network | vnet-gw-v-\<Subscription type>-\<Region>-\<###>               | vnet-gw-v-shared-eastus2-001                          |
| Vnet local gateway       | Virtual gateway | vnet-gw-l-\<Subscription type>-\<Region>-\<###>               | vnet-gw-l-shared-eastus2-001                          |
| Site to site connections | Resource group  | cn-\<local gateway name>-to-\<virtual gateway name>          | cn-l-gw-shared-eastus2-001-to-v-gw-shared-eastus2-001 |
| VNet Connections         | Resource group  | cn-\<subscription1>\<region1>-to-\<subscription2>\<region2>    | cn-shared-eastus2-to-shared-westus                    |
| Subnet                   | Virtual network | snet-\<subscription>-\<sub-region>-\<###>                     | snet-shared-eastus2-001                               |
| NSG                      | Subnet or NIC   | nsg-\<policy name or appname>-\<###>                         | nsg-weballow-001                                      |
| Public IP                | Resource group  | pip-\<vm name or app name>-\<Environment>-\<sub-region>-\<###> | pip-dc1-shared-eastus2-001                            |

## Compute & Web ##

#### Virtual Machines ####
| Asset type                           | Resource provider namespace/entity                     | Abbreviation |
|--------------------------------------|--------------------------------------------------------|--------------|
| App Service environment              | Microsoft.Web/sites                                    | ase-         |
| App Service plan                     | Microsoft.Web/serverFarms                              | plan-        |
| Availability set                     | Microsoft.Compute/availabilitySets                     | avail-       |
| Azure Arc enabled server             | Microsoft.HybridCompute/machines                       | arcs-        |
| Azure Arc enabled Kubernetes cluster | Microsoft.Kubernetes/connectedClusters                 | arck         |
| Cloud service                        | Microsoft.Compute/cloudServices                        | cld-         |
| Disk encryption set                  | Microsoft.Compute/diskEncryptionSets                   | des          |
| Function app                         | Microsoft.Web/sites                                    | func-        |
| Gallery                              | Microsoft.Compute/galleries                            | gal          |
| Managed disk (OS)                    | Microsoft.Compute/disks                                | osdisk       |
| Managed disk (data)                  | Microsoft.Compute/disks                                | disk         |
| Notification Hubs                    | Microsoft.NotificationHubs/namespaces/notificationHubs | ntf-         |
| Notification Hubs namespace          | Microsoft.NotificationHubs/namespaces                  | ntfns-       |
| Snapshot                             | Microsoft.Compute/snapshots                            | snap-        |
| Static web app                       | Microsoft.Web/staticSites                              | stapp-       |
| Virtual machine                      | Microsoft.Compute/virtualMachines                      | vm           |
| Virtual machine scale set            | Microsoft.Compute/virtualMachineScaleSets              | vmss-        |
| VM storage account                   | Microsoft.Storage/storageAccounts                      | stvm         |
| Web app                              | Microsoft.Web/sites                                    | app-         |

| Asset type         | Scope          | Format                                                   | Example                         |
|--------------------|----------------|----------------------------------------------------------|---------------------------------|
| Virtual Machine    | Resource group | vm\<policy name or appname>\<###>                          | vmsharepoint001                 |
| VM Storage account | Global         | stvm\<performance type>\<appname or prodname>\<region>\<###> | stvmstcoreeastus2001            |
| DNS Label          | Global         | \<A record of vm>.[\<region>.cloudapp.azure.com]           | web1.eastus2.cloudapp.azure.com |
| Load Balancer      | Resource group | lb-\<app name or role>\<Environment>\<###>                  | lb-sharepoint-dev-001           |
| NIC                | Resource group | nic-\<##>-\<vmname>-\<subscription>\<###>                    | nic-02-vmhadoop1-prod-001       |

## Containers ##

| Asset type             | Resource provider namespace/entity          | Abbreviation |
|------------------------|---------------------------------------------|--------------|
| AKS cluster            | Microsoft.ContainerService/managedClusters  | aks-         |
| Container registry     | Microsoft.ContainerRegistry/registries      | cr           |
| Container instance     | Microsoft.ContainerInstance/containerGroups | aci\ci       |
| Service Fabric cluster | Microsoft.ServiceFabric/clusters            | sf-          |

## DB & Storage ##

#### Storage ####
| Asset type                                 | Resource provider namespace/Entity                 | Abbreviation |
|--------------------------------------------|----------------------------------------------------|--------------|
| Azure Cosmos DB database                   | Microsoft.DocumentDB/databaseAccounts/sqlDatabases | cosmos-      |
| Azure Cache for Redis instance             | Microsoft.Cache/Redis                              | redis-       |
| Azure SQL Database server                  | Microsoft.Sql/servers                              | sql-         |
| Azure SQL database                         | Microsoft.Sql/servers/databases                    | sqldb-       |
| Azure Synapse Analytics                    | Microsoft.Synapse/workspaces                       | syn          |
| Azure Synapse Analytics Workspaces         | Microsoft.Synapse/workspaces                       | synw         |
| Azure Synapse Analytics SQL Dedicated Pool | Microsoft.Synapse/workspaces/sqlPools              | syndp        |
| Azure Synapse Analytics Spark Pool         | Microsoft.Synapse/workspaces/sqlPools              | synsp        |
| MySQL database                             | Microsoft.DBforMySQL/servers                       | mysql-       |
| PostgreSQL database                        | Microsoft.DBforPostgreSQL/servers                  | psql-        |
| SQL Server Stretch Database                | Microsoft.Sql/servers/databases                    | sqlstrdb-    |
| SQL Managed Instance                       | Microsoft.Sql/managedInstances                     | sqlmi-       |

| Asset type                              | Scope  | Format                                                               | Example               |
|-----------------------------------------|--------|----------------------------------------------------------------------|-----------------------|
| Azure Storage account - general use     | Global | st\<storage name>\<###>                                                | stnavigatordata001    |
| Azure Storage account - diagnostic logs | Global | stdiag\<first 2 letters of subscription name and number>\<region>\<###> | stdiagsh001eastus2001 |
| StorSimple                              | Global | ssimp\<App Name>\<Environment>                                         | ssimpnavigatorprod    |

#### Databse ####
| Asset type       | Resource provider namespace/Entity | Abbreviation |
|------------------|------------------------------------|--------------|
| Storage account  | Microsoft.Storage/storageAccounts  | st           |
| Azure StorSimple | Microsoft.StorSimple/managers      | ssimp        |

| Asset type                          | Scope              | Format                            | Example                 |
|-------------------------------------|--------------------|-----------------------------------|-------------------------|
| Azure SQL Database                  | Global             | sqldb-\<App Name>-\<Environment>    | sqldb-navigator-prod    |
| Azure Cosmos DB (Document Database) | Global             | cosdb-\<App Name>-\<Environment>    | cosdb-navigator-prod    |
| Azure Cache for Redis               | Global             | redis-\<App Name>-\<Environment>    | redis-navigator-prod    |
| Azure Database for MySQL            | Global             | mysql-\<App Name>-\<Environment>    | mysql-navigator-prod    |
| SQL Data Warehouse                  | Global             | sqldw-\<App Name>-\<Environment>    | sqldw-navigator-prod    |
| SQL Server Stretch Database         | Azure SQL Database | sqlstrdb-\<App Name>-\<Environment> | sqlstrdb-navigator-prod |

## Log & Analytics ##

#### Analytics ####
| Asset type                | Scope  | Format                         | Example              |
|---------------------------|--------|--------------------------------|----------------------|
| Azure Data Factory        | Global | df-\<App Name>\<Environment>     | df-navigator-prod    |
| Azure Data Lake Storage   | Global | dls\<App Name>\<Environment>     | dlsnavigatorprod     |
| Azure Data Lake Analytics | Global | dla\<App Name>\<Environment>     | dlanavigatorprod     |
| HDInsight - Spark         | Global | hdis-\<App Name>-\<Environment>  | hdis-navigator-prod  |
| HDInsight - Hadoop        | Global | hdihd-\<App Name>-\<Environment> | hdihd-hadoop-prod    |
| HDInsight - R server      | Global | hdir-\<App Name>-\<Environment>  | hdir-navigator-prod  |
| HDInsight - HBase         | Global | hdihb-\<App Name>-\<Environment> | hdihb-navigator-prod |
| Power BI Embedded         | Global | pbiemb\<App Name>\<Environment>  | pbiem-navigator-prod |

## Tagging Conventions ##

| Tag Name                  | Description                                                                                                                                                                                                    | Key             | Example Value                                 | Required? |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|-----------------------------------------------|-----------|
| Application Name          | Name of the application, service, or workload the resource is associated with.                                                                                                                                 | ApplicationName | {app name}                                    | Yes       |
| Approver Name             | Person responsible for approving costs related to this resource.                                                                                                                                               | Approver        | {email}                                       | Yes       |
| Budget required/approved  | Money allocated for this application, service or workload.                                                                                                                                                     | BudgetAmount    | {$}                                           | No        |
| Business Unit             | Top-level division of your company that owns the subscription or workload the resource belongs to. In smaller organizations, this may represent a single corporate or shared top-level organizational element. | BusinessUnit    | FINANCE, MARKETING,{Product Name},CORP,SHARED | Yes       |
| Cost Center               | Accounting cost center associated with this resource.                                                                                                                                                          | CostCenter      | {number}                                      | Yes       |
| Disaster Recovery         | Business criticality of this application, workload, or service.                                                                                                                                                | DR              | Mission Critical, Critical, Essential         | Yes       |
| End Date of the Project   | Date when this application, workload, or service is planned to be retired.                                                                                                                                     | EndDate         | {date}                                        | No        |
| Environment               | Deployment environment of this application, workload, or service.                                                                                                                                              | Env             | Prod, Dev, QA, Stage, Test                    | Yes       |
| Owner Name                | Owner of the application, workload, or service.                                                                                                                                                                | Owner           | {email}                                       | Yes       |
| Requester Name            | User that requested the creation of this application.                                                                                                                                                          | Requestor       | {email}                                       | No        |
| Service Class             | Service Level Agreement level of this application, workload, or service.                                                                                                                                       | ServiceClass    | Dev, Bronze, Silver, Gold                     | Yes       |
| Start Date of the project | Date when this application, workload, or service was first deployed.                                                                                                                                           | StartDate       | {date}                                        | No        |
| Exam                      | In preparation for which exam the resource is being used                                                                                                                                                       | ExamNumber      | {###}                                         | Yes       |