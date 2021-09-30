## [Checkov](https://github.com/bridgecrewio/checkov)
- Its an opensource tools for scanning below IAC Frameworks :
  - AWS - Cloudformation
  - Azure - ARM
  - GCP - 
  - Kubernetes
  - Dockerfile
  - Helm
  - Terraform


### About Checkov :
- Scan's above listed IAC Frameworks.
- Custom policy can also been created as per your organization
- Can be integrated with CI/CD

### Other similar tools :
- [OWASP Defectdojo](https://owasp.org/www-project-defectdojo/)
- [Bridgecrew](https://bridgecrew.io/infrastructure-as-code-security/)
#### For K8s,Terraform
- [checkov](https://github.com/bridgecrewio/checkov)
- [cfngoat](https://github.com/bridgecrewio/cfngoat)
- [terragoat](https://github.com/bridgecrewio/terragoat)
#### AWS:
- toniblyx/prowler
- duo-labs/cloudmapper
- bridgecrewio/airiam
#### Google cloud
- gcp/terraform-pci-starter


### Whats new in CKV2: 
- Integrated with GraphDB
- Can be written in YAML
- EC2 is been exposed are not will be check using Graphdb to check other resources like Security group, BGP, VPC, ELB, Subnet etc to see if it is been exposed. 
- It also check 7 different Dockerfile check:
  - Ensure COPY is userd insted of ADD
  - Ensure HEALTHCHECK insruction have been used.
  - Ensure update instructions are not used in Dockerfile
  - Ensure User for the container has been created.
  - Ensure port 22 is not exposed

### Checkov Cheatsheet :
- `checkov -l` - List all the supported checks it will do
- `checkov -h` - HELP
- `checkov -l|grep CKV` - Written in Python
- `checkov -l|grep CKV2` - Written in YAML/ backend GraphDB

