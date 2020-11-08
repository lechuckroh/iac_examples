# VPC Peering

* [CloudFormation](cf/README.md)


## Resources

* PublicVPC
    * InternetGateway
    * SecurityGroup (allow TCP inbound for SSH)
    * RouteTable
    * EC2 instance
* PrivateVPC
    * SecurityGroup (allow all ICMP traffic)
    * RouteTable
    * EC2 instance
* VPC Peering


## Test

1. SSH into EC2 instance in public VPC
2. ping to EC2 instance in private VPC

