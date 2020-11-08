STACK_NAME ?= SecureVPC
STACK_FILE = secure-vpc.yaml
PARAM_FILE ?= seoul-parameters.json
CHANGE_SET_NAME ?= SecureVPCChangeSet

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

.PHONY: create-change
create-change:
	@aws cloudformation create-change-set --stack-name $(STACK_NAME) \
		--template-body file://$(STACK_FILE) \
		--parameters file://$(PARAM_FILE) \
		--change-set-name $(CHANGE_SET_NAME)

.PHONY: describe-change
describe-change:
	@aws cloudformation describe-change-set --stack-name $(STACK_NAME) \
		--change-set-name $(CHANGE_SET_NAME)

.PHONY: execute-change
execute-change:
	@aws cloudformation execute-change-set --stack-name $(STACK_NAME) \
		--change-set-name $(CHANGE_SET_NAME)

.PHONY: delete-change
delete-change:
	@aws cloudformation delete-change-set --stack-name $(STACK_NAME) \
		--change-set-name $(CHANGE_SET_NAME)

