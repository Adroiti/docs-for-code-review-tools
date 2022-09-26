Pattern: Disabled at-rest encryption for AWS EMR cluster

Issue: -

## Description

Data stored within an EMR cluster should be encrypted to ensure sensitive data is kept private.

**Resolution**: Enable at-rest encryption for EMR cluster.

## Examples

The following example will fail the aws-emr-enable-at-rest-encryption check.
```terraform

  resource "aws_emr_security_configuration" "bad_example" {
    name = "emrsc_other"
    
    configuration = <<EOF
  {
    "EncryptionConfiguration": {
      "AtRestEncryptionConfiguration": {
        "S3EncryptionConfiguration": {
          "EncryptionMode": "SSE-S3"
        },
        "LocalDiskEncryptionConfiguration": {
          "EncryptionKeyProviderType": "AwsKms",
          "AwsKmsKey": "arn:aws:kms:us-west-2:187416307283:alias/tf_emr_test_key"
        }
      },
      "EnableInTransitEncryption": false,
      "EnableAtRestEncryption": false
    }
  }
  EOF
  }
```

The following example will pass the aws-emr-enable-at-rest-encryption check.
```terraform

  resource "aws_emr_security_configuration" "good_example" {
    name = "emrsc_other"
  
    configuration = <<EOF
  {
    "EncryptionConfiguration": {
      "AtRestEncryptionConfiguration": {
        "S3EncryptionConfiguration": {
          "EncryptionMode": "SSE-S3"
        },
        "LocalDiskEncryptionConfiguration": {
          "EncryptionKeyProviderType": "AwsKms",
          "AwsKmsKey": "arn:aws:kms:us-west-2:187416307283:alias/tf_emr_test_key"
        }
      },
      "EnableInTransitEncryption": true,
      "EnableAtRestEncryption": true
    }
  }
  EOF
  }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/emr_security_configuration](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/emr_security_configuration)
- [https://docs.aws.amazon.com/config/latest/developerguide/operational-best-practices-for-nist_800-171.html](https://docs.aws.amazon.com/config/latest/developerguide/operational-best-practices-for-nist_800-171.html)