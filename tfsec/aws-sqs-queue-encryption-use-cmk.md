Pattern: Missing use of CMK for AWS SQS queue

Issue: -

## Description

Queues should be encrypted with customer managed KMS keys and not default AWS managed keys, in order to allow granular control over access to specific queues.

**Resolution**: Encrypt SQS Queue with a customer-managed key.

## Examples

The following example will fail the aws-sqs-queue-encryption-use-cmk check.
```terraform

 resource "aws_sqs_queue" "bad_example" {
	kms_master_key_id = "alias/aws/sqs"
 }
 
```

The following example will pass the aws-sqs-queue-encryption-use-cmk check.
```terraform

 resource "aws_sqs_queue" "good_example" {
 	kms_master_key_id = "/blah"
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sqs_queue#server-side-encryption-sse](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sqs_queue#server-side-encryption-sse)
- [https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html)