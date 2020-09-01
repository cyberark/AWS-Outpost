# CyberArk AWS Outpost Network CloudFormation Template

## Overview

The Network-Outpost-PAS-NAT CyberArk CloudFormation template automates the deployment of the network architecture in order for CyberArk CorePAS instances to be installed into an AWS Outpost.  This template uses CloudFormation Lambda Layer functionality to install subnets exclusively in an Availability Zone available to Outpost and set the Outpost server using an Outpost ARN.

This integration ensures that the [CyberArk pas-on-cloud](https://github.com/cyberark/pas-on-cloud/tree/master/aws) CFN templates will install the Core PAS instances 

## Requirements

- [ ] Network-Outpost-PAS-NAT.yaml
- [ ] Lambda Layer zip file stored in an S3 Bucket
- [ ] Name of the Python Lambda Layer (op_subnet.py)
- [ ] Availability Zone of Outpost
- [ ] Outpost ARN
- [ ] User Access CIDR
- [ ] Admin Access CIDR
- [ ] Desired Private CIDR blocks for PAS Communication (12)
- [ ] Desired NAT Gateway CIDR Block 
</br>

| Requirements | Description |
|------------------------------|-------------|
| Network-Outpost-PAS-NAT.yml | This is the CloudFormation template housed in this repository to deploy the network |
| Lambda Layer Bucket | Name of the S3 Bucket that will house the Lambda Layer file |
| Lambda Layer Zip File | Key of the S3 object that has the Lambda Layer. Full file path in the Bucket to the zip file **NOTE: DO NOT unzip or modify file path within the zip** Example: group/outpost/python-layer.zip |
| Lambda Layer File Name | The name of the Lambda Layer file, by default it is **op_subnet.py** |
| Outpost Availability Zone | The Availability Zone that the Outpost resides in |
| Outpost ARN | The ARN of the Outpost that CyberArk will be installed in |
| User Access CIDR | CIDR block for user based access to the PVWA, PSM, and PSMSSH |
| Admin Access CIDR | CIDR block for admin based access to ALL Component servers |
| Private PAS VPC CIDR | CIDR block for all PAS communication |
| Desired NAT Gateway CIDR | CIDR block for public access Gateway, this is connected to the Region and not the Availability Zone |

## Deployment Steps
1. Download the **Network-Outpost-PAS-NAT.yaml** and the **python-layer.zip** from this repository.
2. Store the **python-layer.zip** in an S3 Bucket as-is.
3. Navigate to CloudFormation in the AWS Console.
4. Select *Create Stack*.
5. Upload the **Network-Outpost-PAS-NAT.yaml**.
6. Fill out the template with the information from the **Requirements** section and run the template.
7. Once the template completes access your Subnets and ensure that the Outpost ARN is listed in the **Outpost ID** parameter in the Subnet description page.
8. Use the [CyberArk pas-on-cloud](https://github.com/cyberark/pas-on-cloud/tree/master/aws) CFN templates to deploy your CyberArk CorePAS instances.

[CyberArk GitHub page](https://github.com/cyberark/)

## Contributing
We welcome contributions of all kinds to this repository. For instructions on how to get started and descriptions
of our development workflows, please see our [contributing guide](CONTRIBUTING.md).

## License
This repository is licensed under Apache License 2.0 - see [`LICENSE`](LICENSE) for more details.
