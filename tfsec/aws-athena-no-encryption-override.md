Pattern: Athena workgroups should enforce configuration to prevent client disabling encryption

Issue: -

## Description

Athena workgroup configuration should be enforced to prevent client side changes to disable encryption settings.

**Resolution**: Enforce the configuration to prevent client overrides.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_athena_workgroup" "bad_example" {
  name = "example"

  configuration {
    enforce_workgroup_configuration    = false
    publish_cloudwatch_metrics_enabled = true

    result_configuration {
      output_location = "s3://${aws_s3_bucket.example.bucket}/output/"

      encryption_configuration {
        encryption_option = "SSE_KMS"
        kms_key_arn       = aws_kms_key.example.arn
      }
    }
  }
}

resource "aws_athena_workgroup" "bad_example" {
  name = "example"

}
```

Example of **correct** code:

```terraform
resource "aws_athena_workgroup" "good_example" {
  name = "example"

  configuration {
    enforce_workgroup_configuration    = true
    publish_cloudwatch_metrics_enabled = true

    result_configuration {
      output_location = "s3://${aws_s3_bucket.example.bucket}/output/"

      encryption_configuration {
        encryption_option = "SSE_KMS"
        kms_key_arn       = aws_kms_key.example.arn
      }
    }
  }
}
```