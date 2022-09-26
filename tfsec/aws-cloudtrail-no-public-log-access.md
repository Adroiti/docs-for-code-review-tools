Pattern: Use of public S3 bucket for AWS CloudTrail

Issue: -

## Description

CloudTrail logs a record of every API call made in your account. These log files are stored in an S3 bucket. CIS recommends that the S3 bucket policy, or access control list (ACL), applied to the S3 bucket that CloudTrail logs to prevents public access to the CloudTrail logs. Allowing public access to CloudTrail log content might aid an adversary in identifying weaknesses in the affected account's use or configuration.

**Resolution**: Restrict public access to the S3 bucket.

## Examples

The following example will fail the aws-cloudtrail-no-public-log-access check.
```terraform

resource "aws_cloudtrail" "bad_example" {
   s3_bucket_name = "abcdefgh"
   event_selector {
     read_write_type           = "All"
     include_management_events = true
 
     data_resource {
       type = "AWS::S3::Object"
       values = ["${data.aws_s3_bucket.important-bucket.arn}/"]
     }
   }
}

resource "aws_s3_bucket" "good_example" {
	bucket = "abcdefgh"
	acl = "public-read"
}
 
```

The following example will pass the aws-cloudtrail-no-public-log-access check.
```terraform

 resource "aws_cloudtrail" "good_example" {
   is_multi_region_trail = true
   s3_bucket_name = "abcdefgh"
 
   event_selector {
     read_write_type           = "All"
     include_management_events = true
 
     data_resource {
       type = "AWS::S3::Object"
       values = ["${data.aws_s3_bucket.important-bucket.arn}/"]
     }
   }
 }

resource "aws_s3_bucket" "good_example" {
	bucket = "abcdefgh"
	acl = "private"
}
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudtrail#is_multi_region_trail](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudtrail#is_multi_region_trail)
- [https://docs.aws.amazon.com/AmazonS3/latest/userguide/configuring-block-public-access-bucket.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/configuring-block-public-access-bucket.html)