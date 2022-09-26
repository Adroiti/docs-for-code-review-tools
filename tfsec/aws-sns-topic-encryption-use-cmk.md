Pattern: Missing use of CMK for AWS SNS topic

Issue: -

## Description

Topics should be encrypted with customer managed KMS keys and not default AWS managed keys in order to allow granular key management.

**Resolution**: Use a CMK for SNS Topic encryption.

## Examples

The following example will fail the aws-sns-topic-encryption-use-cmk check.
```terraform

 resource "aws_sns_topic" "bad_example" {
    kms_master_key_id = "alias/aws/sns"
 }
 
```

The following example will pass the aws-sns-topic-encryption-use-cmk check.
```terraform

 resource "aws_sns_topic" "good_example" {
 	kms_master_key_id = "/blah"
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic#example-with-server-side-encryption-sse](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic#example-with-server-side-encryption-sse)
- [https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html)