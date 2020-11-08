# VPC Peering

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

## KeyPair

```bash
# create keypair 'example-key' if you don't have one.
$ make create-keypair
```

## Stack

```bash
# validate template
$ make validate

# deploy with default parameters
$ make create-stack

# deploy with 'mine.json' parameters
$ PARAM_FILE=mine.json make create-stack

# describe stack events
$ make stack-events

# describe stack
$ make describe-stack

# delete stack
$ make delete-stack
```

## Test
1. SSH into EC2 instance in public VPC
2. ping to EC2 instance in private VPC

