# Cloud Testing VM

This is the necessary scripts to build and run a Ubuntu virtual machine that has a number of common cloud assessment tools pre-installed. It uses a combination of Vagrant and Ansible to deploy the VM and configure it if running locally. You can also build a version as an AWS AMI.

## Tools

These should all be present in the path by default.

| Tool               | Description                                                 | URL                                                |
| ------------------ | ----------------------------------------------------------- | -------------------------------------------------- |
| `aws`              | AWS CLI                                                     |                                                    |
| `az`               | Azure CLI                                                   |                                                    |
| `gcloud`           | Google Cloud Platform CLI                                   |                                                    |
| `kubectl`          | CLI for interacting with Kubernetes clusters                |                                                    |
| `amicontained`     | Container introspection and runtime enumeration             | <https://github.com/genuinetools/amicontained>     |
| `auger`            | Tool for accessing objects stored in etcd directly          | <https://github.com/jpbetz/auger>                  |
| `aws-vault`        | Secure storage of AWS credentials                           | <https://github.com/99designs/aws-vault>           |
| `azurehound`       | Azure collector for Bloodhound CE                           | <https://github.com/BloodHoundAD/AzureHound>       |
| `bloodhound`       | Entra ID, Azure and Active Directory permission mapping\*   | <https://github.com/SpecterOps/BloodHound/>        |
| `cartography`      | Resource relationship mapper                                | <https://github.com/lyft/cartography>              |
| `checkov`          | Terraform static analysis and security auditing             | <https://github.com/bridgecrewio/checkov>          |
| `cloudfox`         | AWS Exploitation toolkit                                    | <https://github.com/BishopFox/cloudfox>            |
| `cloudsplaining`   | Identify risks in IAM policies                              | <https://github.com/salesforce/cloudsplaining>     |
| `detect-secrets`   | Scan for secrets in code repositories (docker image)        | <https://github.com/Yelp/detect-secrets>           |
| `enumerate-iam`    | Find permissions for a given set of AWS IAM credentials     | <https://github.com/skybound1/enumerate-iam>       |
| `etcdctl`          | CLI client for etcd                                         | <https://github.com/etcd-io/etcd/>                 |
| `freezer`          | Download tool for IceKube                                   | <https://github.com/withsecurelabs/freezer>        |
| `iamgraph`         | Graph out role assumption through an AWS organization       | <https://github.com/withsecurelabs/iamgraph>       |
| `iamspy`           | IAM policy evaluator using formal methods                   | <https://github.com/withsecurelabs/iamspy>         |
| `icekube`          | Kubernetes attack path graph generation                     | <https://github.com/withsecurelabs/icekube>        |
| `jq`               | JSON parser and processor                                   | <https://github.com/jqlang/jq>                     |
| `kics`             | Infrastructure as code vulnerability scanner (docker image) | <https://github.com/Checkmarx/kics>                |
| `kubectl-who-can`  | Query and enumerate permissions in a Kubernetes cluster     | <https://github.com/aquasecurity/kubectl-who-can/> |
| `kubehound`        | Kubernetes identity and permission graphing                 | <https://github.com/DataDog/KubeHound>             |
| `pacu`             | AWS exploitation framework                                  | <https://github.com/RhinoSecurityLabs/pacu>        |
| `pmapper`          | AWS IAM evaluator                                           | <https://github.com/nccgroup/PMapper>              |
| `prowler`          | AWS security auditing tooling                               | <https://github.com/toniblyx/prowler>              |
| `roadtools`        | Entra ID reconnaissance framework                           | <https://github.com/dirkjanm/ROADtools>            |
| `rbac-lookup`      | Tool for looking up Kubernetes roles and cluster roles      | <https://github.com/FairwindsOps/rbac-lookup>      |
| `scoutsuite`       | Multi-cloud audit tool                                      | <https://github.com/nccgroup/ScoutSuite>           |
| `stratus-red-team` | Multi-cloud TTP simulation tool                             | <https://github.com/DataDog/stratus-red-team/>     |
| `terrascan`        | Terraform code scanning tool (docker image)                 | <https://github.com/tenable/terrascan>             |
| `tfsec`            | Terraform code scanning tool (docker image)                 | <https://github.com/aquasecurity/tfsec>            |
| `trivy`            | Container CVE & security issue scanner (docker container)   | <https://github.com/aquasecurity/trivy>            |
| `yq`               | YAML parser and processor                                   | <https://github.com/mikefarah/yq>                  |

\*Bloodhound is the Bloodhound CE version, included as a `docker-compose` file in `~/bloodhound/`. Follow instructions in their repo to use it.

## Local Use

### Prerequisites

- Vagrant [https://www.vagrantup.com/](https://www.vagrantup.com/)
- Virtualbox
- The vagrant-vbguest Vagrant plugin (once vagrant is installed, run `vagrant plugin install vagrant-vbguest`)

### Setup

- Run `vagrant up` to build the VM
- Run `vagrant ssh` to get a terminal inside the VM
- Tools are on the path.

## AWS AMI Building

- `packer init aws-ubuntu.pkr.hcl`
- `packer build aws-ubuntu.pkr.hcl` while configured with the right AWS profile

## TO DO

- Update docs to detail how to build AMIs
- Update packer to build local VMs for virtualbox and VMWare
- Update packer to create vagrant boxes for virtualbox and vmware

### Tools to add

- <https://github.com/hotnops/apeman>
- Powershell
- <https://github.com/BloodHoundAD/BARK>
- <https://github.com/DataDog/guarddog>
- <https://github.com/turbot/steampipe>
- All the project discovery stuff
