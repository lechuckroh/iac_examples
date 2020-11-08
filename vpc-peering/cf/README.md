# VPC Peering

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
