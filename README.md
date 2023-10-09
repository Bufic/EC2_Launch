# **Launch an EC2 instance on AWS CLI**
A prerequisite for launching an EC2 Instance is having the **AWS CLI** installed in your computer.

## **Installing AWS-CLI**
Run the *"apt update"* command to update i.e if AWS-CLI is already installed, and *"apt install awscli -y"* command to install

## **Configure AWS CLI using IAM Credentials**
input “`aws --version*” to confirm version installed, and “*aws configure`” to configure AWS CLI
![AWS_config](https://github.com/Bufic/EC2_Launch/assets/146486260/139bf496-5e31-4027-9e37-8ad368bfcb3d)


## **Create key pair**
input *`aws ec2 create-key-pair --key-name (keypair-Name) --query 'KeyMaterial' –output text > (keypair-Name.pem)`* command
![key-pair created](https://github.com/Bufic/EC2_Launch/assets/146486260/271a09a5-4360-43cb-97b5-0b9bad209c89)


## **Create Security group**
input *`aws ec2 create-security-group --group-name (security grp Name) --description (Description)`*
![sg-created](https://github.com/Bufic/EC2_Launch/assets/146486260/519a9383-86f0-40df-8847-1e45823ca010)

![sg-console](https://github.com/Bufic/EC2_Launch/assets/146486260/9c5fc7bd-a6df-40c9-af0f-ff8b322d784c)


## **Launch instance**
**Add inbound rule:** input *`aws ec2 authorize-security-group-ingress --group-id (security group Id) --protocol tcp --port (port Number) --cidr (ip address)`* command

![added-rule to sg](https://github.com/Bufic/EC2_Launch/assets/146486260/26d307c9-b376-4b50-a58f-ebf1da76925f)


**Launch instance:** *`aws ec2 run-instances --image-id (ami-Id) --count 1 --instance-type (type) --keyname (keypair-Name) --security-groups (security grp Name)`* command

![launch-ec2](https://github.com/Bufic/EC2_Launch/assets/146486260/b24446b3-2454-478e-bcb0-a2ee89fe1c9e)


![ec2-launch-console](https://github.com/Bufic/EC2_Launch/assets/146486260/45c0a040-fc43-4571-98d1-d099bb9e332d) you can confirm the instance launch on your AWS Console 

## Congratulations, you have Successfully Launched and Terminated an EC2 Instance using the AWS-CLI

[Read More](https://github.com/Bufic/EC2_Launch.git)
