# Terraform VPC Setup

This Terraform configuration sets up a Virtual Private Cloud (VPC) in AWS, including public and private subnets, an Internet Gateway (IGW), and a NAT Gateway for routing traffic. The configuration uses variables for flexibility, making it reusable for different environments.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed (v1.0+ recommended)
- AWS credentials set up in your environment (using AWS CLI or environment variables)
- A working AWS account with the necessary permissions (VPC, Subnet, NAT Gateway, Internet Gateway, Route Tables)

## Resources Deployed

1. **VPC**: A virtual private cloud is created using a user-defined CIDR block.
2. **Subnets**:
   - Private subnets (mapped to specific availability zones)
   - Public subnets (mapped to specific availability zones)
3. **Internet Gateway (IGW)**: Provides internet access to the public subnets.
4. **NAT Gateway**: Enables internet access for private subnets through public subnets.
5. **Route Tables**:
   - Public route table with a route to the Internet Gateway
   - Private route table with a route to the NAT Gateway
6. **Elastic IP (EIP)**: Used for the NAT Gateway to allocate a public IP.
7. **Subnet Variables**: Creates subnets using flexible variables for availability zone, CIDR block, and IP mapping.

## How to Use

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd <repository-directory>

variable "vpc_cidr" {
  description = "CIDR block for the VPC"
}

variable "vpc_name" {
  description = "Name for the VPC"
}

variable "private_subnets" {
  description = "Mapping of availability zones for private subnets"
}

variable "public_subnets" {
  description = "Mapping of availability zones for public subnets"
}

variable "variables_sub_cidr" {
  description = "CIDR block for the additional subnet created by variables"
}

variable "variables_sub_az" {
  description = "Availability zone for the additional subnet"
}

variable "variables_sub_auto_ip" {
  description = "Boolean to map public IP on launch"
}

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

terraform init

terraform plan


terraform apply

