A check list of things to go over prior to starting work on new piece of infrastructure. You should document which items you have implemented, which ones you've decided to skip, and explain reasons why.

Production-Grade Infrastructure Checklist
| Task | Description | Example tools |
| -- | ---------- | --- |
| Install | Install the software binaries and all dependencies. | Bash, Ansible, Docker, Packer |
| Configure|  Configure the software at runtime. Includes port settings, TLS certs, service discovery, leaders, followers, replication, etc. | Chef, Ansible, Kubernetes |
| Provision | Provision the infrastructure. Includes servers, load balancers, network configuration, firewall settings, IAM permissions, etc. | Terraform, CloudFormation |
| Deploy | Deploy the service on top of the infrastructure. Roll out updates with no downtime. Includes blue-green, rolling, and canary deployments. | ASG, Kubernetes, ECS |
| High availability |Withstand outages of individual processes, servers, services, datacenters, and regions. | Multidatacenter, multi-region |
| Scalability | Scale up and down in response to load. Scale horizontally and/or verticaly. | Auto scaling, replication |
| Performance | Optimize CPU, memory, disk, network, and GPU usage. Includes query tuning, benchmarking, load testing, and profiling. | Dynatrace, Valgrid, VisualVM |
| Networking | Configure static and dynamic IP's, ports, service discovery, firewalls, DNS, SSH, access, and VPN access. | VPC's, firewalls, Route 53 |
| Security | Ecryption in transit (TLS) and on disk, authentication, athorization, secretes management, serrver hardening. | ACM< Let's encrypt, KMS, Vault |
| Metrics | Availability metrics, business metrics, app metrics, server metrics, events, observability, tracing, and alerting. | CloudWatch, Datadog |
| Logs | Rotate logs on disk. Aggregate log data to a central location. | Elastic Stack, Suomo Logic |
| Data backups | Make backups of DB's, caches, and other data on a scheduled basis, Replicate to separate region/account. | AWS Backup, RDS snapshots |
| Cost optimization | Pick adequate instance types, use spot, and reserved Instances, use auto scaling, and cleanup unused resources. | Auto scaling, Infracost |
| Documentation | Document your code, architecture, and practices. Create playbooks to respond to incidents. | READMEs, wikies, Slack, IaC |
| Tests | Write automated tests for your infrastructure code. Run tests after every commit and nightly. | Terratest, tflint, OPA, InSpec |
