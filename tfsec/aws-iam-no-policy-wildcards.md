Pattern: Use of wildcard for IAM policy

Issue: -

## Description

You should use the principle of least privilege when defining your IAM policies. This means you should specify each exact permission required without using wildcards, as this could cause the granting of access to certain undesired actions, resources and principals.

**Resolution**: Specify the exact permissions required, and to which resources they should apply instead of using wildcards.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_role_policy" "test_policy" {
	name = "test_policy"
	role = aws_iam_role.test_role.id

	policy = data.aws_iam_policy_document.s3_policy.json
}

resource "aws_iam_role" "test_role" {
	name = "test_role"
	assume_role_policy = jsonencode({
		Version = "2012-10-17"
		Statement = [
		{
			Action = "sts:AssumeRole"
			Effect = "Allow"
			Sid    = ""
			Principal = {
			Service = "s3.amazonaws.com"
			}
		},
		]
	})
}

data "aws_iam_policy_document" "s3_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["s3:*"]
    resources = ["*"]
  }
}
```

Example of **correct** code:

```terraform
resource "aws_iam_role_policy" "test_policy" {
	name = "test_policy"
	role = aws_iam_role.test_role.id

	policy = data.aws_iam_policy_document.s3_policy.json
}

resource "aws_iam_role" "test_role" {
	name = "test_role"
	assume_role_policy = jsonencode({
		Version = "2012-10-17"
		Statement = [
		{
			Action = "sts:AssumeRole"
			Effect = "Allow"
			Sid    = ""
			Principal = {
			Service = "s3.amazonaws.com"
			}
		},
		]
	})
}

data "aws_iam_policy_document" "s3_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["s3:GetObject"]
    resources = [aws_s3_bucket.example.arn]
  }
}
```