Pattern: Allowed non-expiring passwords for AWS IAM policy

Issue: -

## Description

IAM account password policies should have a maximum age specified. The account password policy should be set to expire passwords after `90` days or less.

**Resolution**: Limit the password duration with an expiry in the policy.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# max_password_age not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	max_password_age = 90
	# ...
}
```