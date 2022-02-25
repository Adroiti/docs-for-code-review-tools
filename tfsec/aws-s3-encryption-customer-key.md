Pattern: Missing use of customer managed keys for S3 encryption

Issue: -

## Description

Encryption using AWS keys provides protection for your S3 buckets. To increase control of the encryption and manage factors like rotation use customer managed keys.

**Resolution**: Enable encryption using customer managed keys.

## Examples

The following example will fail the aws-s3-encryption-customer-key check.
```terraform

resource "aws_s3_bucket" "bad_exampl" {
   bucket = "mybucket"

  server_side_encryption_configuration {
    rule {
      apply_server_side_encryption_by_default {
        sse_algorithm     = "AES256"
      }
    }
  }
}
```

The following example will pass the aws-s3-encryption-customer-key check.
```terraform
resource "aws_kms_key" "good_example" {
  enable_key_rotation = true
}

resource "aws_s3_bucket" "good_example" {
   bucket = "mybucket"
 
   server_side_encryption_configuration {
     rule {
       apply_server_side_encryption_by_default {
         kms_master_key_id = aws_kms_key.example.arn
         sse_algorithm     = "aws:kms"
       }
     }
   }
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket#enable-default-server-side-encryption](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket#enable-default-server-side-encryption)
- [https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html)