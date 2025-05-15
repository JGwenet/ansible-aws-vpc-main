# ansible-aws-vpc

## Overview

This repository contains an Ansible playbook for creating and managing an AWS VPC. It simplifies the process of provisioning VPC resources such as subnets, route tables, and internet gateways.

## Features

- Create a fully customizable AWS VPC.
- Support for public and private subnets.
- Automated configuration of route tables and gateways.
- Easy integration with other AWS services.

## Prerequisites

- An AWS account with appropriate permissions.
- Ansible installed on your local machine.
- AWS CLI configured with your credentials.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/your-repo/ansible-aws-vpc.git
    cd ansible-aws-vpc
    ```

2. Run the playbook:
    ```bash
    ansible-playbook vpc-setup.yml
    ```
    ## Bastion Host

    A bastion host is included in the playbook to provide secure access to instances within the private subnets. The bastion host is deployed in the public subnet and can be accessed via SSH.

    ### Configuration

    - Ensure your SSH key pair is specified in the playbook variables.
    - Update the security group rules to allow access to the bastion host from your IP address.

    ### Usage

    1. Connect to the bastion host (assumes the baston host is an aws machine):
        ```bash
        ssh -i /path/to/your-key.pem ec2-user@<bastion-host-public-ip>
        ```

    2. From the bastion host, you can SSH into instances in the private subnet.