In this mini lab/lesson we are going to provision an EC2 using Hashicorps's terraform.

Reference: https://www.terraform.io/docs/providers/aws/index.html

<h1>What is Terraform?</h1>
Terraform is a tool made by Hashicorp for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers ( aws, azure, Google cloud) as well as custom in-house solutions.

You can compare Terraform to Cloudformation . They are simililar but at the same time have differences.

<h2>Steps to provision </h2>
Download the terraform binary file https://www.terraform.io/downloads.html
If MAC users have homebrew installed on their machine: Just do: brew install terraform Go to step 5

1.Extract the zip file
You will see the terraform binary executable file
make sure that the terraform binary is available on the PATH.
For Mac/Linux. On the shell/terminal, go to the folder where terraform binary is extracted

echo $"export PATH=\$PATH:$(pwd)" >> ~/.bash_profile
source ~/.bash_profile

For Windows users : follow this to add Terraform to PATH https://stackoverflow.com/questions/1618280/where-can-i-set-path-to-make-exe-on-windows

make a new directory(can be named anything) and go inside the directory
mkdir terraform-july && cd terraform-july
Paste this following code to a file called ec2.tf( can be anything.tf)
minimal viable configuration
provider "aws" {
  access_key = "ACCESS_KEY_HERE"
  secret_key = "SECRET_KEY_HERE"
  region     = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-2757f631"
  instance_type = "t2.micro"
}
