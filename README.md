# **Launch an EC2 instance on AWS CLI**
A prerequisite for launching an EC2 Instance is having the **AWS CLI** installed in your computer.

## **Installing AWS-CLI**
Run the *"apt update"* command to update i.e if AWS-CLI is already installed, and *"apt install awscli -y"* command to install

## **Configure AWS CLI using IAM Credentials**
input “`aws --version*” to confirm version installed, and “*aws configure`” to configure AWS CLI

![Alt text](img/Screenshots/AWS_config.png)

## **Create key pair**
input *`aws ec2 create-key-pair --key-name (keypair-Name) --query 'KeyMaterial' –output text > (keypair-Name.pem)`* command

![Alt text](<img/Screenshots/key-pair created.png>)

## **Create Security group**
input *`aws ec2 create-security-group --group-name (security grp Name) --description (Description)`*

![Alt text](img/Screenshots/sg-created.png)

## **Launch instance**
**Add inbound rule:** input *`aws ec2 authorize-security-group-ingress --group-id (security group Id) --protocol tcp --port (port Number) --cidr (ip address)`* command

![Alt text](<img/Screenshots/added-rule to sg.png>)

**Launch instance:** *`aws ec2 run-instances --image-id (ami-Id) --count 1 --instance-type (type) --keyname (keypair-Name) --security-groups (security grp Name)`* command

![Alt text](img/Screenshots/launch-ec2.png)

![Alt text](img/Screenshots/ec2-launch-console.png)you can confirm the instance launch on your AWS Console 

## Congratulations, you have Successfully Launched and Terminated an EC2 Instance using the AWS-CLI

[Read More](https://github.com/Bufic/EC2_Launch.git)