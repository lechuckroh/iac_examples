STACK_NAME ?= VPCPeering
STACK_FILE = vpc-peering.yaml
PARAM_FILE ?= seoul-parameters.json
KEYPAIR_NAME ?= example-key

.PHONY: create-stack
create-stack:
	@aws cloudformation create-stack --stack-name $(STACK_NAME) \
		--template-body file://$(STACK_FILE) \
		--parameters file://$(PARAM_FILE)

.PHONY: describe-stack
describe-stack:
	@aws cloudformation describe-stacks --stack-name $(STACK_NAME)

.PHONY: stack-events
stack-events:
	@aws cloudformation describe-stack-events --stack-name $(STACK_NAME)

.PHONY: delete-stack
delete-stack:
	@aws cloudformation delete-stack --stack-name $(STACK_NAME)

.PHONY: validate
validate:
	@aws cloudformation validate-template --template-body file://$(STACK_FILE)

.PHONY: create-keypair
create-keypair:
	@aws ec2 create-key-pair --key-name $(KEYPAIR_NAME) --query 'KeyMaterial' --output text > $(KEYPAIR_NAME).pem
	@chmod 600 $(KEYPAIR_NAME).pem
