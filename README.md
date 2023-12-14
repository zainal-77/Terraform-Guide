# Terraform Guide: Creating an AWS Instance

## Objective
This guide aims to walk you through the process of using Terraform to create an instance on Amazon Web Services (AWS).

### Prerequisites
Before you start, make sure you have:
1. An AWS account with access to the AWS Management Console.
2. Access Key and Secret Key generated in AWS.

## Implementation Steps

### Step 1: Install Terraform
1. Download and install Terraform from the [official Terraform website](https://www.terraform.io/downloads.html).
2. Ensure Terraform is accessible via the terminal or command prompt.

### Step 2: AWS Configuration
1. Create a directory for your Terraform project.
2. Inside the directory, create a file named `main.tf`.

### Step 3: Define AWS Provider
1. Populate `main.tf` with the following code to specify the AWS provider and the chosen region:
    ```hcl
    provider "aws" {
      region = "us-west-2" # Replace with your desired region
    }
    ```

### Step 4: Specify EC2 Resource
1. Add the following code to `main.tf` to define an AWS EC2 instance:
    ```hcl
    resource "aws_instance" "example" {
      ami           = "ami-0c55b159cbfafe1f0" # Replace with your desired AMI
      instance_type = "t2.micro"
      tags = {
        Name = "ExampleInstance"
      }
    }
    ```

### Step 5: Initialize and Apply
1. Open the terminal or command prompt, navigate to the Terraform project directory.
2. Run `terraform init` to initialize the project.
3. Use `terraform plan` to view the execution plan and ensure there are no errors.
4. Execute `terraform apply` and confirm the changes by typing `yes`.

### Step 6: Verify EC2 Instance
1. After the `apply` command completes, log in to the AWS Management Console.
2. Navigate to the EC2 service dashboard to verify the creation of the "ExampleInstance" EC2 instance.

### Step 7: Optional - Destroy Resources
1. Once finished, execute `terraform destroy` to remove the created EC2 instance.

Ensure to replace placeholders like `ami-0c55b159cbfafe1f0` with the actual AMI ID and adjust other settings as per your AWS environment.
