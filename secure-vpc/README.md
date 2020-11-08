# Secure VPC

* [CloudFormation](cf/README.md)


## Resources

* Internet Gateway
* VPC with Private / Public Subnets on 2 AZs
* Public Subnet ACL
    * allow all outbound
    * allow TCP inbound from everywhere (22, 80, 443, 1024~)
    * allow all trafic from VPC
* Private Subnet ACL
    * allow all from VPC
    * allow TCP inbound from everywhere (1024~)
    * allow all outbound traffic
