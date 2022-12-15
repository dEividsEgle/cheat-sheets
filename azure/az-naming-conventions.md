  

### General ###

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


