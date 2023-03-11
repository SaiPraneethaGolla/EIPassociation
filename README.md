# EIPassociation
AWSTemplateFormatVersion: '2010-09-09'
Description: Create Elastic IP for EC2 Instance
Parameters:
  InstanceId:
    Description: Instance to which EIP to be allocated.
    Type: String
    Default: i-0e51217e5738a8cf8
  AllocationId:
    Description: Allocation ID for EIP
    Type: String
    Default: eipalloc-04e80eaea20a54a9f
  PrivateIp:
    Description: Private IP Address of EC2 Instance
    Type: String
    Default: 172.31.38.149

Resources:
  EipAssociate:
    Type: AWS::EC2::EIPAssociation
    Properties: 
      AllocationId: 
        Ref: AllocationId
      InstanceId: 
        Ref: InstanceId
      PrivateIpAddress: 
        Ref: PrivateIp
