# AWS CloudFormation Templates

This repository contains AWS CloudFormation templates for deploying a multi-tiered application on Amazon Web Services (AWS). This project is not fully completed.

### Table of Contents

 - [VPC](#vpc)
 - [Security Groups](#security-groups)
 - [Key Pair](#key-pair)
 - [ECS Cluster](#ecs-cluster)
 - [EFS](#efs)
 - [EC2 Instance](#ec2-instance)
 - [ECS Task Definition](#ecs-task-definition)
 - [ECS Service](#ecs-service)
 - [How To Upload Templates](#how-to-upload-templates)

## VPC

This template creates a VPC with public subnets spread across two Availability Zones. It includes an Internet Gateway to enable outbound internet access from resources in the VPC.

Outputs

    VPC: A reference to the created VPC.
    PublicSubnets: A list of the public subnets.
    PublicSubnet1: A reference to the public subnet in the 1st Availability Zone.
    PublicSubnet2: A reference to the public subnet in the 2nd Availability Zone.

## Security Groups

This template creates three security groups for EC2 instances, EFS, and ALB.

Outputs

    EC2SecurityGroup: A reference to the created EC2 Security Group.
    EFSSecurityGroup: A reference to the created EFS Security Group.
    ALBSecurityGroup: A reference to the created ALB Security Group.

## Key Pair

This template creates an EC2 Key Pair for enabling SSH access to EC2 instance.

Outputs

    KeyPair: A reference to the created key pair.

## ECS Cluster

This template created an Amazon ECS cluster with Auto Scaling. It includes an IAM role for EC2 instances, ECS task role, and necessary resources for autoscaling.

Outputs

    ClusterName: A reference to ECS cluster.
    ECSRole: A reference to ECS role.

## EFS

This template creates an Amazon EFS with security groups and mount targets in two Availability Zones.

Outputs

    ElasticFileSystem: A reference to the created Elastic File System.
    EFSMountTargetAZ1Id: A reference to EFS mount target Id in Availability Zone 1.
    EFSMountTargetAZ2Id: A reference to EFS mount target Id in Availability Zone 2.

## EC2 Instance

This template provisions an EC2 instance in the public subnet, installing NFS utilities, and creating a simple HTML page on an EFS volume.

Outputs

    InstanceId: A reference to the created EC2 instance.
    AZ: A reference to the availability zone of the created EC2 instance.
    PublicDNS: A reference to the public DNSName of the created EC2 instance.
    PublicIP: A reference to the public IP address of the created EC2 instance.

## ECS Task Definition

This template creates an ECS Task Definition for running a containerized application. It includes an IAM role for ECS tasks.

Outputs

    ECSTaskDefinition: A reference to the created Task Definition.

## ECS Service

This template creates an ECS service that runs tasks based on the provided task definition.

Outputs

    ECSService: Output of ECS Service.

## How to Upload Templates

1. Open you AWS Management Console page and go to CloudFormation.

2. Click Create stack > With new resources (standard).

3. Select Upload a template file and then click Choose file to select the template you have on your system.

4. Click Next.

5. In the stack name, enter a name for your stack.

6. Click Next.

7. If your organization requires tags, you can enter them. You can also leave them blank.

8. Click I acknowledge that AWS CloudFormation might create IAM resources with custom names.

9. Click Create stack.

After you uploaded your template, you need to wait for Status CREATE_COMPLETE for your stack.
